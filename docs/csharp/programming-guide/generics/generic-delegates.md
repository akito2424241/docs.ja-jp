---
title: "汎用デリゲート (C# プログラミング ガイド)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1377723f18d6dd0e984538b530acbc7aa8d52feb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="generic-delegates-c-programming-guide"></a>汎用デリゲート (C# プログラミング ガイド)
[デリゲート](../../../csharp/language-reference/keywords/delegate.md)はその独自の型パラメーターを定義できます。 ジェネリック デリゲートを参照するコードは、次の例に示すように、ジェネリック クラスをインスタンス化したり、ジェネリック メソッドを呼び出したりするときのように、型引数を指定し、構築されたクローズ型を作成できます。  
  
 [!code-csharp[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 C# バージョン 2.0 には、メソッド グループ変換という新しい機能があります。これはジェネリック デリゲート型だけでなく具象型にも適用され、前の行を次のような簡素化された構文で記述できます。  
  
 [!code-csharp[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 ジェネリック クラス内で定義されたデリゲートは、クラス メソッドと同様の方法でジェネリック クラスの型パラメーターを利用できます。  
  
 [!code-csharp[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 デリゲートを参照するコードで、次のように、包含クラスの型引数を指定する必要があります。  
  
 [!code-csharp[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 ジェネリック デリゲートは、典型的な設計パターンに基づいてイベントを定義する場合に特に便利です。sender 引数は厳密に型指定できること、<xref:System.Object> との間でキャストが必要ないことがその理由です。  
  
 [!code-csharp[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Collections.Generic>  
 [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
 [ジェネリックの概要](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [ジェネリック メソッド](../../../csharp/programming-guide/generics/generic-methods.md)  
 [ジェネリック クラス](../../../csharp/programming-guide/generics/generic-classes.md)  
 [ジェネリック インターフェイス](../../../csharp/programming-guide/generics/generic-interfaces.md)  
 [デリゲート](../../../csharp/programming-guide/delegates/index.md)  
 [ジェネリック](~/docs/standard/generics/index.md)
