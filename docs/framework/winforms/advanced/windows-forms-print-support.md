---
title: "Windows フォームにおける印刷のサポート"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81f89ee41eb9f8b492ab12e30ae4580cdffbd8f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-print-support"></a>Windows フォームにおける印刷のサポート
Windows フォームにおける印刷は、主に使用して、 [PrintDocument コンポーネント](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)を印刷するユーザーを有効にするコンポーネントと[PrintPreviewDialog コントロール](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)コントロール、 [PrintDialogコンポーネント](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)と[PageSetupDialog コンポーネント](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)Windows オペレーティング システムに慣れているユーザーが使い慣れたグラフィカル インターフェイスを提供するコンポーネントです。  
  
 通常の新しいインスタンスを作成、<xref:System.Drawing.Printing.PrintDocument>コンポーネント、設定を使用して印刷する対象を記述するプロパティ、<xref:System.Drawing.Printing.PrinterSettings>と<xref:System.Drawing.Printing.PageSettings>クラス、および呼び出し、<xref:System.Drawing.Printing.PrintDocument.Print%2A>を実際には、ドキュメントを印刷する方法です。  
  
 Windows ベースのアプリケーションからの印刷の実行中に、<xref:System.Drawing.Printing.PrintDocument>コンポーネントは中止印刷 ダイアログ ボックスをユーザーに表示アラート印刷が発生しているという事実にし、印刷ジョブをキャンセルできません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: 標準の Windows フォーム印刷ジョブを作成する](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 使用する方法について説明します、<xref:System.Drawing.Printing.PrintDocument>から Windows フォームを印刷するコンポーネントです。  
  
 [方法: 実行時に PrintDialog のユーザー入力をキャプチャする](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 選択した印刷オプションを使用してプログラムから変更する方法について説明します、<xref:System.Windows.Forms.PrintDialog>コンポーネントです。  
  
 [方法: Windows フォームでユーザーのコンピューターに接続されたプリンターを選択する](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 印刷を使用するプリンターの変更について説明します、<xref:System.Windows.Forms.PrintDialog>実行時コンポーネントです。  
  
 [方法: Windows フォームでグラフィックスを印刷する](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 プリンターに送信側のグラフィックスについて説明します。  
  
 [方法: Windows フォームで複数ページのテキスト ファイルを印刷する](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 プリンターに送信するテキストを説明します。  
  
 [方法: Windows フォームの印刷ジョブを完了する](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 印刷ジョブの完了をユーザーに通知する方法について説明します。  
  
 [方法: Windows フォームを印刷する](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 現在のフォームのコピーを印刷する方法を示します。  
  
 [方法: Windows フォームで印刷プレビューを使用して印刷する](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 使用する方法を示します、<xref:System.Windows.Forms.PrintPreviewDialog>ドキュメントを印刷します。  
  
## <a name="related-sections"></a>関連項目  
 [PrintDocument コンポーネント](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 使用方法を説明、<xref:System.Drawing.Printing.PrintDocument>コンポーネントです。  
  
 [PrintDialog コンポーネント](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 使用方法を説明、<xref:System.Windows.Forms.PrintDialog>コンポーネントです。  
  
 [PrintPreviewDialog コントロール](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 使用方法を説明、<xref:System.Windows.Forms.PrintPreviewDialog>コントロール。  
  
 [PageSetupDialog コンポーネント](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 使用方法を説明、<xref:System.Windows.Forms.PageSetupDialog>コンポーネントです。  
  
 <xref:System.Drawing.Printing>  
 内のクラスをについて説明します、<xref:System.Drawing.Printing>名前空間。
