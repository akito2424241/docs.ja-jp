---
title: "NULL リテラルと型推論 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: eeea6a6b1674361a605d5236e203699d08724df3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="null-literals-and-type-inference-entity-sql"></a>NULL リテラルと型推論 (Entity SQL)
NULL リテラルは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 型システムのすべての型と互換性があります。 ただし、正しく、推論される null リテラルの型の[!INCLUDE[esql](../../../../../../includes/esql-md.md)]null リテラルを使用できる場所で特定の制約が適用されます。  
  
## <a name="typed-nulls"></a>型指定された NULL  
 型指定された NULL は任意の場所で使用できます。 型指定された NULL の場合、型が不明であるため、型推論は必要ありません。 たとえば、次の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 構成要素を使用すると、Int16 型の NULL を作成できます。  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a>型指定されない NULL リテラル  
 型指定されない NULL リテラルは、次のようなコンテキストで使用できます。  
  
-   CAST 式または TREAT 式への引数として使用できます。 これは、型指定された NULL 式を生成する場合に推奨される方法です。  
  
-   メソッドまたは関数への引数として使用できます。 標準のオーバーロード規則が適用されます。  
  
-   +、-、/ などの算術式への引数の 1 つとして使用できます。 他の引数に NULL リテラルを指定することはできません。指定した場合、型推論ができなくなります。  
  
-   論理式 (AND、OR、または NOT) への引数として使用できます。 引数はすべて Boolean 型であると見なされます。  
  
-   IS NULL 式または IS NOT NULL 式への引数として使用できます。  
  
-   LIKE 式への 1 つ以上の引数として使用できます。 引数はすべて文字列であると見なされます。  
  
-   名前付きの型コンストラクターへの 1 つ以上の引数として使用できます。  
  
-   マルチセット コンストラクターへの 1 つ以上の引数として使用できます。 マルチセット コンストラクターに渡す引数のうち、少なくとも 1 つは、NULL リテラルではない式である必要があります。  
  
-   CASE 式の THEN 式または ELSE 式への 1 つ以上の引数として使用できます。 CASE 式の THEN 式または ELSE 式のうち、少なくとも一方は、NULL リテラルではない式である必要があります。  
  
 型指定されない NULL リテラルは、その他のシナリオでは使用できません。 たとえば、行コンストラクターへの引数として使用することはできません。  
  
## <a name="see-also"></a>参照  
 [Entity SQL の概要](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
