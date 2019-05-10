---
title: アンセーフ コードとポインター - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 9f4e74e1e8fa71d1492a10162191822c1edfb635
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608036"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="43bed-102">アンセーフ コードとポインター (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="43bed-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="43bed-103">タイプ セーフとセキュリティを維持するために、既定では C# はポインター演算をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="43bed-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="43bed-104">ただし、[unsafe](../../../csharp/language-reference/keywords/unsafe.md) キーワードを使用すれば、ポインターを使用できる unsafe コンテキストを定義できます。</span><span class="sxs-lookup"><span data-stu-id="43bed-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="43bed-105">ポインターの詳細については、「[ポインター型 (C# プログラミング ガイド)](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43bed-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43bed-106">共通言語ランタイム (CLR) では、アンセーフ コードは検査できないコードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="43bed-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="43bed-107">C# のアンセーフ コードは、必ずしも危険ではありません。ただ、CLR で安全性を検査できないコードであるというだけです。</span><span class="sxs-lookup"><span data-stu-id="43bed-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="43bed-108">そのため CLR は、完全に信頼できるアセンブリ内にある場合にのみ、アンセーフ コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="43bed-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="43bed-109">アンセーフ コードを使用する場合は、セキュリティ上のリスクやポインター エラーが発生しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="43bed-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="43bed-110">アンセーフ コードの概要</span><span class="sxs-lookup"><span data-stu-id="43bed-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="43bed-111">アンセーフ コードには次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="43bed-111">Unsafe code has the following properties:</span></span>  
  
- <span data-ttu-id="43bed-112">メソッド、型、およびコード ブロックをアンセーフとして定義できます。</span><span class="sxs-lookup"><span data-stu-id="43bed-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
- <span data-ttu-id="43bed-113">アンセーフ コードでアプリケーションのパフォーマンスが向上することがあります。これは、配列のバインド チェックが削除されるためです。</span><span class="sxs-lookup"><span data-stu-id="43bed-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
- <span data-ttu-id="43bed-114">アンセーフ コードは、ポインターを必要とするネイティブ関数を呼び出すときに必要です。</span><span class="sxs-lookup"><span data-stu-id="43bed-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
- <span data-ttu-id="43bed-115">アンセーフ コードを使用すると、セキュリティと安定性の面でリスクが生じます。</span><span class="sxs-lookup"><span data-stu-id="43bed-115">Using unsafe code introduces security and stability risks.</span></span>  
  
- <span data-ttu-id="43bed-116">C# でアンセーフ コードをコンパイルするには、[/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) を指定してアプリケーションをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bed-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43bed-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="43bed-117">Related Sections</span></span>  
 <span data-ttu-id="43bed-118">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="43bed-118">For more information, see:</span></span>  
  
- [<span data-ttu-id="43bed-119">ポインター型</span><span class="sxs-lookup"><span data-stu-id="43bed-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
- [<span data-ttu-id="43bed-120">固定サイズ バッファー</span><span class="sxs-lookup"><span data-stu-id="43bed-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
- [<span data-ttu-id="43bed-121">方法: ポインターを使用してバイトの配列をコピーする</span><span class="sxs-lookup"><span data-stu-id="43bed-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
- [<span data-ttu-id="43bed-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="43bed-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="43bed-123">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="43bed-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43bed-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="43bed-124">See also</span></span>

- [<span data-ttu-id="43bed-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="43bed-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
