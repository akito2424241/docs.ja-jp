---
title: "方法: WIF トレースを使用してクレーム対応アプリケーションおよびサービスをデバッグする | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# 方法: WIF トレースを使用してクレーム対応アプリケーションおよびサービスをデバッグする
## 対象  
  
-   Microsoft® Windows® Identity Foundation \(WIF\)  
  
-   サービス トレース ビューアー ツール \(SvcTraceViewer.exe\)  
  
-   WIF アプリケーションのトラブルシューティングとデバッグ  
  
## 概要  
 この方法では、WIF トレースの構成方法、トレース ログの収集方法、およびトレース ビューアー ツールを使用してトレース ログを分析する方法について、必要な手順を説明します。  WIF に関連する問題をトラブルシューティングするために、必要なアクションに対してトレース エントリの全般的なマッピングを行います。  
  
## 目次  
  
-   目的  
  
-   手順の要約  
  
-   手順 1 – Web.config 構成ファイルを使用して WIF のトレースを構成する  
  
-   手順 2 – トレース ビューアー ツールを使用して WIF のトレース ファイルを分析する  
  
-   手順 3 – WIF 関連の問題を修復するための解決策を特定する  
  
-   関連項目  
  
## 目的  
  
-   WIF トレースを構成する。  
  
-   トレース ビューアー ツールでトレース ログを表示する。  
  
-   トレース ログで WIF 関連の問題を特定する。  
  
-   トレース ログで検出された WIF 関連の問題に修正措置を適用する。  
  
## 手順の要約  
  
-   手順 1 – Web.config 構成ファイルを使用して WIF のトレースを構成する  
  
-   手順 2 – トレース ビューアー ツールを使用して WIF のトレース ファイルを分析する  
  
-   手順 3 – WIF 関連の問題を修復するための解決策を特定する  
  
## 手順 1 – Web.config 構成ファイルを使用して WIF のトレースを構成する  
 この手順では、*Web.config* ファイルの構成セクションに変更を加えて、WIF がイベントをトレースしてトレース ログに格納できるようにします。  
  
#### Web.config 構成ファイルを使用して WIF のトレースを構成するには  
  
1.  **ソリューション エクスプローラー** で、Visual Studio エディターのルートの **Web.config** または **App.config** 構成ファイルをダブルクリックして、ファイルを開きます。  ソリューションに **Web.config** または **App.config** 構成ファイルがない場合は、**ソリューション エクスプローラー**でソリューションを右クリックして、**\[追加\]**、**\[新しい項目...\]** の順にクリックして追加します。  **\[新しい項目\]** ダイアログ ボックスで、一覧から **\[アプリケーション構成ファイル\]** \(**App.config の場合**\) または **\[Web 構成ファイル\]** \(**Web.config の場合**\) を選択してから、**\[OK\]** をクリックします。  
  
2.  構成ファイルの最後にある **\< configuration \>** ノード内に、以下のような構成エントリを追加します。  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3.  上記の構成は、トレース イベントの詳細を生成し、*WIFTrace.e2e* ファイルにログを記録するよう WIF に指示します。  **switchValue** スイッチの値の完全なリストについては、トピック「[トレースの構成](http://msdn.microsoft.com/library/ms733025.aspx)」にあるトレース レベルの表を参照してください。  
  
## 手順 2 – トレース ビューアー ツールを使用して WIF のトレース ファイルを分析する  
 このステップでは、トレース ビューアー ツール \(SvcTraceViewer.exe\) を使用して WIF のトレース ログを分析します。  
  
#### トレース ビューアー ツール \(SvcTraceViewer.exe\) を使用して WIF のトレース ログを分析するには  
  
1.  トレース ビューアー ツール \(SvcTraceViewer.exe\) は、Windows SDK の一部として同梱されています。  Windows SDK をまだインストールしていない場合は、こちら \([Windows SDK](http://www.microsoft.com/download/en/details.aspx?id=8279)\) からダウンロードできます。  
  
2.  トレース ビューアー ツール \(SvcTraceViewer.exe\) を実行します。  通常、これはインストール パスの **Bin** フォルダーから使用できます。  
  
3.  たとえば、メニューで **\[ファイル\]**、**\[開く...\]** オプションをクリックするか、**Ctrl キーを押しながら O キーを押す**ショートカットを使用して、WIF トレースのログ ファイル WIFTrace.e2e を開きます。  トレース ビューアー ツールでトレース ログ ファイルが開きます。  
  
4.  **\[アクティビティ\]** タブでエントリを確認します。  各エントリには、アクティビティの数、ログに記録されたトレースの数、アクティビティの期間および開始と終了のタイムスタンプが含まれているはずです。  
  
5.  **\[アクティビティ\]** タブをクリックします。  ツールのメイン領域に詳細なトレース エントリが表示されます。  メニューにある **\[レベル\]** ドロップダウン リストを使用して、たとえば **\[すべて\]**、**\[警告\]**、**\[エラー\]**、**\[情報\]** など、特定のレベルのトレースをフィルター処理します。  
  
6.  特定のトレース エントリをクリックすると、ツールの下部の領域で詳細を確認できます。  詳細は、対応するタブを選択することで、**書式付き**および **XML** ビューで表示することができます。  
  
## 手順 3 – WIF 関連の問題を修復するための解決策を特定する  
 この手順では、WIF のトレース ログとトレース ビューアー ツールを使用して、WIF に関連する問題の解決方法を特定できます。  WIF 関連の例外と、問題をトラブルシューティングするための可能性のある解決策や必要な操作との全般的なマッピングを概説しています。  
  
#### WIF 関連の問題を修復するための解決策を特定するには  
  
1.  WIF の例外と問題を修正するために必要な操作に関する次の表を確認します。  
  
||||  
|-|-|-|  
|**エラー ID**|**エラー メッセージ**|**エラーを修復するために必要な操作**|  
|ID4175|セキュリティ トークンの発行者は、IssuerNameRegistry で認識されませんでした。  この発行者からのセキュリティ トークンを承認するには、この発行者の有効な名前を返すように IssuerNameRegistry を構成します。|このエラーは、MMC スナップインから拇印をコピーして、*Web.config* ファイルに貼り付けると発生する可能性があります。  具体的には、\[証明書のプロパティ\] ウィンドウからコピーするときに、テキスト文字列内で余分な印刷できない文字を取得することがあります。  この余分な文字により、拇印との照合が失敗します。正しく拇印をコピーするための手順は以下を参照してください。 [http:\/\/msdn.microsoft.com\/library\/ff359102.aspx](http://msdn.microsoft.com/library/ff359102.aspx)|  
  
## 関連項目  
  
-   [サービス トレース ビューアーを使用した相関トレースの表示とトラブルシューティング](http://msdn.microsoft.com/library/aa751795.aspx)