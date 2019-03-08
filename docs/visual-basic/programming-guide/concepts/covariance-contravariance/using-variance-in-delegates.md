---
title: デリゲート (Visual Basic) の分散の使用
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 19eb3070c1b8359a4eb050e7cf2f16622f66ebe9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679795"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="0115e-102">デリゲート (Visual Basic) の分散の使用</span><span class="sxs-lookup"><span data-stu-id="0115e-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="0115e-103">メソッドをデリゲートに割り当てると、"*共変性*" と "*反変性*" により、デリゲート型をメソッドのシグネチャに柔軟に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="0115e-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="0115e-104">共変性により、メソッドの戻り値の型の派生を、デリゲートに定義されている型よりも強くできます。</span><span class="sxs-lookup"><span data-stu-id="0115e-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="0115e-105">また、反変性により、メソッドのパラメーター型の派生をデリゲート型よりも弱くできます。</span><span class="sxs-lookup"><span data-stu-id="0115e-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="0115e-106">例 1:共変性</span><span class="sxs-lookup"><span data-stu-id="0115e-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="0115e-107">説明</span><span class="sxs-lookup"><span data-stu-id="0115e-107">Description</span></span>

<span data-ttu-id="0115e-108">この例は、デリゲート シグネチャ内の戻り値の型から派生した戻り値の型を持つメソッドで、デリゲートをどのように使用できるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0115e-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="0115e-109">`DogsHandler` が返すデータ型は `Dogs` です。これは、デリゲートに定義された `Mammals` 型の派生型です。</span><span class="sxs-lookup"><span data-stu-id="0115e-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="0115e-110">コード</span><span class="sxs-lookup"><span data-stu-id="0115e-110">Code</span></span>

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a><span data-ttu-id="0115e-111">例 2:反変性</span><span class="sxs-lookup"><span data-stu-id="0115e-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="0115e-112">説明</span><span class="sxs-lookup"><span data-stu-id="0115e-112">Description</span></span>

<span data-ttu-id="0115e-113">この例は、パラメーターの型がデリゲート シグネチャ パラメーター型の基本データ型であるメソッドで、デリゲートをどのように使用できるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0115e-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="0115e-114">反変性により、複数のハンドラーの代わりに単一のイベント ハンドラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0115e-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="0115e-115">たとえば、`EventArgs` 入力パラメーターを受け取るイベント ハンドラーを作成し、そのイベント ハンドラーを、`MouseEventArgs` 型をパラメーターとして送信する `Button.MouseClick` イベントや `KeyEventArgs` パラメーターを送信する `TextBox.KeyDown` イベントで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0115e-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>

### <a name="code"></a><span data-ttu-id="0115e-116">コード</span><span class="sxs-lookup"><span data-stu-id="0115e-116">Code</span></span>

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a><span data-ttu-id="0115e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0115e-117">See also</span></span>

- [<span data-ttu-id="0115e-118">デリゲートの分散 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0115e-118">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [<span data-ttu-id="0115e-119">Func および Action 汎用デリゲートでの分散の使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0115e-119">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
