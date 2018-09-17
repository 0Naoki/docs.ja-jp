---
title: Visual Studio 2017 での .NET Standard ライブラリの使用
description: Visual Studio 2017 でクラス ライブラリのメンバーを呼び出す方法について説明します。
author: BillWagner
ms.author: wiwagn
ms.date: 06/05/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 52ec46c23bb928b49f034270ed1d510d1acf992e
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45518166"
---
# <a name="consuming-a-net-standard-library-in-visual-studio-2017"></a><span data-ttu-id="3b3cb-103">Visual Studio 2017 での .NET Standard ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="3b3cb-103">Consuming a .NET Standard library in Visual Studio 2017</span></span>

<span data-ttu-id="3b3cb-104">「[Visual Studio 2017 での C# と .NET Core を使用したクラス ライブラリの構築](./library-with-visual-studio.md)」または「[Visual Studio 2017 で Visual Basic と .NET Core を使用したクラス ライブラリの構築](vb-library-with-visual-studio.md)」の手順で .NET Standard クラス ライブラリを作成し、「[Visual Studio 2017 の .NET Core を使用したクラス ライブラリのテスト](testing-library-with-visual-studio.md)」でそれをテストし、ライブラリのリリース バージョンをビルドしたら、次の手順は、呼び出し元がそれを利用できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-104">Once you've created a .NET Standard class library by following the steps in [Building a C# class library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) or [Building a Visual Basic class library with .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), tested it in [Testing a class library with .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md), and built a Release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="3b3cb-105">これは次の 2 つの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-105">You can do this in two ways:</span></span>

* <span data-ttu-id="3b3cb-106">ライブラリが 1 つのソリューションで使われる場合 (たとえば、1 つの大規模なアプリケーションのコンポーネントである場合)、1 つのプロジェクトとしてソリューションに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>

* <span data-ttu-id="3b3cb-107">ライブラリが一般に公開されている場合は、NuGet パッケージとして配布できます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-107">If the library will be generally accessible, you can distribute it as a NuGet package.</span></span>

## <a name="including-a-library-as-a-project-in-a-solution"></a><span data-ttu-id="3b3cb-108">ソリューション内のプロジェクトとしてライブラリを含める</span><span class="sxs-lookup"><span data-stu-id="3b3cb-108">Including a library as a project in a solution</span></span>

<span data-ttu-id="3b3cb-109">単体テストをクラス ライブラリと同じソリューションに含めたのと同様に、アプリケーションをソリューションの一部として含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-109">Just as you included unit tests in the same solution as your class library, you can include your application as part of that solution.</span></span> <span data-ttu-id="3b3cb-110">たとえば、文字列を入力するようにユーザーに要求して、最初の文字が大文字かどうかを報告するコンソール アプリケーションで、このクラス ライブラリを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-110">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="3b3cb-111">C#</span><span class="sxs-lookup"><span data-stu-id="3b3cb-111">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="3b3cb-112">「[Visual Studio 2017 での C# と .NET Core を使用したクラス ライブラリの構築](./library-with-visual-studio.md)」トピックで作成した `ClassLibraryProjects` ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-112">Open the `ClassLibraryProjects` solution you created in the [Building a C# Class Library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="3b3cb-113">**ソリューション エクスプローラー**で **ClassLibraryProjects** ソリューションを右クリックし、コンテキスト メニューから **[追加]** > **[新しいプロジェクト]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-113">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="3b3cb-114">**[新しいプロジェクトの追加]** ダイアログで、**[Visual C#]** ノードを展開し、**[.NET Core]** ノードを選択し、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-114">In the **Add New Project** dialog, expand the **Visual C#** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="3b3cb-115">**[名前]** テキスト ボックスに「ShowCase」と入力し、**[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-115">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![[新しいプロジェクトの追加] ダイアログ](./media/consuming-library-with-visual-studio/addnewproject.png)

1. <span data-ttu-id="3b3cb-117">**ソリューション エクスプローラー**で、**ShowCase** プロジェクトを右クリックして、コンテキスト メニューで **[スタートアップ プロジェクトに設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-117">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span> 

   ![ShowCase のコンテキスト メニュー](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. <span data-ttu-id="3b3cb-119">初期状態では、プロジェクトにはクラス ライブラリへのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-119">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="3b3cb-120">プロジェクトでクラス ライブラリのメソッドを呼び出すことができるようにするには、クラス ライブラリへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-120">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="3b3cb-121">**ソリューション エクスプローラー**で、`ShowCase` プロジェクトの **[依存関係]** ノードを右クリックして、**[参照の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-121">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![ShowCase の依存関係のコンテキスト メニュー](./media/consuming-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="3b3cb-123">**[参照マネージャー]** ダイアログ ボックスで、クラス ライブラリ プロジェクト **StringLibrary** を選び、**[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-123">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![参照マネージャー](./media/consuming-library-with-visual-studio/referencemanager.png)

1. <span data-ttu-id="3b3cb-125">*Program.cs* ファイルのコード ウィンドウで、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-125">In the code window for the *Program.cs* file, replace all of the code with the following code:</span></span>

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   <span data-ttu-id="3b3cb-126">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-126">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="3b3cb-127">この変数が 25 以上であるときは、コードは常にコンソール ウィンドウをクリアして、ユーザーにメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-127">Whenever it is greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="3b3cb-128">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="3b3cb-128">The program prompts the user to enter a string.</span></span> <span data-ttu-id="3b3cb-129">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-129">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="3b3cb-130">ユーザーが文字列を入力せずに Enter キーを押すと、アプリケーションは終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-130">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="3b3cb-131">必要に応じて、ツールバーを変更して、`ShowCase` プロジェクトの**デバッグ** リリースをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-131">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="3b3cb-132">**ShowCase** の緑色の矢印を選び、プログラムをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-132">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![イメージ](./media/consuming-library-with-visual-studio/toolbar.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="3b3cb-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3b3cb-134">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="3b3cb-135">「[Visual Studio 2017 で Visual Basic と .NET Core を使用したクラス ライブラリの構築](vb-library-with-visual-studio.md)」トピックで作成した `ClassLibraryProjects` ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-135">Open the `ClassLibraryProjects` solution you created in the [Building a class Library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="3b3cb-136">**ソリューション エクスプローラー**で **ClassLibraryProjects** ソリューションを右クリックし、コンテキスト メニューから **[追加]** > **[新しいプロジェクト]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-136">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="3b3cb-137">**[新しいプロジェクトの追加]** ダイアログで、**[Visual Basic]** ノードを展開し、**[.NET Core]** ノードを選択し、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-137">In the **Add New Project** dialog, expand the **Visual Basic** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="3b3cb-138">**[名前]** テキスト ボックスに「ShowCase」と入力し、**[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-138">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![[新しいプロジェクトの追加] ダイアログ](./media/consuming-library-with-visual-studio/vb-addnewproject.png)

1. <span data-ttu-id="3b3cb-140">**ソリューション エクスプローラー**で、**ShowCase** プロジェクトを右クリックして、コンテキスト メニューで **[スタートアップ プロジェクトに設定]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-140">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span> 

   ![ShowCase のコンテキスト メニュー](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. <span data-ttu-id="3b3cb-142">初期状態では、プロジェクトにはクラス ライブラリへのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-142">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="3b3cb-143">プロジェクトでクラス ライブラリのメソッドを呼び出すことができるようにするには、クラス ライブラリへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-143">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="3b3cb-144">**ソリューション エクスプローラー**で、`ShowCase` プロジェクトの **[依存関係]** ノードを右クリックして、**[参照の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-144">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![ShowCase の依存関係のコンテキスト メニュー](./media/consuming-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="3b3cb-146">**[参照マネージャー]** ダイアログ ボックスで、クラス ライブラリ プロジェクト **StringLibrary** を選び、**[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-146">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![参照マネージャー](./media/consuming-library-with-visual-studio/referencemanager.png)

1. <span data-ttu-id="3b3cb-148">*Program.vb* ファイルのコード ウィンドウで、すべてのコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-148">In the code window for the *Program.vb* file, replace all of the code with the following code:</span></span>

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="3b3cb-149">このコードでは、`row` 変数を使って、コンソール ウィンドウに書き込まれるデータの行数のカウントを維持します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-149">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="3b3cb-150">この変数が 25 以上であるときは、コードは常にコンソール ウィンドウをクリアして、ユーザーにメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-150">Whenever it is greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="3b3cb-151">プログラムは、ユーザーに文字列の入力を要求し、</span><span class="sxs-lookup"><span data-stu-id="3b3cb-151">The program prompts the user to enter a string.</span></span> <span data-ttu-id="3b3cb-152">文字列が大文字で始まるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-152">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="3b3cb-153">ユーザーが文字列を入力せずに Enter キーを押すと、アプリケーションは終了し、コンソール ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-153">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="3b3cb-154">必要に応じて、ツールバーを変更して、`ShowCase` プロジェクトの**デバッグ** リリースをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-154">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="3b3cb-155">**ShowCase** の緑色の矢印を選び、プログラムをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-155">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![イメージ](./media/consuming-library-with-visual-studio/toolbar.png)
---

<span data-ttu-id="3b3cb-157">「[Visual Studio 2017 で Hello World Application をデバッグする](debugging-with-visual-studio.md)」と「[Visual Studio 2017 を使用した Hello World アプリケーションの発行](publishing-with-visual-studio.md)」の手順に従って、このライブラリを使うアプリケーションをデバッグして発行できます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-157">You can debug and publish the application that uses this library by following the steps in [Debugging your Hello World application with Visual Studio 2017](debugging-with-visual-studio.md) and [Publishing your Hello World Application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="distributing-the-library-in-a-nuget-package"></a><span data-ttu-id="3b3cb-158">ライブラリを NuGet パッケージで配布する</span><span class="sxs-lookup"><span data-stu-id="3b3cb-158">Distributing the library in a NuGet package</span></span>

<span data-ttu-id="3b3cb-159">NuGet パッケージとして発行すると、クラス ライブラリが広く利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-159">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="3b3cb-160">NuGet パッケージの作成は Visual Studio ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-160">Visual Studio does not support the creation of NuGet packages.</span></span> <span data-ttu-id="3b3cb-161">作成するには、[`dotnet` コマンド ライン ユーティリティ](../../core/tools/dotnet.md)を使います。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-161">To create one, you use the [`dotnet` command line utility](../../core/tools/dotnet.md):</span></span>

1. <span data-ttu-id="3b3cb-162">コンソール ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-162">Open a console window.</span></span> <span data-ttu-id="3b3cb-163">たとえば、Windows タスク バーの **[何でも聞いてください]** テキスト ボックスに「`Command Prompt`」 (または省略して「`cmd`」) と入力し、**コマンド プロンプト** デスクトップ アプリを選ぶか、コマンド プロンプトが検索結果で選択されている場合は Enter キーを押して、コンソール ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-163">For example in the **Ask me anything** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="3b3cb-164">ライブラリのプロジェクト ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-164">Navigate to your library's project directory.</span></span> <span data-ttu-id="3b3cb-165">一般的なファイルの場所を再構成していない限り、*Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary* ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-165">Unless you've reconfigured the typical file location, it's in the *Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary* directory.</span></span> <span data-ttu-id="3b3cb-166">このディレクトリには、ソース コードおよびプロジェクト ファイル *StringLibrary.csproj* が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-166">The directory contains your source code and a project file, *StringLibrary.csproj*.</span></span>

1. <span data-ttu-id="3b3cb-167">`dotnet pack --no-build` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-167">Issue the command `dotnet pack --no-build`.</span></span> <span data-ttu-id="3b3cb-168">`dotnet` ユーティリティにより、*.nupkg* 拡張子を持つパッケージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-168">The `dotnet` utility generates a package with a *.nupkg* extension.</span></span>

   > [!TIP]
   > <span data-ttu-id="3b3cb-169">*dotnet.exe* を含むディレクトリが PATH になくても、コンソール ウィンドウで「`where dotnet.exe`」と入力して、場所を検索できます。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-169">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="3b3cb-170">NuGet パッケージの作成の詳細については、「[クロスプラットフォーム ツールを使用して NuGet パッケージを作成する方法](../../core/deploying/creating-nuget-packages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b3cb-170">For more information on creating NuGet packages, see [How to Create a NuGet Package with Cross Platform Tools](../../core/deploying/creating-nuget-packages.md).</span></span>
