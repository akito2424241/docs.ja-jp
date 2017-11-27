---
title: "抽象クラス (F#)"
description: "一部またはすべてのメンバーを実装しないままにして f# 抽象クラスをについて説明し、オブジェクトの種類の多様な一連の共通の機能を表します。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 209bcca70318db59506011b1f2bb74a09bf3814a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="abstract-classes"></a>抽象クラス

*抽象クラス*実装を派生クラスによって提供されることができるように実装されていません、一部またはすべてのメンバーのままにするクラスです。

## <a name="syntax"></a>構文

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>コメント
オブジェクト指向プログラミングでは、抽象クラスは、階層の基本クラスとして使用し、オブジェクトの種類の多様な一連の共通機能を表します。 "Abstract"という名前が示すように、抽象クラス多くの場合、対応していない問題ドメインの具体的なエンティティに直接できます。 ただし、どのような多くのさまざまな具体的なエンティティが共通では関係。

抽象クラスがあります、`AbstractClass`属性。 実装されているし、メンバーが実装されていませんできます。 用語の使用*抽象*クラスは、他の .NET 言語以外の場合と同様に適用するとただし、用語の使用*抽象*メソッドとプロパティに適用される場合は、少し異なりますからの f# では、他の .NET 言語で使用します。 F# でメソッドが付いている場合、`abstract`キーワード、このことを示しますメンバーと呼ばれる、エントリ、*仮想ディスパッチ スロット*、その種類の仮想関数の内部テーブルにします。 つまり、メソッドは、仮想ですが、`virtual`キーワードは、f# 言語では使用されません。 キーワード`abstract`メソッドを実装するかどうかに関係なく、仮想メソッドで使用します。 仮想ディスパッチ スロットの宣言は、そのディスパッチ スロットのメソッドの定義とは別です。 そのため、抽象メソッドの宣言といずれかで、個別の定義の両方の組み合わせでは、仮想メソッドの宣言と他の .NET 言語での定義の f# 相当、`default`キーワードまたは`override`キーワード。 詳細と例については、次を参照してください。[メソッド](members/methods.md)です。

クラスは抽象メソッドが宣言されていますが、定義されていないことがある場合にのみ抽象と見なされます。 そのため、抽象メソッドを持つクラスは、必ずしも抽象クラスではできません。 クラスには、抽象メソッドが定義されていませんが、しない限りは使用しないで、 **AbstractClass**属性。

前の構文で*アクセシビリティ修飾子*できます`public`、`private`または`internal`です。 詳細については、「[Access Control](access-control.md)」(アクセス制御) を参照してください。

その他の種類と同様、基底クラスと 1 つ以上のインターフェイスの基本抽象クラスことができます。 と共に別々 の行に各基底クラスまたはインターフェイスが表示されます、`inherit`キーワード。

抽象クラスの種類の定義は、完全に定義されたメンバーを含めることができますが、抽象メンバーを含めることもできます。 抽象メンバーの構文は、前の構文で別々 に表示されます。 この構文では、*型シグネチャ*メンバーの一覧を含む、パラメーターの順序と戻り値の型の型で区切られます`->`トークンや`*`カリー化を必要に応じてトークンとタプルパラメーター。 抽象メンバー型のシグネチャの構文は、署名ファイル内で使用して、Visual Studio コード エディターの IntelliSense によって表示されるのと同じです。

次のコードは、抽象クラスが 2 つ非抽象派生クラス、四角形と円形の図形を示しています。 この例では、抽象クラス、メソッド、プロパティを使用する方法を示します。 この例では、抽象クラス図形は、具体的なエンティティの円、四角形の共通の要素を表します。 (2 次元座標系) のすべての図形の一般的な機能は、抽象化されて、図形のクラスに: グリッド、回転の角度と、領域および境界のプロパティでの位置。 これは、オーバーライドできます、位置、個々 の図形を変更できませんが、動作を除く。

その対称のための回転インバリアントが、Circle クラスと同様に、回転メソッドをオーバーライドすることができます。 ように、Circle クラスでは、回転メソッドは何も実行しないメソッドに置き換えられます。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**出力:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>関連項目
[クラス](classes.md)

[メンバー](members/index.md)

[メソッド](members/methods.md)

[プロパティ](members/Properties.md)