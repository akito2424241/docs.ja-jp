---
title: "手書き認識"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 384f21587c29e6afe82964fc28432f5a6be92b05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="handwriting-recognition"></a>手書き認識
このセクションでは、WPF プラットフォームのデジタル インクに関連する認識の基礎について説明します。  
  
## <a name="recognition-solutions"></a>認識ソリューション  
 次の例は、[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) クラスを利用し、インクを認識する方法を示しています。  
  
> [!NOTE]
>  このサンプルでは、手書き認識エンジンをインストールする必要があります。  
  
 Visual Studio で **InkRecognition** という名前の新しい WPF アプリケーション プロジェクトを作成します。 Window1.xaml ファイルの内容を次の XAML コードに置き換えます。 このコードにより、アプリケーションのユーザー インターフェイスがレンダリングされます。  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Microsoft インク アセンブリである Microsoft.Ink.dll に参照を追加します。これは Program Files\Common Files\Microsoft Shared\Ink にあります。 この分離コード ファイルの内容を次のコードで置き換えます。  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>参照  
 [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)
