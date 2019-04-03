---
title: '方法: 長い修飾パス (Visual Basic) のオブジェクトへのアクセスを高速化します。'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: b10876c22d2f6dd5832baa0d498db7c4205a3fcb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816292"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="77c66-102">方法: 長い修飾パス (Visual Basic) のオブジェクトへのアクセスを高速化します。</span><span class="sxs-lookup"><span data-stu-id="77c66-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="77c66-103">いくつかのメソッドとプロパティの修飾パスを必要とするオブジェクトを頻繁にアクセスする場合は、修飾パスを繰り返さないこと、コードを短縮できます。</span><span class="sxs-lookup"><span data-stu-id="77c66-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="77c66-104">修飾パスの繰り返しを回避できます 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="77c66-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="77c66-105">オブジェクトを変数に割り当てることができますかで使用できる、 `With`.`End With`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="77c66-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="77c66-106">高速化するアクセス頻度の高い修飾オブジェクトを変数に代入することで</span><span class="sxs-lookup"><span data-stu-id="77c66-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="77c66-107">頻繁にアクセスしているオブジェクトの型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="77c66-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="77c66-108">宣言の初期化の部分で修飾パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="77c66-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="77c66-109">オブジェクトのメンバーにアクセスするのにには、変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="77c66-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="77c66-110">高速化するアクセス頻度の高い修飾オブジェクトに、With を使用しています.End With ブロック</span><span class="sxs-lookup"><span data-stu-id="77c66-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="77c66-111">修飾パスを配置、`With`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="77c66-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="77c66-112">内のオブジェクトのメンバーにアクセス、`With`前に、ブロック、`End With`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="77c66-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="77c66-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="77c66-113">See also</span></span>

- [<span data-ttu-id="77c66-114">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="77c66-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="77c66-115">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="77c66-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
