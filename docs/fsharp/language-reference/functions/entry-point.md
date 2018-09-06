---
title: エントリ ポイント (F#)
description: 実行が正式に開始、実行可能ファイルとしてコンパイルされた f# プログラムのエントリ ポイントを設定する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884771"
---
# <a name="entry-point"></a><span data-ttu-id="73e68-103">エントリ ポイント</span><span class="sxs-lookup"><span data-stu-id="73e68-103">Entry Point</span></span>

<span data-ttu-id="73e68-104">このトピックでは、f# プログラムのエントリ ポイントの設定を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73e68-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="73e68-105">構文</span><span class="sxs-lookup"><span data-stu-id="73e68-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="73e68-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="73e68-106">Remarks</span></span>

<span data-ttu-id="73e68-107">前の構文で*let-関数-バインド*内の関数の定義には、`let`バインド。</span><span class="sxs-lookup"><span data-stu-id="73e68-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="73e68-108">実行可能ファイルの実行が正式な開始位置としてコンパイルされるプログラムへのエントリ ポイント。</span><span class="sxs-lookup"><span data-stu-id="73e68-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="73e68-109">適用することによって f# アプリケーションへのエントリ ポイントを指定する、`EntryPoint`属性をプログラムの`main`関数。</span><span class="sxs-lookup"><span data-stu-id="73e68-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="73e68-110">この関数 (を使用して作成、`let`バインディング) コンパイルの最後のファイルの最後の関数でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="73e68-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="73e68-111">最後のコンパイル済みファイルは、プロジェクトの最後のファイルまたはコマンドラインに渡される最後のファイルです。</span><span class="sxs-lookup"><span data-stu-id="73e68-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="73e68-112">エントリ ポイント関数が型`string array -> int`します。</span><span class="sxs-lookup"><span data-stu-id="73e68-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="73e68-113">コマンドラインで指定された引数が渡される、`main`文字列の配列内の関数。</span><span class="sxs-lookup"><span data-stu-id="73e68-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="73e68-114">配列の最初の要素は、最初の引数他の言語であるために、実行可能ファイルの名前は、配列に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="73e68-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="73e68-115">戻り値は、プロセスの終了コードとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="73e68-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="73e68-116">0 は、成功した場合、通常、ことを示します。0 以外の値は、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="73e68-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="73e68-117">0 以外のリターン コードの特定の意味の規則はありません。リターン コードの意味では、アプリケーション固有です。</span><span class="sxs-lookup"><span data-stu-id="73e68-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="73e68-118">次の例では、単純な`main`関数。</span><span class="sxs-lookup"><span data-stu-id="73e68-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="73e68-119">コマンドラインを使用したこのコードが実行されると`EntryPoint.exe 1 2 3`出力は次のようにします。</span><span class="sxs-lookup"><span data-stu-id="73e68-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="73e68-120">暗黙的なエントリ ポイント</span><span class="sxs-lookup"><span data-stu-id="73e68-120">Implicit Entry Point</span></span>

<span data-ttu-id="73e68-121">プログラムがにない場合**EntryPoint**エントリ ポイントでコンパイルする最後のファイルの最上位レベルのバインドを明示的に示す属性は、エントリ ポイントとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="73e68-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="73e68-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="73e68-122">See also</span></span>

- [<span data-ttu-id="73e68-123">関数</span><span class="sxs-lookup"><span data-stu-id="73e68-123">Functions</span></span>](index.md)
- [<span data-ttu-id="73e68-124">let バインド</span><span class="sxs-lookup"><span data-stu-id="73e68-124">let Bindings</span></span>](let-bindings.md)
