---
title: "方法 : 2 つのコントロールのプロパティをバインドする"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e79b1f9f00e8c76f94bf4386a284607f526624a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>方法 : 2 つのコントロールのプロパティをバインドする
この例を使用して別のものを 1 つのインスタンス化されたコントロールのプロパティをバインドする方法を示しています、<xref:System.Windows.Data.Binding.ElementName%2A>プロパティです。  
  
## <a name="example"></a>例  
 次の例は、バインドする方法を示しています、<xref:System.Windows.Controls.Panel.Background%2A>のプロパティ、<xref:System.Windows.Controls.Canvas>を<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A>のプロパティ、 <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 この例をレンダリングすると、次のようになります。  
  
 ![背景が緑のキャンバス](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **注**バインディング ターゲット プロパティ (この例では、<xref:System.Windows.Controls.Panel.Background%2A>プロパティ)、依存関係プロパティをする必要があります。 詳しくは、「 [データ バインディングの概要](../../../../docs/framework/wpf/data/data-binding-overview.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [バインディング ソースを指定する](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [方法トピック](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
