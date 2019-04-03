---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 1b8de27e872914ba59d73126d2a9a7c42609165e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829028"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="b7ec1-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7ec1-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="b7ec1-103">プロパティの記述が読み取らないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7ec1-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7ec1-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b7ec1-105">ルール</span><span class="sxs-lookup"><span data-stu-id="b7ec1-105">Rules</span></span>  
 <span data-ttu-id="b7ec1-106">**宣言コンテキスト。**</span><span class="sxs-lookup"><span data-stu-id="b7ec1-106">**Declaration Context.**</span></span> <span data-ttu-id="b7ec1-107">`WriteOnly` は、モジュール レベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="b7ec1-108">これは、意味の宣言のコンテキストを`WriteOnly`プロパティは、クラス、構造体、またはモジュールにある必要があるあり、ソース ファイル、名前空間、またはプロシージャにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="b7ec1-109">としてプロパティを宣言する`WriteOnly`が変数ではありません。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="b7ec1-110">WriteOnly を使用する場合</span><span class="sxs-lookup"><span data-stu-id="b7ec1-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="b7ec1-111">値の設定ができないことができる、使用側コードたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="b7ec1-112">たとえば、ソーシャル登録番号やパスワードなどの機密データを設定していない任意のコンポーネントによるアクセスから保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="b7ec1-113">このような場合は、使用することができます、`WriteOnly`プロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7ec1-114">定義して使用するときに、`WriteOnly`プロパティ、次の追加の保護対策を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
-   <span data-ttu-id="b7ec1-115">**オーバーライドします。**</span><span class="sxs-lookup"><span data-stu-id="b7ec1-115">**Overriding.**</span></span> <span data-ttu-id="b7ec1-116">プロパティがクラスのメンバーである場合は、許可する既定の[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)を宣言していないと`Overridable`または`MustOverride`します。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="b7ec1-117">これは派生クラスが上書きすることによって、不要なアクセスを作成することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
-   <span data-ttu-id="b7ec1-118">**アクセス レベルです。**</span><span class="sxs-lookup"><span data-stu-id="b7ec1-118">**Access Level.**</span></span> <span data-ttu-id="b7ec1-119">1 つまたは複数の変数で、プロパティの機密データを保持する場合では、宣言[プライベート](../../../visual-basic/language-reference/modifiers/private.md)できるように、その他のコードはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
-   <span data-ttu-id="b7ec1-120">**暗号化。**</span><span class="sxs-lookup"><span data-stu-id="b7ec1-120">**Encryption.**</span></span> <span data-ttu-id="b7ec1-121">プレーン テキストではなく、暗号化された形式では、すべての機密データを格納します。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="b7ec1-122">何らかの方法で、悪意のあるコードのメモリの領域にアクセスできる場合より少なく、データを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="b7ec1-123">暗号化も機密データをシリアル化する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
-   <span data-ttu-id="b7ec1-124">**リセットしています。**</span><span class="sxs-lookup"><span data-stu-id="b7ec1-124">**Resetting.**</span></span> <span data-ttu-id="b7ec1-125">クラス、構造体、またはプロパティを定義するモジュールが終了するときに既定値または他の意味のない値に機微なデータをリセットします。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="b7ec1-126">これにより、一般的なアクセスにそのメモリ領域が解放されるとき、保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
-   <span data-ttu-id="b7ec1-127">**永続化します。**</span><span class="sxs-lookup"><span data-stu-id="b7ec1-127">**Persistence.**</span></span> <span data-ttu-id="b7ec1-128">回避する場合、ディスクなどに、機密データは保持されません。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="b7ec1-129">クリップボードには、機密データは書き込みませんも。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="b7ec1-130">`WriteOnly`修飾子は、このコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7ec1-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="b7ec1-131">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="b7ec1-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7ec1-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7ec1-132">See also</span></span>

- [<span data-ttu-id="b7ec1-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="b7ec1-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="b7ec1-134">Private</span><span class="sxs-lookup"><span data-stu-id="b7ec1-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="b7ec1-135">キーワード</span><span class="sxs-lookup"><span data-stu-id="b7ec1-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
