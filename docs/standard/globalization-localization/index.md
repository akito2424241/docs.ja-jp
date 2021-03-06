---
title: ".NET Framework アプリケーションのグローバライズとローカライズ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- international applications [.NET Framework]
- globalization [.NET Framework], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET Framework], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
caps.latest.revision: "42"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 63f0e001280773c55f18f0604ca93986acbb9674
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2018
---
# <a name="globalizing-and-localizing-net-framework-applications"></a>.NET Framework アプリケーションのグローバライズとローカライズ
1 つ以上の言語にローカライズされるアプリケーションなど、[国際対応アプリケーション](http://msdn.microsoft.com/goglobal/bb978433.aspx)を開発するには、グローバリゼーション、ローカライズ対象の確認、およびローカリゼーションの 3 つの手順が必要です。  
  
 [グローバリゼーション](../../../docs/standard/globalization-localization/globalization.md)  
 これは、特定のカルチャや言語に依存せず、すべてのユーザーに対して、ローカライズされたユーザー インターフェイスと、その地域に合ったデータをサポートするような、アプリケーションの設計と開発を行う手順です。 これはカルチャ固有の前提に基づかない決定によって設計とプログラミングを行うことです。 グローバライズされたアプリケーションは、ローカライズされていなくても、後から比較的容易に 1 つ以上の言語にローカライズできるように設計開発されています。  
  
 [ローカライズ化の確認](../../../docs/standard/globalization-localization/localizability-review.md)  
 この手順により、アプリケーションのコードと設計をレビューして、ローカライズが容易になるようにし、ローカライズのための潜在的な問題点を識別し、アプリケーションの実行可能コードがリソースから分離されていることを確認します。 グローバリゼーションの段階が効果的なものであれば、ローカリゼーション レビューはグローバリゼーションの過程で行われた設計とコーディングの決定を確認するものになります。 ローカライズ対象の確認の段階では、ローカライズの段階でアプリケーションのソース コードを変更する必要がないように、残っている問題を特定します。  
  
 [ローカリゼーション](../../../docs/standard/globalization-localization/localization.md)  
 この手順では、特定のカルチャまたは地域に合わせてアプリケーションをカスタマイズします。 グローバリゼーションとローカライズ対象の確認を適切に行うと、ローカリゼーションでは主にユーザー インターフェイスの翻訳作業が行われます。  
  
 この 3 つの手順に従うことにより、次の 2 つの利点があります。  
  
-   米国英語などのような 1 つのカルチャだけをサポートするアプリケーションを、他のカルチャもサポートするように変更する作業を行う必要がなくなります。  
  
-   ローカライズされたアプリケーションが、より安定してバグがより少ないものになります。  
  
 .NET Framework には、国際対応アプリケーションやローカライズされたアプリケーションの開発の拡張サポートが備わっています。 特に、.NET Framework クラス ライブラリの多くの型メンバーは、現在のユーザーのカルチャまたは特定のカルチャの規則を表す値を返すことができ、グローバリゼーションに役立ちます。 また、.NET Framework はサテライト アセンブリをサポートし、アプリケーションのローカライズ プロセスを容易にします。  
  
 詳細については、[グローバリゼーションのドキュメント](/globalization/)をご覧ください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [グローバリゼーション](../../../docs/standard/globalization-localization/globalization.md)  
 国際対応アプリケーションを作成するための最初の手順を説明します。カルチャや言語に依存しないアプリケーションの設計とコーディングを行います。  
  
 [ローカライズ化の確認](../../../docs/standard/globalization-localization/localizability-review.md)  
 ローカライズされたアプリケーションを作成するための 2 つ目の手順を説明します。ローカライズのための潜在的な問題点を識別します。  
  
 [ローカリゼーション](../../../docs/standard/globalization-localization/localization.md)  
 ローカライズされたアプリケーションを作成するための最後の手順を説明します。特定の地域またはカルチャのために、アプリケーションのユーザー インターフェイスをカスタマイズします。  
  
 [カルチャを認識しない文字列操作](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 既定ではカルチャが識別される .NET Framework のメソッドやクラスを使用して、カルチャが識別されない結果を取得する方法について説明します。  
  
 [推奨される国際対応アプリケーション開発手順](../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)  
 国際対応 ASP.NET アプリケーションのグローバリゼーション、ローカリゼーション、および開発の推奨手順について説明します。  
  
## <a name="reference"></a>参照  
 <xref:System.Globalization?displayProperty=nameWithType> 名前空間  
 言語、国/地域、使用する暦、日付、通貨、通知の書式パターン、文字列の並べ替え順序など、カルチャ関連の情報を定義するクラスが含まれています。  
  
 <xref:System.Resources> 名前空間  
 リソースを作成、操作、および使用するためのクラスが格納されている名前空間です。  
  
 <xref:System.Text> 名前空間  
 ASCII、ANSI、Unicode、およびその他の文字エンコーディングを表すクラスが格納されている名前空間です。  
  
 [Resgen.exe (リソース ファイル ジェネレーター)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)  
 Resgen.exe を使用して .txt ファイルと XML ベース リソース フォーマット (.resx) ファイルを共通言語ランタイムのバイナリ .resources ファイルに変換する方法について説明します。  
  
 [Winres.exe (Windows フォーム リソース エディター)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md)  
 Winres.exe を使用して Windows フォームのフォームをローカライズする方法について説明します。
