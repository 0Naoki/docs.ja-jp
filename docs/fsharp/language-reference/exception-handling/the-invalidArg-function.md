---
title: 例外:invalidArg 関数
description: について説明しますが、どのようにF#'invalidArg' 関数に引数例外が生成されます。
ms.date: 05/16/2016
ms.openlocfilehash: 7fd8d48b80970dbbafc0c23a478b4ccf3490f3ee
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613337"
---
# <a name="exceptions-the-invalidarg-function"></a>例外:invalidArg 関数

`invalidArg`関数に引数例外が生成されます。

## <a name="syntax"></a>構文

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Remarks

前の構文でパラメーター名は、文字列の引数が正しくないパラメーターの名前です。 *エラー メッセージの文字列*リテラル文字列または型の値は、`string`します。 `Message`例外オブジェクトのプロパティ。

によって生成された例外`invalidArg`は、`System.ArgumentException`例外。 次のコードの使用を示します`invalidArg`例外をスローします。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

出力は、次は、後に (非表示) スタック トレース。

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>関連項目

- [例外処理](index.md)
- [例外の種類](exception-types.md)
- [例外処理:`try...with`式](the-try-with-expression.md)
- [例外処理:`try...finally`式](the-try-finally-expression.md)
- [例外: `raise` 関数](the-raise-function.md)
- [例外処理:`failwith`関数](the-failwith-function.md)