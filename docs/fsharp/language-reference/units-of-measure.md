---
title: "測定単位 (F#)"
description: "どの浮動小数点型の学習 f# の符号付き整数値を関連付けることができます、測定単位の長さ、ボリューム、および大容量を示すために通常使用されます。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: cb2eb658-df6c-422e-afad-97422609c773
ms.openlocfilehash: 2d0683e864c5684a78c02e177c296d3067295723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="units-of-measure"></a><span data-ttu-id="50dea-104">測定単位</span><span class="sxs-lookup"><span data-stu-id="50dea-104">Units of Measure</span></span>

<span data-ttu-id="50dea-105">F# での浮動小数点値と符号付き整数値を関連付けることが通常は、一括、長さ、ボリュームを示すために使用する測定単位。</span><span class="sxs-lookup"><span data-stu-id="50dea-105">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="50dea-106">算術リレーションシップでは、正しい単位があるを防止することを確認するコンパイラを有効にする数量を単位を使用するプログラミング エラーです。</span><span class="sxs-lookup"><span data-stu-id="50dea-106">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>


## <a name="syntax"></a><span data-ttu-id="50dea-107">構文</span><span class="sxs-lookup"><span data-stu-id="50dea-107">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="50dea-108">コメント</span><span class="sxs-lookup"><span data-stu-id="50dea-108">Remarks</span></span>
<span data-ttu-id="50dea-109">前の構文を定義*単位名*メジャーの単位として。</span><span class="sxs-lookup"><span data-stu-id="50dea-109">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="50dea-110">省略可能部分を使用して、以前に定義された単位で新しいメジャーを定義します。</span><span class="sxs-lookup"><span data-stu-id="50dea-110">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="50dea-111">たとえば、次の行がメジャーを定義`cm`(センチメートル)。</span><span class="sxs-lookup"><span data-stu-id="50dea-111">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="50dea-112">次の行のメジャーを定義する`ml`(milliliter) 立方センチメートルとして (`cm^3`)。</span><span class="sxs-lookup"><span data-stu-id="50dea-112">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="50dea-113">前の構文で*メジャー*ユニットを含む式を示します。</span><span class="sxs-lookup"><span data-stu-id="50dea-113">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="50dea-114">単位を使用する数式の整数乗がサポートされている (正と負の値)、単位間のスペースを示す 2 つの単位では、製品`*`単位の積を示しますと`/`単位の商を示します。</span><span class="sxs-lookup"><span data-stu-id="50dea-114">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="50dea-115">逆数の単位、負の整数乗を使用することができますか、または`/`分子と単位の数式の分母となる間の分離を示すです。</span><span class="sxs-lookup"><span data-stu-id="50dea-115">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="50dea-116">分母に複数の単位は、かっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="50dea-116">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="50dea-117">単位は後のスペースで区切られた、`/`分母では、次の任意の単位の一部として解釈されます、`*`分子の一部として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="50dea-117">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="50dea-118">単位式の場合は無次元を示すためだけにするかまたはと共に分子など、他の単位は、1 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="50dea-118">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="50dea-119">たとえば、速度の単位として書き込まれる`1/s`ここで、`s`秒を示すです。</span><span class="sxs-lookup"><span data-stu-id="50dea-119">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="50dea-120">かっこは、単位の数式では使用されません。</span><span class="sxs-lookup"><span data-stu-id="50dea-120">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="50dea-121">単位の式で数値変換の定数を指定しません。ただし、単位に変換定数を個別に定義でき、計算の単位がチェックされたで使用できます。</span><span class="sxs-lookup"><span data-stu-id="50dea-121">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="50dea-122">同じことを意味する単位の数式は、さまざまな方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="50dea-122">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="50dea-123">そのため、コンパイラでは、単位の数式が、逆数、グループ単位を 1 つの分子と分母に負の累乗を変換し、分子と分母のユニットが、アルファベット順に並べ替えますが一貫性のある形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="50dea-123">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="50dea-124">単位式など、`kg m s^-2`と`m /s s * kg`に変換されます両方`kg m/s^2`です。</span><span class="sxs-lookup"><span data-stu-id="50dea-124">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="50dea-125">浮動小数点式では、測定単位を使用します。</span><span class="sxs-lookup"><span data-stu-id="50dea-125">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="50dea-126">タイプ セーフの別のレベルを追加するメジャーの関連付けられている単位と共に浮動小数点数を使用して、弱く型指定された浮動小数点数を使用するときに、数式で発生する単位の不一致エラーの回避に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="50dea-126">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="50dea-127">浮動を記述する場合と一致単位を使用する小数点式、式のユニットが、必要があります。</span><span class="sxs-lookup"><span data-stu-id="50dea-127">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="50dea-128">次の例に示すように、山かっこで単位式を持つリテラルの注釈を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="50dea-128">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="50dea-129">数と、山かっ; 間にスペースを配置しないでください。ただし、リテラルのサフィックスをなどに含めることができます`f`、次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="50dea-129">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="50dea-130">このような注釈がそのプリミティブ型のリテラルの型を変更 (など`float`) ディメンションが指定された型になど`float<cm>`または、この場合、`float<miles/hour>`です。</span><span class="sxs-lookup"><span data-stu-id="50dea-130">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="50dea-131">単位の注釈の`<1>`無次元の数量、およびその型が単位パラメーターを指定せず、プリミティブ型と同じことを示します。</span><span class="sxs-lookup"><span data-stu-id="50dea-131">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="50dea-132">測定単位の種類は、浮動小数点または符号付き整数型、余分な単位の注釈を角かっこで囲んでと共にします。</span><span class="sxs-lookup"><span data-stu-id="50dea-132">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="50dea-133">変換の種類を記述するときにそのため、 `g` (グラム) に`kg`(キロ)、次のように、型を記述します。</span><span class="sxs-lookup"><span data-stu-id="50dea-133">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="50dea-134">測定単位は、コンパイル単位のチェックに使用されますが、実行時環境では保持されません。</span><span class="sxs-lookup"><span data-stu-id="50dea-134">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="50dea-135">そのため、パフォーマンスは影響ありません。</span><span class="sxs-lookup"><span data-stu-id="50dea-135">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="50dea-136">測定単位はだけでなく浮動小数点型は、任意の型に適用できます。ただし、唯一の浮動小数点型には、整数型、および 10 進数型の次元のサポートの数量が署名されています。</span><span class="sxs-lookup"><span data-stu-id="50dea-136">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="50dea-137">したがって、のみ理にかなってプリミティブ型およびこれらのプリミティブ型が含まれる集約にメジャーの単位を使用します。</span><span class="sxs-lookup"><span data-stu-id="50dea-137">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="50dea-138">次の例では、測定単位の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="50dea-138">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
<span data-ttu-id="50dea-139">次のコード例は、無次元浮動小数点数から次元設定された浮動小数点値に変換する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="50dea-139">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="50dea-140">乗算 1.0, 1.0 に次元を適用します。</span><span class="sxs-lookup"><span data-stu-id="50dea-140">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="50dea-141">ような関数に抽象化することができます`degreesFahrenheit`です。</span><span class="sxs-lookup"><span data-stu-id="50dea-141">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="50dea-142">また、する無次元浮動小数点関数に次元設定された値を渡す際にする必要があります単位を取り消すまたはにキャスト`float`を使用して、`float`演算子。</span><span class="sxs-lookup"><span data-stu-id="50dea-142">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="50dea-143">除算するこの例では`1.0<degC>`への引数の`printf`ため`printf`無次元数量が必要です。</span><span class="sxs-lookup"><span data-stu-id="50dea-143">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="50dea-144">このコードの入力と出力から次の例のセッションを示しています。</span><span class="sxs-lookup"><span data-stu-id="50dea-144">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="50dea-145">汎用的な単位を使用します。</span><span class="sxs-lookup"><span data-stu-id="50dea-145">Using Generic Units</span></span>
<span data-ttu-id="50dea-146">関連するメジャーの単位を持つデータを処理するジェネリック関数を記述できます。</span><span class="sxs-lookup"><span data-stu-id="50dea-146">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="50dea-147">これを行う、型パラメーターと汎用的な単位と型を指定することによって次のコード例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="50dea-147">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="50dea-148">ジェネリック ユニットと集約型の作成</span><span class="sxs-lookup"><span data-stu-id="50dea-148">Creating Aggregate Types with Generic Units</span></span>
<span data-ttu-id="50dea-149">次のコードでは、一般的な単位を持つ個別の浮動小数点値で構成される集計の種類を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50dea-149">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="50dea-150">これにより、さまざまなユニットの動作を作成する 1 つの型。</span><span class="sxs-lookup"><span data-stu-id="50dea-150">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="50dea-151">また、ジェネリック ユニットでは、単位の 1 つのセットを持つジェネリック型が異なる一連の単位で同じジェネリック型とは異なる型であることを確認して型の安全性が保持されます。</span><span class="sxs-lookup"><span data-stu-id="50dea-151">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="50dea-152">この方法の基礎は、`Measure`属性は、型パラメーターに適用できます。</span><span class="sxs-lookup"><span data-stu-id="50dea-152">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a><span data-ttu-id="50dea-153">実行時の単位</span><span class="sxs-lookup"><span data-stu-id="50dea-153">Units at Runtime</span></span>
<span data-ttu-id="50dea-154">測定単位は、静的な型をチェックするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="50dea-154">Units of measure are used for static type checking.</span></span> <span data-ttu-id="50dea-155">浮動小数点値がコンパイルされると、メジャーの単位排除されるので、実行時に、単位は失われます。</span><span class="sxs-lookup"><span data-stu-id="50dea-155">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="50dea-156">そのため、実行時に単位のチェックが依存する機能を実装しようとするとはできません。</span><span class="sxs-lookup"><span data-stu-id="50dea-156">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="50dea-157">たとえば、実装、`ToString`単位出力する関数はできません。</span><span class="sxs-lookup"><span data-stu-id="50dea-157">For example, implementing a `ToString` function to print out the units is not possible.</span></span>


## <a name="conversions"></a><span data-ttu-id="50dea-158">変換</span><span class="sxs-lookup"><span data-stu-id="50dea-158">Conversions</span></span>
<span data-ttu-id="50dea-159">単位を持つ型に変換する (たとえば、 `float<'u>`) ユニットがない型には、標準変換関数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="50dea-159">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="50dea-160">たとえば、使用することができます`float`に変換する、`float`値を持たないものユニットでは、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="50dea-160">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="50dea-161">単位を持つ値を単位のない値を変換するには、適切な単位で注釈が付けられる 1 か 1.0 の値を掛けますにすることができます。</span><span class="sxs-lookup"><span data-stu-id="50dea-161">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="50dea-162">ただし、相互運用性レイヤーを記述するためもユニットと単位のない値を値に変換するのに使用できるいくつかの明示的な関数です。</span><span class="sxs-lookup"><span data-stu-id="50dea-162">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="50dea-163">これらには、 [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3)モジュール。</span><span class="sxs-lookup"><span data-stu-id="50dea-163">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="50dea-164">例については、単位からに変換する`float`を`float<cm>`を使用して[FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)次のコードに示すように、します。</span><span class="sxs-lookup"><span data-stu-id="50dea-164">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a><span data-ttu-id="50dea-165">F# Power Pack の測定単位</span><span class="sxs-lookup"><span data-stu-id="50dea-165">Units of Measure in the F# Power Pack</span></span>
<span data-ttu-id="50dea-166">単位ライブラリは、f# PowerPack で使用できます。</span><span class="sxs-lookup"><span data-stu-id="50dea-166">A unit library is available in the F# PowerPack.</span></span> <span data-ttu-id="50dea-167">SI 単位と物理定数単体ライブラリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="50dea-167">The unit library includes SI units and physical constants.</span></span>


## <a name="see-also"></a><span data-ttu-id="50dea-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="50dea-168">See Also</span></span>
[<span data-ttu-id="50dea-169">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="50dea-169">F# Language Reference</span></span>](index.md)