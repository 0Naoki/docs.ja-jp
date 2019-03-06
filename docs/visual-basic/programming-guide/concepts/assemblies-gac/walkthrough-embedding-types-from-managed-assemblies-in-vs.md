---
title: 'チュートリアル: Visual Studio (Visual Basic) でマネージ アセンブリから型を埋め込む'
ms.date: 07/20/2015
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
ms.openlocfilehash: 836d035aab06f18c13e3675fbd72c5ab9879a3d2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359464"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="19fa7-102">チュートリアル: Visual Studio (Visual Basic) でマネージ アセンブリから型を埋め込む</span><span class="sxs-lookup"><span data-stu-id="19fa7-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="19fa7-103">厳密な名前を持つマネージド アセンブリから型情報を埋め込むと、アプリケーション内で型を疎結合して、バージョンに依存しないプログラムを実現できます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="19fa7-104">つまり、各バージョン用の再コンパイルを必要とすることなく、マネージド ライブラリの複数のバージョンから型を使用するプログラムを記述できます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>

<span data-ttu-id="19fa7-105">型の埋め込みは、COM 相互運用と共によく使用されます (Microsoft Office からのオートメーション オブジェクトを使用するアプリケーションなど)。</span><span class="sxs-lookup"><span data-stu-id="19fa7-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="19fa7-106">型情報を埋め込むと、同じビルドのプログラムを、別のコンピューター上にある別バージョンの Microsoft Office と連携させることができます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="19fa7-107">ただし、型の埋め込みはフル マネージド ソリューションと共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-107">However, you can also use type embedding with a fully managed solution.</span></span>

<span data-ttu-id="19fa7-108">型情報は、次の特性を持つアセンブリから埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>

- <span data-ttu-id="19fa7-109">アセンブリが、少なくとも 1 つのパブリック インターフェイスを公開している。</span><span class="sxs-lookup"><span data-stu-id="19fa7-109">The assembly exposes at least one public interface.</span></span>

- <span data-ttu-id="19fa7-110">埋め込みインターフェイスに `ComImport` 属性と `Guid` 属性 (および一意の GUID) が付けられている。</span><span class="sxs-lookup"><span data-stu-id="19fa7-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>

- <span data-ttu-id="19fa7-111">アセンブリに、`ImportedFromTypeLib` 属性または `PrimaryInteropAssembly` 属性、およびアセンブリ レベルの `Guid` 属性が付けられている。</span><span class="sxs-lookup"><span data-stu-id="19fa7-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="19fa7-112">(既定では、Visual Basic プロジェクト テンプレートに含めるアセンブリ レベル`Guid`属性)。</span><span class="sxs-lookup"><span data-stu-id="19fa7-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>

<span data-ttu-id="19fa7-113">埋め込み可能なパブリック インターフェイスを指定したら、それらのインターフェイスを実装するランタイム クラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="19fa7-114">その後、クライアント プログラムは、パブリック インターフェイスを含んだアセンブリを参照し、参照の `Embed Interop Types` プロパティを `True` に設定することで、デザイン時にそれらのインターフェイスの型情報を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="19fa7-115">これは、コマンド ライン コンパイラを使用し、`/link` コンパイラ オプションを使用してアセンブリを参照することに相当します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="19fa7-116">クライアント プログラムはその後、それらのインターフェイスとして型指定されたランタイム オブジェクトのインスタンスを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="19fa7-117">厳密な名前を持つランタイム アセンブリの新バージョンを作成した場合、クライアント プログラムを、更新後のランタイム アセンブリで再コンパイルする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="19fa7-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="19fa7-118">クライアント プログラムでは、パブリック インターフェイスの埋め込み型情報を使用して、利用可能なバージョンをどちらでも引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="19fa7-119">型埋め込みの主な機能は、COM 相互運用アセンブリからの型情報の埋め込みをサポートすることなので、フル マネージドのソリューションで型情報を埋め込む場合には、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>

- <span data-ttu-id="19fa7-120">COM 相互運用に固有の属性のみが埋め込まれます。その他の属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>

- <span data-ttu-id="19fa7-121">型がジェネリック パラメーターを使用していて、ジェネリック パラメーターの型が埋め込み型である場合、その型はアセンブリの境界を越えて使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="19fa7-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="19fa7-122">アセンブリの境界を越える場合の例としては、別のアセンブリからメソッドを呼び出す場合や、別のアセンブリで定義されている型から型を派生させる場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>

- <span data-ttu-id="19fa7-123">定数は埋め込まれません。</span><span class="sxs-lookup"><span data-stu-id="19fa7-123">Constants are not embedded.</span></span>

- <span data-ttu-id="19fa7-124"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> クラスでは、埋め込み型をキーとして利用できません。</span><span class="sxs-lookup"><span data-stu-id="19fa7-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="19fa7-125">埋め込み型をキーとしてサポートするために、独自のディクショナリ型を実装することは可能です。</span><span class="sxs-lookup"><span data-stu-id="19fa7-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>

 <span data-ttu-id="19fa7-126">このチュートリアルでは、次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="19fa7-126">In this walkthrough, you will do the following:</span></span>

- <span data-ttu-id="19fa7-127">埋め込み可能な型情報を含んだパブリック インターフェイスを持つ、厳密な名前付きのアセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="19fa7-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>

- <span data-ttu-id="19fa7-128">そのパブリック インターフェイスを実装する、厳密な名前付きのランタイム アセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="19fa7-128">Create a strong-named runtime assembly that implements that public interface.</span></span>

- <span data-ttu-id="19fa7-129">パブリック インターフェイスから型情報を埋め込み、ランタイム アセンブリからクラスのインスタンスを作成する、クライアント プログラムを作成する。</span><span class="sxs-lookup"><span data-stu-id="19fa7-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>

- <span data-ttu-id="19fa7-130">ランタイム アセンブリを変更し、リビルドする。</span><span class="sxs-lookup"><span data-stu-id="19fa7-130">Modify and rebuild the runtime assembly.</span></span>

- <span data-ttu-id="19fa7-131">クライアント プログラムを実行して、新バージョンのランタイム アセンブリが、クライアント プログラムを再コンパイルしなくても使用されていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="19fa7-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-an-interface"></a><span data-ttu-id="19fa7-132">インターフェイスの作成</span><span class="sxs-lookup"><span data-stu-id="19fa7-132">Creating an Interface</span></span>

#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="19fa7-133">型等価性インターフェイス プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="19fa7-133">To create the type equivalence interface project</span></span>

1. <span data-ttu-id="19fa7-134">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="19fa7-135">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、**[Windows]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="19fa7-136">**[テンプレート]** ペインで **[クラス ライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="19fa7-137">**[名前]** ボックスに `TypeEquivalenceInterface` と入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="19fa7-138">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-138">The new project is created.</span></span>

3. <span data-ttu-id="19fa7-139">**ソリューション エクスプ ローラー**Class1.vb ファイルを右クリックし、クリックして、**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="19fa7-140">ファイルの名前を `ISampleInterface.vb` に変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="19fa7-141">ファイルの名前を変更すると、クラスの名前も `ISampleInterface` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="19fa7-142">このクラスは、クラスのパブリック インターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-142">This class will represent the public interface for the class.</span></span>

4. <span data-ttu-id="19fa7-143">TypeEquivalenceInterface プロジェクトを右クリックし、**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="19fa7-144">**[コンパイル]** タブをクリックします。開発用コンピューター上の有効な場所への出力パスを設定します (`C:\TypeEquivalenceSample` など)。</span><span class="sxs-lookup"><span data-stu-id="19fa7-144">Click the **Compile** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="19fa7-145">この場所は、このチュートリアルの後の手順でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-145">This location will also be used in a later step in this walkthrough.</span></span>

5. <span data-ttu-id="19fa7-146">プロジェクト プロパティの編集を続けたまま、**[署名]** タブをクリックします。**[アセンブリの署名]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="19fa7-147">**[厳密な名前のキー ファイルを選択してください]** ボックスの一覧で **[<新規作成...>]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="19fa7-148">**[キー ファイル名]** ボックスに、「`key.snk`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="19fa7-149">**[キーファイルをパスワードで保護する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="19fa7-150">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-150">Click **OK**.</span></span>

6. <span data-ttu-id="19fa7-151">ISampleInterface.vb ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-151">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="19fa7-152">ISampleInterface クラス ファイルに、ISampleInterface インターフェイスを作成するための次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>

    ```vb
    Imports System.Runtime.InteropServices

    <ComImport()>
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
    Public Interface ISampleInterface
        Sub GetUserInput()
        ReadOnly Property UserInput As String
    End Interface
    ```

7. <span data-ttu-id="19fa7-153">**[ツール]** メニューの **[GUID の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="19fa7-154">**[GUID の作成]** ダイアログ ボックスで、**[レジストリ形式]** をクリックし、**[コピー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="19fa7-155">**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-155">Click **Exit**.</span></span>

8. <span data-ttu-id="19fa7-156">`Guid` 属性で、サンプルの GUID を削除し、**[GUID の作成]** ダイアログ ボックスからコピーした GUID を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="19fa7-157">コピーした GUID から中かっこ ({}) を削除します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-157">Remove the braces ({}) from the copied GUID.</span></span>

9. <span data-ttu-id="19fa7-158">**[プロジェクト]** メニューの **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-158">On the **Project** menu, click **Show All Files**.</span></span>

10. <span data-ttu-id="19fa7-159">**ソリューション エクスプ ローラー**、展開、 **My Project**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="19fa7-159">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="19fa7-160">AssemblyInfo.vb をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-160">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="19fa7-161">ファイルに次の属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-161">Add the following attribute to the file.</span></span>

    ```vb
    <Assembly: ImportedFromTypeLib("")>
    ```

    <span data-ttu-id="19fa7-162">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-162">Save the file.</span></span>

11. <span data-ttu-id="19fa7-163">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-163">Save the project.</span></span>

12. <span data-ttu-id="19fa7-164">TypeEquivalenceInterface プロジェクトを右クリックし、**[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-164">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="19fa7-165">クラス ライブラリの .dll ファイルがコンパイルされ、指定したビルド出力パス (たとえば、C:\TypeEquivalenceSample) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-165">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="creating-a-runtime-class"></a><span data-ttu-id="19fa7-166">ランタイム クラスの作成</span><span class="sxs-lookup"><span data-stu-id="19fa7-166">Creating a Runtime Class</span></span>

#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="19fa7-167">型等価性ランタイム プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="19fa7-167">To create the type equivalence runtime project</span></span>

1. <span data-ttu-id="19fa7-168">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-168">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="19fa7-169">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、**[Windows]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-169">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="19fa7-170">**[テンプレート]** ペインで **[クラス ライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-170">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="19fa7-171">**[名前]** ボックスに `TypeEquivalenceRuntime` と入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-171">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="19fa7-172">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-172">The new project is created.</span></span>

3. <span data-ttu-id="19fa7-173">**ソリューション エクスプ ローラー**Class1.vb ファイルを右クリックし、クリックして、**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-173">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="19fa7-174">ファイルの名前を `SampleClass.vb` に変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-174">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="19fa7-175">ファイルの名前を変更すると、クラスの名前も `SampleClass` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-175">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="19fa7-176">このクラスが `ISampleInterface` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-176">This class will implement the `ISampleInterface` interface.</span></span>

4. <span data-ttu-id="19fa7-177">TypeEquivalenceRuntime プロジェクトを右クリックし、**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-177">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="19fa7-178">**[コンパイル]** タブをクリックします。出力パスを、TypeEquivalenceInterface プロジェクトで使用したのと同じ場所に設定します (たとえば、`C:\TypeEquivalenceSample`)。</span><span class="sxs-lookup"><span data-stu-id="19fa7-178">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>

5. <span data-ttu-id="19fa7-179">プロジェクト プロパティの編集を続けたまま、**[署名]** タブをクリックします。**[アセンブリの署名]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-179">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="19fa7-180">**[厳密な名前のキー ファイルを選択してください]** ボックスの一覧で **[<新規作成...>]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-180">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="19fa7-181">**[キー ファイル名]** ボックスに、「`key.snk`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-181">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="19fa7-182">**[キーファイルをパスワードで保護する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-182">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="19fa7-183">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-183">Click **OK**.</span></span>

6. <span data-ttu-id="19fa7-184">TypeEquivalenceRuntime プロジェクトを右クリックし、**[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-184">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="19fa7-185">**[参照]** タブをクリックし、出力パスのフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-185">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="19fa7-186">TypeEquivalenceInterface.dll ファイルを選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-186">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>

7. <span data-ttu-id="19fa7-187">**[プロジェクト]** メニューの **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-187">On the **Project** menu, click **Show All Files**.</span></span>

8. <span data-ttu-id="19fa7-188">**ソリューション エクスプローラー**で、**[参照]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-188">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="19fa7-189">TypeEquivalenceInterface 参照を選択します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-189">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="19fa7-190">TypeEquivalenceInterface 参照の [プロパティ] ウィンドウで、**[特定バージョン]** プロパティを **[False]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-190">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>

9. <span data-ttu-id="19fa7-191">SampleClass クラス ファイルに、SampleClass クラスを作成するための次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-191">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>

    ```vb
    Imports TypeEquivalenceInterface

    Public Class SampleClass
        Implements ISampleInterface

        Private p_UserInput As String
        Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
            Get
                Return p_UserInput
            End Get
        End Property

        Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
            Console.WriteLine("Please enter a value:")
            p_UserInput = Console.ReadLine()
        End Sub
    End Class
    ```

10. <span data-ttu-id="19fa7-192">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-192">Save the project.</span></span>

11. <span data-ttu-id="19fa7-193">TypeEquivalenceRuntime プロジェクトを右クリックし、**[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-193">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="19fa7-194">クラス ライブラリの .dll ファイルがコンパイルされ、指定したビルド出力パス (たとえば、C:\TypeEquivalenceSample) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-194">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="creating-a-client-project"></a><span data-ttu-id="19fa7-195">クライアント プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="19fa7-195">Creating a Client Project</span></span>

#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="19fa7-196">型等価性クライアント プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="19fa7-196">To create the type equivalence client project</span></span>

1. <span data-ttu-id="19fa7-197">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-197">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="19fa7-198">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、**[Windows]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-198">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="19fa7-199">**[テンプレート]** ペインの **[コンソール アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-199">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="19fa7-200">**[名前]** ボックスに `TypeEquivalenceClient` と入力して、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-200">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="19fa7-201">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-201">The new project is created.</span></span>

3. <span data-ttu-id="19fa7-202">TypeEquivalenceClient プロジェクトを右クリックし、**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-202">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="19fa7-203">**[コンパイル]** タブをクリックします。出力パスを、TypeEquivalenceInterface プロジェクトで使用したのと同じ場所に設定します (たとえば、`C:\TypeEquivalenceSample`)。</span><span class="sxs-lookup"><span data-stu-id="19fa7-203">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>

4. <span data-ttu-id="19fa7-204">TypeEquivalenceClient プロジェクトを右クリックし、**[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-204">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="19fa7-205">**[参照]** タブをクリックし、出力パスのフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-205">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="19fa7-206">TypeEquivalenceInterface.dll ファイル (TypeEquivalenceRuntime.dll ではない) を選択し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-206">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>

5. <span data-ttu-id="19fa7-207">**[プロジェクト]** メニューの **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-207">On the **Project** menu, click **Show All Files**.</span></span>

6. <span data-ttu-id="19fa7-208">**ソリューション エクスプローラー**で、**[参照]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-208">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="19fa7-209">TypeEquivalenceInterface 参照を選択します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-209">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="19fa7-210">TypeEquivalenceInterface 参照の [プロパティ] ウィンドウで、**[相互運用型の埋め込み]** プロパティを **[True]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-210">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>

7. <span data-ttu-id="19fa7-211">Module1.vb ファイルをクライアント プログラムを作成するには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-211">Add the following code to the Module1.vb file to create the client program.</span></span>

    ```vb
    Imports TypeEquivalenceInterface
    Imports System.Reflection

    Module Module1

        Sub Main()
            Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
            Dim sampleClass As ISampleInterface = CType( _
                sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
            sampleClass.GetUserInput()
            Console.WriteLine(sampleClass.UserInput)
            Console.WriteLine(sampleAssembly.GetName().Version)
            Console.ReadLine()
        End Sub

    End Module
    ```

8. <span data-ttu-id="19fa7-212">Ctrl キーを押しながら F5 キーを押して、プログラムをビルドおよび実行します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-212">Press CTRL+F5 to build and run the program.</span></span>

## <a name="modifying-the-interface"></a><span data-ttu-id="19fa7-213">インターフェイスの変更</span><span class="sxs-lookup"><span data-stu-id="19fa7-213">Modifying the Interface</span></span>

#### <a name="to-modify-the-interface"></a><span data-ttu-id="19fa7-214">インターフェイスを変更するには</span><span class="sxs-lookup"><span data-stu-id="19fa7-214">To modify the interface</span></span>

1. <span data-ttu-id="19fa7-215">Visual Studio で、**[ファイル]** メニューの **[開く]** をポイントし、**[プロジェクト/ソリューション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-215">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>

2. <span data-ttu-id="19fa7-216">**[プロジェクトを開く]** ダイアログ ボックスで、TypeEquivalenceInterface プロジェクトを右クリックし、**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-216">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="19fa7-217">**[アプリケーション]** タブをクリックします。**[アセンブリ情報]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-217">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="19fa7-218">**[アセンブリ バージョン]** と **[ファイル バージョン]** の値を `2.0.0.0` に変更します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-218">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>

3. <span data-ttu-id="19fa7-219">ISampleInterface.vb ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-219">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="19fa7-220">ISampleInterface インターフェイスに、次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-220">Add the following line of code to the ISampleInterface interface.</span></span>

    ```vb
    Function GetDate() As Date
    ```

    <span data-ttu-id="19fa7-221">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-221">Save the file.</span></span>

4. <span data-ttu-id="19fa7-222">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-222">Save the project.</span></span>

5. <span data-ttu-id="19fa7-223">TypeEquivalenceInterface プロジェクトを右クリックし、**[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-223">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="19fa7-224">クラス ライブラリ .dll ファイルの新バージョンがコンパイルされ、指定したビルド出力パス (たとえば、C:\TypeEquivalenceSample) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-224">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="modifying-the-runtime-class"></a><span data-ttu-id="19fa7-225">ランタイム クラスの変更</span><span class="sxs-lookup"><span data-stu-id="19fa7-225">Modifying the Runtime Class</span></span>

#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="19fa7-226">ランタイム クラスを変更するには</span><span class="sxs-lookup"><span data-stu-id="19fa7-226">To modify the runtime class</span></span>

1. <span data-ttu-id="19fa7-227">Visual Studio で、**[ファイル]** メニューの **[開く]** をポイントし、**[プロジェクト/ソリューション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-227">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>

2. <span data-ttu-id="19fa7-228">**[プロジェクトを開く]** ダイアログ ボックスで、TypeEquivalenceRuntime プロジェクトを右クリックし、**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-228">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="19fa7-229">**[アプリケーション]** タブをクリックします。**[アセンブリ情報]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-229">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="19fa7-230">**[アセンブリ バージョン]** と **[ファイル バージョン]** の値を `2.0.0.0` に変更します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-230">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>

3. <span data-ttu-id="19fa7-231">SampleClass.vb ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-231">Open the SampleClass.vb file.</span></span> <span data-ttu-id="19fa7-232">SampleClass クラスに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-232">Add the following lines of code to the SampleClass class.</span></span>

```vb
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
    Return Now
End Function
```

    Save the file.

4. <span data-ttu-id="19fa7-233">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-233">Save the project.</span></span>

5. <span data-ttu-id="19fa7-234">TypeEquivalenceRuntime プロジェクトを右クリックし、**[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19fa7-234">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="19fa7-235">クラス ライブラリ .dll ファイルの更新バージョンがコンパイルされ、前に指定したビルド出力パス (たとえば、C:\TypeEquivalenceSample) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-235">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

6. <span data-ttu-id="19fa7-236">ファイル エクスプローラーで、出力パスのフォルダー (たとえば、C:\TypeEquivalenceSample) を開きます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-236">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="19fa7-237">TypeEquivalenceClient.exe をダブルクリックして、プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="19fa7-237">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="19fa7-238">プログラムでは、再コンパイルを行わなくても、新バージョンの TypeEquivalenceRuntime アセンブリが反映されます。</span><span class="sxs-lookup"><span data-stu-id="19fa7-238">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="19fa7-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="19fa7-239">See also</span></span>

- [<span data-ttu-id="19fa7-240">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19fa7-240">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="19fa7-241">プログラミングの概念</span><span class="sxs-lookup"><span data-stu-id="19fa7-241">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="19fa7-242">アセンブリを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="19fa7-242">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="19fa7-243">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="19fa7-243">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
