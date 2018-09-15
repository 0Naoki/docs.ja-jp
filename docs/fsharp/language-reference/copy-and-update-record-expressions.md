---
title: コピーして更新するレコード式 (f#)
description: "'コピーと更新レコード式を' 既存のレコード、更新プログラムをコピーするフィールドを指定および更新されたレコードを返します記述する方法について説明します。"
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: d2b089e8a7fc5c7ee26139003e23d2eaa8a3174e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2018
ms.locfileid: "45638348"
---
# <a name="copy-and-update-record-expressions"></a>レコード式のコピーと更新

A*コピーして更新するレコード式*を既存のレコードをコピーし、指定のフィールドを更新し、更新されたレコードを返す式を指定します。

## <a name="syntax"></a>構文

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Remarks

レコードは、可能な更新プログラムを既存のレコードがないように、既定では、不変です。 更新したレコードを作成するには、レコードのすべてのフィールドには、もう一度指定する必要があります。 このタスクを簡略化する、*コピーして更新するレコード式*ことができます。 この式は、既存のレコードには、式から指定したフィールドと、式で指定された存在しないフィールドを使用して、同じ型の新しいデフォルトを作成します。
これは、フィールドの値の一部を変更する可能性があります、既存のレコードをコピーする必要があるときに役立ちます。

新しく作成されたレコード インスタンスがかかります。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

使用することがそのレコードのフィールドでのみ更新する場合は、*コピーして更新するレコード式*次のように。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>関連項目

- [レコード](records.md)
- [F# 言語リファレンス](index.md)
