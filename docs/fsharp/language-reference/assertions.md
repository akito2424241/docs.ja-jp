---
title: "アサーション (F#)"
description: "F# のプログラミング言語で式をテストするはデバッグ機能として 'assert' 式を使用する方法を説明します。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a>アサーション

`assert`式が式のテストに使用できるデバッグ機能。 デバッグ モードでエラーが発生すると、アサーションによってシステム エラーのダイアログ ボックスが生成されます。

## <a name="syntax"></a>構文

```fsharp
assert condition
```

## <a name="remarks"></a>コメント

`assert`式の型が`bool -> unit`です。

前の構文で*条件*ブール式をテストするを表します。 式が評価された場合`true`実行がそのまま継続します。 評価結果が場合`false`、システム エラー ダイアログ ボックスを生成します。 エラー ダイアログ ボックス キャプションがあり、文字列を含む**アサーションが失敗した**です。 ダイアログ ボックスには、アサーション エラーが発生したことを示します。 スタック トレースが含まれています。

デバッグ モードでコンパイルするときだけアサーション チェックが有効にします。つまり場合、定数`DEBUG`が定義されています。 プロジェクト システムで、既定では、`DEBUG`定数は、リリース構成ではなく、デバッグ構成で定義されています。

F# の例外処理を使用してアサーション失敗エラーをキャッチできません。

>[!NOTE]
`assert`関数に解決<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>です。

## <a name="example"></a>例

次のコード例の使用を示しています、`assert`式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a>関連項目

[F# 言語リファレンス](index.md)
