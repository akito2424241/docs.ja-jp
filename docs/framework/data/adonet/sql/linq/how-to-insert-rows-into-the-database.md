---
title: "方法 : 行をデータベースに挿入する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2b51ba8191ddd1b0e70c483970133cfe22d321a1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-insert-rows-into-the-database"></a>方法 : 行をデータベースに挿入する
関連付けられているオブジェクトを追加することで、データベースに行を挿入する[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Table%601>コレクションと、データベースへの変更を送信します。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]変換により変更が適切な SQL に`INSERT`コマンド。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の `Insert`、`Update`、および `Delete` の既定のデータベース操作メソッドはオーバーライドできます。 詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)です。  
>   
>  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] を使用している開発者は、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]を使用して、同じ用途のストアド プロシージャを開発できます。  
  
 以下の手順では、有効な <xref:System.Data.Linq.DataContext> で Northwind データベースに接続されるものと想定しています。 詳細については、次を参照してください。[する方法: データベースへの接続](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)です。  
  
### <a name="to-insert-a-row-into-the-database"></a>行をデータベースに挿入するには  
  
1.  送信する列データを含む新しいオブジェクトを作成します。  
  
2.  新しいオブジェクトを追加する、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table`データベース内のターゲット テーブルに関連付けられているコレクション。  
  
3.  データベースに変更内容を送信します。  
  
## <a name="example"></a>例  
 次のサンプル コードでは、`Order` 型の新しいオブジェクトを作成し、適切な値をこのオブジェクトに設定します。 その後で、新しいオブジェクトを `Order` コレクションに追加します。 最後にこの変更内容を `Orders` テーブルの新しい行としてデータベースに送信します。  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a>参照  
 [方法 : 変更の競合を管理する](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [DataContext メソッド (O/R デザイナー)](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [方法: 更新、挿入、および削除 (O/R デザイナー) を実行するストアド プロシージャを割り当てる](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [データの変更と変更の送信](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
