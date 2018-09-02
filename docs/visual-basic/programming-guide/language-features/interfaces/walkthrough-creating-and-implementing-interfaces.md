---
title: 作成するインターフェイスと実装 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: af9305deb60637b642d091501e743f2c7a57ccad
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391082"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="993eb-102">チュートリアル: インターフェイスの作成と実装 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="993eb-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="993eb-103">インターフェイスは、プロパティ、メソッド、およびイベントの特性を記述が最大構造体またはクラスの実装の詳細のままにします。</span><span class="sxs-lookup"><span data-stu-id="993eb-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="993eb-104">このチュートリアルでは、宣言およびインターフェイスを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="993eb-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="993eb-105">このチュートリアルでは、ユーザー インターフェイスを作成する方法についての情報を提供しません。</span><span class="sxs-lookup"><span data-stu-id="993eb-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="993eb-106">インターフェイスを定義するには</span><span class="sxs-lookup"><span data-stu-id="993eb-106">To define an interface</span></span>
  
1.  <span data-ttu-id="993eb-107">新しい Visual Basic Windows アプリケーション プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="993eb-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="993eb-108">新しいモジュールをクリックして、プロジェクトに追加**モジュールの追加**上、**プロジェクト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="993eb-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="993eb-109">新しいモジュールの名前を付けます`Module1.vb`クリック**追加**。</span><span class="sxs-lookup"><span data-stu-id="993eb-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="993eb-110">新しいモジュールのコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="993eb-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="993eb-111">という名前のインターフェイスを定義`TestInterface`内`Module1`」と入力して`Interface TestInterface`間、`Module`と`End Module`ステートメント、およびし、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="993eb-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="993eb-112">**コード エディター**インデント、`Interface`キーワードを追加し、`End Interface`コード ブロックを形成するステートメント。</span><span class="sxs-lookup"><span data-stu-id="993eb-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="993eb-113">間に次のコードを配置することで、プロパティ、メソッド、およびインターフェイスのイベントを定義、`Interface`と`End Interface`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="993eb-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="993eb-114">実装</span><span class="sxs-lookup"><span data-stu-id="993eb-114">Implementation</span></span>

 <span data-ttu-id="993eb-115">インターフェイス メンバーを宣言するために使用する構文はクラス メンバーを宣言するために使用する構文と異なることに注意してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="993eb-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="993eb-116">この違いは、インターフェイスが実装コードを含めることはできませんという事実を反映します。</span><span class="sxs-lookup"><span data-stu-id="993eb-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="993eb-117">インターフェイスを実装するには</span><span class="sxs-lookup"><span data-stu-id="993eb-117">To implement the interface</span></span>
  
1.  <span data-ttu-id="993eb-118">という名前のクラスを追加`ImplementationClass`次のステートメントを追加して`Module1`後に、`End Interface`ステートメントする前に、`End Module`ステートメント、および ENTER を押してします。</span><span class="sxs-lookup"><span data-stu-id="993eb-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="993eb-119">統合開発環境内で作業している場合、**コード エディター**提供、一致する`End Class`ENTER キーを押したときのステートメント。</span><span class="sxs-lookup"><span data-stu-id="993eb-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="993eb-120">次の追加`Implements`ステートメントを`ImplementationClass`クラス、インターフェイスの名前を実装します。</span><span class="sxs-lookup"><span data-stu-id="993eb-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="993eb-121">クラスまたは構造体の上部にある他の項目とは別に表示されている場合、`Implements`ステートメントでは、クラスまたは構造体がインターフェイスを実装することを示します。</span><span class="sxs-lookup"><span data-stu-id="993eb-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="993eb-122">統合開発環境内で作業している場合、**コード エディター**で必要なクラス メンバーを実装して`TestInterface`、ENTER キーを押すし、次の手順をスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="993eb-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="993eb-123">統合開発環境内で動作していない場合は、インターフェイスのすべてのメンバーを実装する必要があります`MyInterface`します。</span><span class="sxs-lookup"><span data-stu-id="993eb-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="993eb-124">次のコードを追加`ImplementationClass`を実装する`Event1`、 `Method1`、および`Prop1`:</span><span class="sxs-lookup"><span data-stu-id="993eb-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="993eb-125">`Implements`ステートメント インターフェイスおよび実装するインターフェイス メンバーの名前します。</span><span class="sxs-lookup"><span data-stu-id="993eb-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="993eb-126">定義が完了`Prop1`プロパティ値を格納するクラスにプライベート フィールドを追加することで。</span><span class="sxs-lookup"><span data-stu-id="993eb-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="993eb-127">値を返す、`pval`プロパティからアクセサーを取得します。</span><span class="sxs-lookup"><span data-stu-id="993eb-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="993eb-128">値を設定`pval`プロパティ アクセサーを設定します。</span><span class="sxs-lookup"><span data-stu-id="993eb-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  <span data-ttu-id="993eb-129">定義が完了`Method1`次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="993eb-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="993eb-130">インターフェイスの実装をテストするには</span><span class="sxs-lookup"><span data-stu-id="993eb-130">To test the implementation of the interface</span></span>
  
1.  <span data-ttu-id="993eb-131">プロジェクトのスタートアップ フォームを右クリックし、**ソリューション エクスプ ローラー**、 をクリック**コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="993eb-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="993eb-132">エディターには、スタートアップ フォームのクラスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="993eb-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="993eb-133">既定では、スタートアップ フォームと呼ばれる`Form1`します。</span><span class="sxs-lookup"><span data-stu-id="993eb-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="993eb-134">次の追加`testInstance`フィールドを`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="993eb-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="993eb-135">宣言することで`testInstance`として`WithEvents`、`Form1`クラスは、そのイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="993eb-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="993eb-136">次のイベント ハンドラーを追加、`Form1`によって生成されるイベントを処理するクラスを`testInstance`:</span><span class="sxs-lookup"><span data-stu-id="993eb-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  <span data-ttu-id="993eb-137">という名前のサブルーチンを追加`Test`を`Form1`実装クラスをテストするクラス。</span><span class="sxs-lookup"><span data-stu-id="993eb-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="993eb-138">`Test`プロシージャは、実装するクラスのインスタンスを作成します。 `MyInterface`、そのインスタンスを割り当てます、`testInstance`フィールド、プロパティの設定およびインターフェイスを通じたメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="993eb-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="993eb-139">呼び出すコードを追加、`Test`プロシージャから、`Form1 Load`スタートアップ フォームの手順。</span><span class="sxs-lookup"><span data-stu-id="993eb-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  <span data-ttu-id="993eb-140">実行、 `Test` f5 キーを押してプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="993eb-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="993eb-141">メッセージ"Prop1 が 9 に設定"が表示されます。</span><span class="sxs-lookup"><span data-stu-id="993eb-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="993eb-142">クリックした後、メッセージ"Method1 の X パラメーター is 5"が表示されます。</span><span class="sxs-lookup"><span data-stu-id="993eb-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="993eb-143">[Ok] をクリックして、「イベント ハンドラーが、イベントが発生しました」のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="993eb-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="993eb-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="993eb-144">See also</span></span>

 [<span data-ttu-id="993eb-145">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="993eb-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="993eb-146">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="993eb-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [<span data-ttu-id="993eb-147">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="993eb-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="993eb-148">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="993eb-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)  