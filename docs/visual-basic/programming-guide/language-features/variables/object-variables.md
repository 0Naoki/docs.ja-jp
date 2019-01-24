---
title: Visual Basic におけるオブジェクト変数
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 046119664fc0277a6a5305d0cf086b4438b13f9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685465"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="1c4c7-102">Visual Basic におけるオブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="1c4c7-102">Object Variables in Visual Basic</span></span>
<span data-ttu-id="1c4c7-103">値を直接格納するだけでなく、変数は、オブジェクトを参照できます。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="1c4c7-104">同じ理由から、変数に任意の値を代入するには、変数にオブジェクトを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>  
  
-   <span data-ttu-id="1c4c7-105">変数名は、多くの場合、短くしてメソッドと、オブジェクト自体へのアクセスに必要なプロパティの完全なパスよりも覚えやすくします。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>  
  
-   <span data-ttu-id="1c4c7-106">オブジェクトを参照する変数を使用するは、必要なメソッドやプロパティを使って繰り返しオブジェクト自体へのアクセスよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>  
  
-   <span data-ttu-id="1c4c7-107">コードの実行中に他のオブジェクトを参照する変数を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-107">You can change a variable to refer to other objects while your code is running.</span></span>  
  
## <a name="making-code-shorter"></a><span data-ttu-id="1c4c7-108">コードを短く</span><span class="sxs-lookup"><span data-stu-id="1c4c7-108">Making Code Shorter</span></span>  
 <span data-ttu-id="1c4c7-109">オブジェクト変数を使用すると、入力するのに必要がコードを短きます。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="1c4c7-110">次の例では、メソッドとプロパティの完全なパスを使用して、アクセスする、<xref:System.Windows.Forms.Control>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 <span data-ttu-id="1c4c7-111">このコードを短くし、コントロールのオブジェクト変数を使用する場合は、実行を高速化できます。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="1c4c7-112">割り当てる特定のクラスでオブジェクト変数を宣言する必要があります (`Control`この場合)。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="1c4c7-113">オブジェクトを変数に代入すると参照するオブジェクトを扱うときとまったく同じように扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="1c4c7-114">設定またはオブジェクトのプロパティを取得またはそのメソッドのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="1c4c7-115">次の例では、オブジェクト変数を使用して、前の例のコードを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c4c7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c4c7-116">See also</span></span>
- [<span data-ttu-id="1c4c7-117">変数宣言</span><span class="sxs-lookup"><span data-stu-id="1c4c7-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="1c4c7-118">方法: 長い修飾パスを持つオブジェクトへのアクセスを高速化します。</span><span class="sxs-lookup"><span data-stu-id="1c4c7-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="1c4c7-119">オブジェクト変数の宣言</span><span class="sxs-lookup"><span data-stu-id="1c4c7-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="1c4c7-120">オブジェクト変数の代入</span><span class="sxs-lookup"><span data-stu-id="1c4c7-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="1c4c7-121">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="1c4c7-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
