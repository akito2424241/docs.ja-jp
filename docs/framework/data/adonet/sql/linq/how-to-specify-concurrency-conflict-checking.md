---
title: "方法 : 同時実行の競合のチェックを指定する"
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
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 51176e53af158536ab895c64a8eb3cf015aa01b1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-concurrency-conflict-checking"></a>方法 : 同時実行の競合のチェックを指定する
<xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出すときに同時実行の競合をチェックするデータベース列を指定できます。 詳細については、次を参照してください。[する方法: 同時実行の競合があるテストを指定するメンバー](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)です。  
  
## <a name="example"></a>例  
 次のコード例では、更新の確認時に `HomePage` メンバーを検査しないことを指定しています。 詳細については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>」を参照してください。  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>参照  
 [LINQ to SQL オブジェクト モデル](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [方法 : コード エディターを使用してエンティティ クラスをカスタマイズする](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
