---
title: "UriTemplate と UriTemplateTable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac77fe2c83828d2cc9473417d2b29b2d2e540923
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="uritemplate-and-uritemplatetable"></a>UriTemplate と UriTemplateTable
Web 開発者は、サービスの応答先となる URI の形状とレイアウトを記述できる必要があります。 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] では、開発者が URI を制御するための 2 つの新しいクラスが追加されています。 <xref:System.UriTemplate> と <xref:System.UriTemplateTable> は、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] における URI ベースのディスパッチ エンジンの基盤となります。 これらのクラスは単独で使用することもできるため、開発者は [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] サービスを実装せずにテンプレートと URI マッピング機構を利用できます。  
  
## <a name="templates"></a>テンプレート  
 テンプレートとは、一連の相対 URI を記述する方法です。 次の表の URI テンプレートのセットは、各種気象情報を取得するシステムがどのように定義されているかを示しています。  
  
|データ|テンプレート|  
|----------|--------------|  
|国の天気予報|weather/national|  
|州の天気予報|weather/{state}|  
|都市の天気予報|weather/{state}/{city}|  
|アクティビティの天気予報|weather/{state}/{city}/{activity}|  
  
 この表は、構造が似ている一連の URI を示しています。 各エントリが URI テンプレートです。 中かっこで囲まれたセグメントは変数を表します。 中かっこで囲まれていないセグメントはリテラル文字を表します。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] のテンプレート クラスを使用すると、開発者は "/weather/wa/seattle/cycling" のような受信 URI を取得し、これを "/weather/{state}/{city}/{activity}" として説明するテンプレートと照合できます。  
  
## <a name="uritemplate"></a>UriTemplate  
 <xref:System.UriTemplate> は、URI テンプレートをカプセル化するクラスです。 コンストラクターは、テンプレートを定義する文字列パラメーターを受け取ります。 この文字列には、次のセクションで説明する形式のテンプレートが含まれます。 <xref:System.UriTemplate> クラスには、受信 URI をテンプレートと照合するメソッド、テンプレートから URI を生成するメソッド、テンプレートで使用されている変数名のコレクションを取得するメソッド、2 つのテンプレートが等しいかどうかを判断するメソッド、およびテンプレートの文字列を返すメソッドが用意されています。  
  
 <xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> は、ベース アドレスと候補となる URI を取得し、その URI をテンプレートと照合します。 URI とテンプレートが一致した場合は、<xref:System.UriTemplateMatch> インスタンスが返されます。 <xref:System.UriTemplateMatch> オブジェクトには、ベース URI、候補となる URI、クエリ パラメーターの名前/値コレクション、相対パス セグメントの配列、一致した変数の名前/値コレクション、照合を実行する際に使用する <xref:System.UriTemplate> インスタンス、候補となる URI の一致していない部分を含む文字列 (テンプレートにワイルドカードが含まれているときに使用)、およびテンプレートに関連付けられたオブジェクトが格納されます。  
  
> [!NOTE]
>  <xref:System.UriTemplate> クラスは、候補となる URI をテンプレートと照合するときにスキームとポート番号を無視します。  
  
 テンプレートから URI を生成できるメソッドとして、<xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> と <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> の 2 つのメソッドがあります。 <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> は、ベース アドレスおよびパラメーターの名前/値コレクションを取得します。 テンプレートのバインド時に、これらのパラメーターが変数に代入されます。 <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> は、名前と値のペアを取得し、これらのペアを左から右の順に代入します。  
  
 <xref:System.UriTemplate.ToString> は、テンプレート文字列を返します。  
  
 <xref:System.UriTemplate.PathSegmentVariableNames%2A> プロパティには、テンプレート文字列のパス セグメント内で使用される変数の名前のコレクションが格納されます。  
  
 <xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> は <xref:System.UriTemplate> をパラメーターとして受け取り、2 つのテンプレートが等しいかどうかを示すブール値を返します。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]このトピックで後述する「テンプレートの等価性」を参照してください。  
  
 <xref:System.UriTemplate> は、HTTP URI 文法に準じるすべての URI スキームで使用できるように設計されています。 サポートされている URI スキームの例を次に示します。  
  
-   http://  
  
-   https://  
  
-   net.tcp://  
  
-   net.pipe://  
  
-   sb://  
  
 file:// や urn:// などのスキームは、HTTP URI 文法に準じていません。このため、URI テンプレートで使用すると予期せぬ結果が発生します。  
  
### <a name="template-string-syntax"></a>テンプレート文字列の構文  
 テンプレートには、パス、クエリ (省略可能)、およびフラグメント (省略可能) の 3 つの部分があります。 テンプレートの一例を次に示します。  
  
```  
"/weather/{state}/{city}?forecast={length)#frag1  
```  
  
 パスは "/weather/{state}/{city}"、クエリは "?forecast={length}、フラグメントは "#frag1" でそれぞれ構成されています。  
  
 パス式では、先頭と末尾のスラッシュは省略可能です。 クエリ式とフラグメント式は、いずれも式全体を省略できます。 パスは、一連のセグメントで区切られた '/'、各セグメントは、リテラル値、変数名 ({中かっこ} で書き込まれます)、またはワイルドカードを持つことができます (書き込まれる '\*')。 上記のテンプレートでは、"/weather/" セグメントがリテラル値で、"{state}" と "{city}" が変数です。 変数が中かっこの内容から名前を取得し、作成する具体的な値で置き換えられる後で、*クローズである URI*です。 ワイルドカードは省略可能では、論理的に一致する「残りのパス」、URI の末尾にのみ使用できます。  
  
 クエリ式 (存在する場合) では、'&' で区切られた順序なしの一連の名前と値のペアを指定します。 クエリ式の要素には、リテラル ペア (x=2) または変数ペア (x={var}) を指定できます。 変数を指定できるのはクエリ式の右辺のみです。 ({someName} = {someValue}) は指定できません。 対になっていない値 (?x) は使用できません。 空のクエリ式と、1 つの '?' だけで構成されたクエリ式は同じものです (いずれも "任意のクエリ" を意味します)。  
  
 フラグメント式はリテラル値で構成できます。変数は使用できません。  
  
 テンプレート文字列内のすべてのテンプレート変数名は、一意であることが必要です。 テンプレート変数名では、大文字と小文字は区別されません。  
  
 有効なテンプレート文字列の例を以下に示します。  
  
-   ""  
  
-   "/shoe"  
  
-   "/shoe/*"  
  
-   "{shoe}/boat"  
  
-   "{shoe}/{ボート}/bed/{キルト}"  
  
-   「靴/{ボート}」  
  
-   "靴/{ボート}/*"  
  
-   "靴/ボート? x = 2"  
  
-   "靴/{ボート}? x = {ベッド}"  
  
-   "shoe/{boat}?x={bed}&y=band"  
  
-   "? x = {shoe}"  
  
-   "shoe?x=3&y={var}  
  
 無効なテンプレート文字列の例を以下に示します。  
  
-   "{shoe}/}/x = 2"– 変数名と重複します。  
  
-   "{shoe}/boat? ベッド = {shoe}"– 変数名と重複します。  
  
-   "? x = 2 & x = 3"– リテラルにある場合でも、クエリ文字列内の名前/値ペアは一意である必要があります。  
  
-   "? x = 2 &"– クエリ文字列の形式が正しくありません。  
  
-   "? 2 & x = {shoe}"– クエリ文字列が名前/値ペアにする必要があります。  
  
-   "しますか? y = 2 & & X = 3"– クエリ文字列が名前値のペアにする必要があります、名前に始めることはできません '&' です。  
  
### <a name="compound-path-segments"></a>複合パス セグメント  
 複合パス セグメントでは、単一の URI パス セグメントに複数の変数およびリテラルと組み合わせた変数を含むことができます。 有効な複合パス セグメントの例を次に示します。  
  
-   /filename.{ext}/  
  
-   /{filename}.jpg/  
  
-   /{filename}.{ext}/  
  
-   /{a}.{b}someLiteral{c}({d})/  
  
 無効なパス セグメントの例を次に示します。  
  
-   /{} – 変数には名前が付けられている必要があります。  
  
-   /{shoe}{boat} – 変数はリテラルによって分割されている必要があります。  
  
### <a name="matching-and-compound-path-segments"></a>照合と複合パス セグメント  
 複合パス セグメントを使用すると、1 つのパス セグメント内に複数の変数を含む UriTemplate を定義できます。 たとえば、次のテンプレート文字列で:"アドレス/{state} です。{city}"2 つの変数 (state と city) が同じセグメント内で定義されています。 このテンプレートには、"http://example.com/Washington.Redmond"などの URL と一致しますが、"http://example.com/Washington.Redmond.Microsoft"のような URL は一致もします。 後者の場合、状態変数には、"Washington"が含まれ、city 変数は"Redmond.Microsoft"が含まれます。 この場合、任意のテキスト ('/' 以外) が {city} 変数と一致することになります。 テンプレートを「余分な」テキストと一致しない場合は、配置、変数セグメントでは、別のテンプレート、たとえば:"アドレス/{state}/{city} です。  
  
### <a name="named-wildcard-segments"></a>名前付きワイルドカード セグメント  
 名前付きワイルドカード セグメントは、ワイルドカード文字 '*' で始まる変数名を持つ任意のパス変数セグメントです。 次のテンプレート文字列には、"shoe" という名前付きワイルドカード セグメントが含まれています。  
  
```  
"literal/{*shoe}"  
```  
  
 ワイルドカード セグメントは、次の規則に従う必要があります。  
  
-   1 つのテンプレート文字列に含められる名前付きワイルドカード セグメントは 1 つのみです。  
  
-   名前付きワイルドカード セグメントは、パス内の右端のセグメントにある必要があります。  
  
-   名前付きワイルドカード セグメントは、匿名ワイルドカード セグメントのあるテンプレート文字列には使用できません。  
  
-   名前付きワイルドカード セグメントの名前は一意である必要があります。  
  
-   名前付きワイルドカード セグメントには既定値を指定できません。  
  
-   名前付きワイルドカード セグメントで終わることはできません「/」です。  
  
### <a name="default-variable-values"></a>既定変数値  
 既定変数値を使用すると、テンプレート内で変数に既定値を指定できます。 既定変数は、変数を宣言する中かっこを使用して指定することも、UriTemplate コンストラクターに渡されるコレクションとして指定することもできます。 次のテンプレートに、既定値のある変数を使用して <xref:System.UriTemplate> を指定する 2 つの方法を示します。  
  
```  
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 このテンプレートでは、既定値が `a` で `1` という名前の変数と、既定値が `b` で `5` という名前の変数が宣言されています。  
  
> [!NOTE]
>  パス セグメント変数のみが、既定値を持つことができます。 クエリ文字列変数、複合セグメント変数、および名前付きワイルドカード変数には、既定値を指定することはできません。  
  
 候補 URI との照合時に、既定値のある変数がどのように処理されるかを次のコードに示します。  
  
```  
Uri baseAddress = new Uri("http://localhost:800   
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);0");  
UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);  
Uri candidate = new Uri("http://localhost:8000/OR");  
  
UriTemplateMatch m1 = t.Match(baseAddress, candidate);  
  
// Display contents of BoundVariables  
foreach (string key in m1.BoundVariables.AllKeys)  
{  
    Console.WriteLine("\t\t{0}={1}", key, m1.BoundVariables[key]);  
}  
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/  
// Candidate URI: http://localhost:8000/OR  
// BoundVariables:  
//      STATE=OR  
//       CITY=Redmond  
```  
  
> [!NOTE]
>  http://localhost:8000/// のような URI は、上記のコード内に一覧表示されるテンプレートには一致しません。一致するのは、http://localhost:8000/ のような URI です。  
  
 テンプレートを使用して URI を作成する場合に、既定値のある変数がどのように処理されるかを次のコードに示します。  
  
```  
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
 変数の既定値として `null` が指定されている場合、さらに追加の制約があります。 テンプレート文字列の右端のセグメントに変数を含んでいるか、その変数の右側にあるすべてのセグメントが `null` を既定値としている変数のみに既定値として `null` を指定できます。 既定値に `null` が指定されている有効なテンプレート文字列を次に示します。  
  
-   ```  
    UriTemplate t = new UriTemplate("shoe/{boat=null}");  
    ```  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");  
    ```  
 既定値に `null` が指定されている無効なテンプレート文字列を次に示します。  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value  
    ```  
### <a name="default-values-and-matching"></a>既定値と照合  
 候補 URI と既定値が指定されているテンプレートとの照合時に、候補 URI に値が指定されていない場合には、<xref:System.UriTemplateMatch.BoundVariables%2A> コレクションに既定値が配置されます。  
  
### <a name="template-equivalence"></a>テンプレートの等価性  
 2 つのテンプレートと呼ばれます*構造的に同等*すべてのリテラルの一致して、同じセグメントに変数があります。 たとえば、次のテンプレートは構造的に等しいテンプレートです。  
  
-   /a/{var1}/b b/{var2}?x=1&y=2  
  
-   a/{x}/b%20b/{var1}?y=2&x=1  
  
-   a/{y}/B%20B/{z}/?y=2&x=1  
  
 次の点に注意してください。  
  
-   テンプレートに先頭のスラッシュが含まれている場合、最初の 1 つだけが無視されます。  
  
-   テンプレート文字列が構造的に等しいかどうかを比較する場合、変数名とパス セグメントでは大文字小文字は無視されますが、クエリ文字列では区別されます。  
  
-   クエリ文字列は順序なしです。  
  
## <a name="uritemplatetable"></a>UriTemplateTable  
 <xref:System.UriTemplateTable> クラスは、開発者が選択したオブジェクトにバインドされた <xref:System.UriTemplate> オブジェクトの結合テーブルを表します。 <xref:System.UriTemplateTable> を呼び出す前に、<xref:System.UriTemplate> に 1 つ以上の <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> を含めておく必要があります。 <xref:System.UriTemplateTable> が呼び出されるまでは、<xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> の内容を変更できます。 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> が呼び出されると、検証が実行されます。 実行される検証の種類は、`allowMultiple` に対する <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> パラメーターの値によって異なります。  
  
 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> を渡して `false` を呼び出した場合、<xref:System.UriTemplateTable> はテーブル内に複数のテンプレートが存在しないことを確認します。 構造的に等しいテンプレートが見つかった場合は、例外がスローされます。 これは、受信 URI と一致するテンプレートが 1 つだけであることを確認する場合に、<xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> と組み合わせて使用します。  
  
 <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> を渡して `true` を呼び出した場合、<xref:System.UriTemplateTable> は、構造的に等しい複数のテンプレートが <xref:System.UriTemplateTable> に含まれることを許可します。  
  
 <xref:System.UriTemplate> に追加された一連の <xref:System.UriTemplateTable> オブジェクトにクエリ文字列が含まれている場合、これらの文字列をあいまいにすることはできません。 許可されるのは同一のクエリ文字列です。  
  
> [!NOTE]
>  <xref:System.UriTemplateTable> では、HTTP 以外のスキームを使用したベース アドレスを使用できますが、候補 URI をテンプレートと照合する場合にスキームおよびポート番号は無視されます。  
  
### <a name="query-string-ambiguity"></a>クエリ文字列のあいまいさ  
 複数のテンプレートと一致する URI が存在する場合、等しいパスを共有するテンプレートにあいまいなクエリ文字列が含まれています。  
  
 クエリ文字列の次のセットにはあいまいさはありません。  
  
-   ?x=1  
  
-   ?x=2  
  
-   ?x=3  
  
-   ?x=1&y={var}  
  
-   ?x=2&z={var}  
  
-   ?x=3  
  
-   ?x=1  
  
-   ?  
  
-   ? x={var}  
  
-   ?  
  
-   ?m=get&c=rss  
  
-   ?m=put&c=rss  
  
-   ?m=get&c=atom  
  
-   ?m=put&c=atom  
  
 クエリ文字列テンプレートの次のセットにはあいまいさがあります。  
  
-   ?x=1  
  
-   ?x={var}  
  
 "x=1" - 両方のテンプレートに一致します。  
  
-   ?x=1  
  
-   ?y=2  
  
 "x=1&y=2" は両方のテンプレートに一致します。 これは、クエリ文字列に、一致するテンプレートよりも多くのクエリ文字列変数が含まれている可能性があるからです。  
  
-   ?x=1  
  
-   ?x=1&y={var}  
  
 "x=1&y=3" は両方のテンプレートに一致します。  
  
-   ?x=3&y=4  
  
-   ?x=3&z=5  
  
> [!NOTE]
>  文字 á と Á が URI パスまたは <xref:System.UriTemplate> のパス セグメントのリテラルの一部として出現した場合、これらは異なる文字と見なされます (ただし、a と A は同じ文字と見なされます)。 文字 á と Á が <xref:System.UriTemplate> の {variableName} またはクエリ文字列の一部として出現した場合は、これらは同じ文字と見なされます (a と A も同じ文字と見なされます)。  
  
## <a name="see-also"></a>参照  
 [WCF Web HTTP プログラミング モデルの概要](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 [WCF Web HTTP プログラミング オブジェクト モデル](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)  
 [UriTemplate テーブル](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [UriTemplate テーブル ディスパッチャー](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
