---
title: "方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61b2a39943dfca412afa4b66265aabbf65b9ccf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする
任意のセルの外観をカスタマイズするには、処理することにより、<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Windows.Forms.DataGridView.CellPainting>イベント。 抽出することができます、<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Drawing.Graphics>から、<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A>のプロパティ、<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>です。 この<xref:System.Drawing.Graphics>、全体の外観に影響する可能性<xref:System.Windows.Forms.DataGridView>コントロールは通常するのには現在塗りつぶされているセルの外観だけに影響します。 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>のプロパティ、<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>現在塗りつぶされているセルに、描画操作を制限することができます。  
  
 次のコード例では、すべてのセルを描画します、`ContactName`列を使用して、<xref:System.Windows.Forms.DataGridView>コントロールの色のスキーム。 各セルのテキスト コンテンツを描画する<xref:System.Drawing.Color.Crimson%2A>と同じ色に埋め込みの四角形を描画し、<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Windows.Forms.DataGridView.GridColor%2A>プロパティです。  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   A<xref:System.Windows.Forms.DataGridView>という名前のコントロール`dataGridView1`で、`ContactName`など、Northwind サンプル データベース内の Customers テーブルの列です。  
  
-   System、System.Windows.Forms、および System.Drawing の各アセンブリへの参照。  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [Windows フォーム DataGridView コントロールのカスタマイズ](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
