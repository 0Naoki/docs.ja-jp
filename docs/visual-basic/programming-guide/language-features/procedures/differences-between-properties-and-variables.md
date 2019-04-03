---
title: Visual Basic のプロパティと変数の違い
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: de4800e23519c2cc1c8b2b219287b9fa018b9bbf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842903"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="1c8fe-102">Visual Basic のプロパティと変数の違い</span><span class="sxs-lookup"><span data-stu-id="1c8fe-102">Differences Between Properties and Variables in Visual Basic</span></span>
<span data-ttu-id="1c8fe-103">変数とプロパティは、アクセス可能な値を表します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-103">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="1c8fe-104">ただし、ストレージと実装の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-104">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="1c8fe-105">変数</span><span class="sxs-lookup"><span data-stu-id="1c8fe-105">Variables</span></span>  
 <span data-ttu-id="1c8fe-106">A*変数*メモリ位置に直接対応しています。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-106">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="1c8fe-107">1 つの宣言ステートメントで変数を定義するとします。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-107">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="1c8fe-108">変数、*ローカル変数*、プロシージャ内にあると、そのプロシージャ内でのみ使用可能な定義またはことができます、*メンバー変数*、いずれかの内部ではなく、モジュール、クラスまたは構造体で定義されています。プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-108">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="1c8fe-109">メンバー変数とも呼ばれますが、*フィールド*します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-109">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1c8fe-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1c8fe-110">Properties</span></span>  
 <span data-ttu-id="1c8fe-111">A*プロパティ*はモジュール、クラスまたは構造体で定義されているデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-111">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="1c8fe-112">コード ブロックの間でのプロパティを定義する、`Property`と`End Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-112">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="1c8fe-113">コード ブロックが含まれる、`Get`プロシージャ、`Set`プロシージャ、または両方。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-113">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="1c8fe-114">これらのプロシージャ*プロパティ プロシージャ*または*プロパティ アクセサー*します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-114">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="1c8fe-115">取得するか、プロパティの値を格納するだけでなく、アクセス カウンターの更新などのカスタム アクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-115">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="1c8fe-116">相違点</span><span class="sxs-lookup"><span data-stu-id="1c8fe-116">Differences</span></span>  
 <span data-ttu-id="1c8fe-117">次の表では、変数とプロパティのいくつかの重要な違いを示します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-117">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="1c8fe-118">相違点のポイント</span><span class="sxs-lookup"><span data-stu-id="1c8fe-118">Point of difference</span></span>|<span data-ttu-id="1c8fe-119">変数</span><span class="sxs-lookup"><span data-stu-id="1c8fe-119">Variable</span></span>|<span data-ttu-id="1c8fe-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1c8fe-120">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="1c8fe-121">宣言</span><span class="sxs-lookup"><span data-stu-id="1c8fe-121">Declaration</span></span>|<span data-ttu-id="1c8fe-122">1 つの宣言ステートメント</span><span class="sxs-lookup"><span data-stu-id="1c8fe-122">Single declaration statement</span></span>|<span data-ttu-id="1c8fe-123">一連のコード ブロック内のステートメント</span><span class="sxs-lookup"><span data-stu-id="1c8fe-123">Series of statements in a code block</span></span>|  
|<span data-ttu-id="1c8fe-124">実装</span><span class="sxs-lookup"><span data-stu-id="1c8fe-124">Implementation</span></span>|<span data-ttu-id="1c8fe-125">1 つのストレージの場所</span><span class="sxs-lookup"><span data-stu-id="1c8fe-125">Single storage location</span></span>|<span data-ttu-id="1c8fe-126">実行可能コード (プロパティ プロシージャ)</span><span class="sxs-lookup"><span data-stu-id="1c8fe-126">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="1c8fe-127">記憶域</span><span class="sxs-lookup"><span data-stu-id="1c8fe-127">Storage</span></span>|<span data-ttu-id="1c8fe-128">変数の値に直接関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-128">Directly associated with variable's value</span></span>|<span data-ttu-id="1c8fe-129">通常、プロパティの親クラスまたはモジュールの外部からアクセスできない内部ストレージには</span><span class="sxs-lookup"><span data-stu-id="1c8fe-129">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="1c8fe-130">プロパティの値の可能性がありますまたは格納された要素として存在していない可能性があります<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1c8fe-130">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="1c8fe-131">実行可能コード</span><span class="sxs-lookup"><span data-stu-id="1c8fe-131">Executable code</span></span>|<span data-ttu-id="1c8fe-132">なし</span><span class="sxs-lookup"><span data-stu-id="1c8fe-132">None</span></span>|<span data-ttu-id="1c8fe-133">少なくとも 1 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-133">Must have at least one procedure</span></span>|  
|<span data-ttu-id="1c8fe-134">読み取り/書き込みアクセス</span><span class="sxs-lookup"><span data-stu-id="1c8fe-134">Read and write access</span></span>|<span data-ttu-id="1c8fe-135">読み取り/書き込みまたは読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1c8fe-135">Read/write or read-only</span></span>|<span data-ttu-id="1c8fe-136">読み取り/書き込み、読み取り専用または書き込み専用</span><span class="sxs-lookup"><span data-stu-id="1c8fe-136">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="1c8fe-137">(値を返すことを許可または) に加えて、カスタム アクション</span><span class="sxs-lookup"><span data-stu-id="1c8fe-137">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="1c8fe-138">無理です</span><span class="sxs-lookup"><span data-stu-id="1c8fe-138">Not possible</span></span>|<span data-ttu-id="1c8fe-139">設定またはプロパティの値を取得するの一部として実行できます。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-139">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="1c8fe-140"><sup>1</sup>変数とは異なり、プロパティの値は 1 つの項目の記憶域に直接対応しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-140"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="1c8fe-141">記憶域を利便性またはセキュリティに部分に分割する可能性がありますか、値は、暗号化された形式で格納される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-141">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="1c8fe-142">このような場合、`Get`プロシージャはコンポーネントの編成または格納されている値の暗号化を解除し、`Set`プロシージャは新しい値を暗号化または構成の記憶域に分割することです。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-142">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="1c8fe-143">プロパティ値があります、1 日の時間などの一時的な場合、`Get`プロシージャは計算こと、実行時にプロパティにアクセスするたびにします。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-143">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c8fe-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c8fe-144">See also</span></span>

- [<span data-ttu-id="1c8fe-145">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1c8fe-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="1c8fe-146">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="1c8fe-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1c8fe-147">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="1c8fe-147">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="1c8fe-148">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="1c8fe-148">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="1c8fe-149">方法: プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-149">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="1c8fe-150">方法: 混合アクセス レベルを持つプロパティを宣言します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-150">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="1c8fe-151">方法: プロパティ プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1c8fe-151">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="1c8fe-152">方法: 宣言し、Visual Basic では、既定のプロパティを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1c8fe-152">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="1c8fe-153">方法: プロパティに値を格納します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-153">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="1c8fe-154">方法: プロパティから値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c8fe-154">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
