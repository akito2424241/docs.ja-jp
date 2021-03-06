---
title: "方法 : データベースの行を更新する"
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
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 62c1ac16ab2d8607c7dd505bf4cb68f475dc26a7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-update-rows-in-the-database"></a>方法 : データベースの行を更新する
関連付けられているオブジェクトのメンバーの値を変更することにより、データベース内の行を更新することができます、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601>コレクションと、データベースへの変更を送信します。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]変換により変更が適切な SQL に`UPDATE`コマンド。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の `Insert`、`Update`、および `Delete` の既定のデータベース操作メソッドはオーバーライドできます。 詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)です。  
>   
>  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] を使用している開発者は、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]を使用して、同じ用途のストアド プロシージャを開発できます。  
  
 以下の手順では、有効な <xref:System.Data.Linq.DataContext> で Northwind データベースに接続されるものと想定しています。 詳細については、次を参照してください。[する方法: データベースへの接続](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)です。  
  
### <a name="to-update-a-row-in-the-database"></a>データベースの行を更新するには  
  
1.  データベースで更新する行をクエリします。  
  
2.  結果として得られた [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] オブジェクトのメンバー値に、必要な変更を加えます。  
  
3.  データベースに変更内容を送信します。  
  
## <a name="example"></a>例  
 次の例では、データベースの注文 #11000 をクエリし、結果として得られた `ShipName` オブジェクトの `ShipVia` と `Order` の値を変更します。 次に、これらのメンバー値の変更内容を、`ShipName` 列と `ShipVia` 列に対する変更としてデータベースに送信します。  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a>参照  
 [方法 : 変更の競合を管理する](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [方法: 更新、挿入、および削除 (O/R デザイナー) を実行するストアド プロシージャを割り当てる](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [データの変更と変更の送信](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
