---
title: 列挙型を使用する状況 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: ff2d8c324aee8bbccef050c020e5392368b05b1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825106"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="841e7-102">列挙型を使用する状況 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="841e7-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="841e7-103">列挙体は、関連する定数のセットを操作する簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="841e7-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="841e7-104">列挙型で、または`Enum`一連の値のシンボリック名です。</span><span class="sxs-lookup"><span data-stu-id="841e7-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="841e7-105">列挙体は、データ型として扱われ、それらを使用して、変数とプロパティを使用するための定数のセットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="841e7-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="841e7-106">列挙型を使用する状況</span><span class="sxs-lookup"><span data-stu-id="841e7-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="841e7-107">プロシージャが限られた一連の変数を受け取ったときは、列挙体の使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="841e7-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="841e7-108">列挙体は、わかりやすい名前を使用する場合に特にわかりやすく読みやすいコードのこと。</span><span class="sxs-lookup"><span data-stu-id="841e7-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="841e7-109">列挙体を使用する利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="841e7-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="841e7-110">置き換えや数値の入力ミスによって発生したエラーを軽減します。</span><span class="sxs-lookup"><span data-stu-id="841e7-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="841e7-111">簡単に、将来の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="841e7-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="841e7-112">により、コードを読みやすくするので、そこにエラーが生じる可能性がある可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="841e7-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="841e7-113">前方の互換性を確保します。</span><span class="sxs-lookup"><span data-stu-id="841e7-113">Ensures forward compatibility.</span></span> <span data-ttu-id="841e7-114">列挙型をコードがメンバー名に対応する値が、今後だれかが変更された場合に失敗する可能性を低減します。</span><span class="sxs-lookup"><span data-stu-id="841e7-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="841e7-115">名前付けの列挙型</span><span class="sxs-lookup"><span data-stu-id="841e7-115">Naming Enumerations</span></span>  
 <span data-ttu-id="841e7-116">列挙型メンバーの名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="841e7-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="841e7-117">Visual Basic では、列挙体のメンバー名が検出されると、他の参照先のタイプ ライブラリには、同じ名前が含まれている場合に例外がスローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="841e7-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="841e7-118">アプリケーションまたはコンポーネントの値を識別する一意のプレフィックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="841e7-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="841e7-119">列挙体のメンバーを指すときにする必要があります、列挙名でメンバー名を修飾を使用してください、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="841e7-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="841e7-120">詳細については、次を参照してください。[列挙型と名前修飾](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)します。</span><span class="sxs-lookup"><span data-stu-id="841e7-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="841e7-121">定義済みの列挙型</span><span class="sxs-lookup"><span data-stu-id="841e7-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="841e7-122">Visual Basic では、多数の定義済みの列挙など`FirstDayOfWeek`と`MsgBoxResult`コードを容易にします。</span><span class="sxs-lookup"><span data-stu-id="841e7-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="841e7-123">これらの一覧については、次を参照してください。[定数と列挙体](../../../../visual-basic/language-reference/constants-and-enumerations.md)します。</span><span class="sxs-lookup"><span data-stu-id="841e7-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841e7-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="841e7-124">See also</span></span>

- [<span data-ttu-id="841e7-125">方法: 列挙体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="841e7-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="841e7-126">方法: 列挙体のメンバーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="841e7-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="841e7-127">列挙型と名前の修飾</span><span class="sxs-lookup"><span data-stu-id="841e7-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="841e7-128">方法: Visual Basic で列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="841e7-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="841e7-129">方法: 列挙値に関連付けられている文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="841e7-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="841e7-130">Enum ステートメント</span><span class="sxs-lookup"><span data-stu-id="841e7-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="841e7-131">定数と列挙体</span><span class="sxs-lookup"><span data-stu-id="841e7-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
