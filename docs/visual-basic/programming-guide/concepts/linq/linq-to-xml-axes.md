---
title: "LINQ to XML 軸 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 119c4808b6d436c2227331dbb3ab9c4077ff56f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-axes-visual-basic"></a>LINQ to XML 軸 (Visual Basic)
XML ツリーを作成した後、または XML ドキュメントを XML ツリーに読み込んだ後は、クエリを実行して要素や属性を調べたり、その値を取得したりできます。  
  
 クエリを記述する前に、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 軸について理解しておく必要があります。 軸メソッドは 2 種類あります。まず、単一の <xref:System.Xml.Linq.XElement> オブジェクト、<xref:System.Xml.Linq.XDocument> オブジェクト、または <xref:System.Xml.Linq.XNode> オブジェクトで呼び出すメソッドがあります。 これらのメソッドは、単一のオブジェクトに対して機能し、<xref:System.Xml.Linq.XElement>、<xref:System.Xml.Linq.XAttribute>、または <xref:System.Xml.Linq.XNode> オブジェクトのコレクションを返します。 第 2 に、コレクションに対して機能し、コレクションを返す拡張メソッドがあります。 拡張メソッドは、ソース コレクションを列挙し、コレクション内の各アイテムに対して適切な軸メソッドを呼び出し、結果を連結します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|トピック|説明|  
|-----------|-----------------|  
|[LINQ to XML 軸の概要 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|軸を定義し、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] クエリのコンテキストにおける使用方法について説明します。|  
|[方法: 要素 (LINQ to XML) のコレクションを取得する (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|<xref:System.Xml.Linq.XContainer.Elements%2A> メソッドについて説明します。 このメソッドは、要素の子要素のコレクションを取得します。|  
|[方法: 要素 (LINQ to XML) の値の取得 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|要素の値を取得する方法について説明します。|  
|[方法: 要素名 (LINQ to XML) をフィルター (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|軸を使用する場合に要素名をフィルター処理する方法について説明します。|  
|[方法: チェーンの軸メソッドの呼び出し (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|軸メソッドの呼び出しを連結する方法について説明します。|  
|[方法: 1 つの子要素 (LINQ to XML) を取得 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|タグ名を指定して要素の単一の子要素を取得する方法について説明します。|  
|[方法: 属性 (LINQ to XML) のコレクションを取得する (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|<xref:System.Xml.Linq.XElement.Attributes%2A> メソッドについて説明します。 このメソッドは、要素の属性を取得します。|  
|[方法: 単一の属性 (LINQ to XML) を取得する (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|属性名を指定して要素の単一の属性を取得する方法について説明します。|  
|[方法: 属性 (LINQ to XML) の値の取得 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|属性の値を取得する方法について説明します。|  
|[方法: 要素 (Visual Basic) の浅い値を取得](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|要素の浅い値を取得する方法について説明します。|  
|[Visual Basic (LINQ to XML) の統合言語軸](../../../../visual-basic/programming-guide/concepts/linq/language-integrated-axes.md)|要約、[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]統合軸です。|  
  
## <a name="see-also"></a>関連項目  
 [プログラミング ガイド (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
