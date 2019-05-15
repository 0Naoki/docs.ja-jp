---
title: '方法: 署名されたフレンド アセンブリを作成する (C#)'
ms.date: 07/20/2015
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
ms.openlocfilehash: df04f6f5a006c7eea7984004e20578c85e51efe0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64582979"
---
# <a name="how-to-create-signed-friend-assemblies-c"></a><span data-ttu-id="7270b-102">方法: 署名されたフレンド アセンブリを作成する (C#)</span><span class="sxs-lookup"><span data-stu-id="7270b-102">How to: Create Signed Friend Assemblies (C#)</span></span>
<span data-ttu-id="7270b-103">この例では、厳密な名前を持つアセンブリと共にフレンド アセンブリを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7270b-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="7270b-104">両方のアセンブリに厳密な名前が付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7270b-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="7270b-105">この例のアセンブリは両方とも同じキーを使用していますが、2 つのアセンブリそれぞれが別々のキーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7270b-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="7270b-106">署名付きアセンブリとフレンド アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="7270b-106">To create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="7270b-107">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7270b-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="7270b-108">厳密な名前ツールで次のコマンド シーケンスを使用して、キー ファイルを生成し、公開鍵を表示します。</span><span class="sxs-lookup"><span data-stu-id="7270b-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="7270b-109">詳細については、「[Sn.exe (厳密名ツール)](../../../../framework/tools/sn-exe-strong-name-tool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7270b-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1. <span data-ttu-id="7270b-110">この例で使用する厳密な名前キーを生成し、FriendAssemblies.snk ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="7270b-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2. <span data-ttu-id="7270b-111">FriendAssemblies.snk から公開鍵を抽出し、FriendAssemblies.publickey に追加します。</span><span class="sxs-lookup"><span data-stu-id="7270b-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. <span data-ttu-id="7270b-112">FriendAssemblies.publickey ファイルに格納されている公開鍵を表示します。</span><span class="sxs-lookup"><span data-stu-id="7270b-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="7270b-113">次のコードを含む、`friend_signed_A` という名前の C# ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7270b-113">Create a C# file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="7270b-114">コードでは <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性を使用して、フレンド アセンブリとして friend_signed_B を宣言します。</span><span class="sxs-lookup"><span data-stu-id="7270b-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="7270b-115">厳密な名前ツールは、実行するごとに新しい公開鍵を生成します。</span><span class="sxs-lookup"><span data-stu-id="7270b-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="7270b-116">このため、次の例に示すコード内の公開鍵を、ここで生成した公開鍵に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7270b-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```csharp  
    // friend_signed_A.cs  
    // Compile with:   
    // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    using System.Runtime.CompilerServices;  
  
    [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
    class Class1  
    {  
        public void Test()  
        {  
            System.Console.WriteLine("Class1.Test");  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
4. <span data-ttu-id="7270b-117">次のコマンドを使用して friend_signed_A をコンパイルして署名します。</span><span class="sxs-lookup"><span data-stu-id="7270b-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5. <span data-ttu-id="7270b-118">次のコードを含む、`friend_signed_B` という名前の C# ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7270b-118">Create a C# file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="7270b-119">friend_signed_A が friend_signed_B をフレンド アセンブリとして指定しているため、friend_signed_B 内のコードは、friend_signed_A の `internal` 型とメンバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7270b-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `internal` types and members from friend_signed_A.</span></span> <span data-ttu-id="7270b-120">このファイルには、次のコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7270b-120">The file contains the following code.</span></span>  
  
    ```csharp  
    // friend_signed_B.cs  
    // Compile with:   
    // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            Class1 inst = new Class1();  
            inst.Test();  
        }  
    }  
    ```  
  
6. <span data-ttu-id="7270b-121">次のコマンドを使用して friend_signed_B をコンパイルして署名します。</span><span class="sxs-lookup"><span data-stu-id="7270b-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     <span data-ttu-id="7270b-122">コンパイラによって生成されたアセンブリの名前は、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性に渡されたフレンド アセンブリ名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7270b-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="7270b-123">`/out` コンパイラ オプションを使用して、出力アセンブリ (.exe または .dll) の名前を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7270b-123">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span>  <span data-ttu-id="7270b-124">詳しくは、「[/out (C# コンパイラ オプション)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7270b-124">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
7. <span data-ttu-id="7270b-125">friend_signed_B.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="7270b-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="7270b-126">このプログラムでは、文字列 "Class1.Test" が出力されます。</span><span class="sxs-lookup"><span data-stu-id="7270b-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7270b-127">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7270b-127">.NET Framework Security</span></span>  
 <span data-ttu-id="7270b-128"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性と <xref:System.Security.Permissions.StrongNameIdentityPermission> クラスには類似点があります。</span><span class="sxs-lookup"><span data-stu-id="7270b-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="7270b-129">主な違いは、<xref:System.Security.Permissions.StrongNameIdentityPermission> はセキュリティ アクセス許可を要求することで特定のコード セクションを実行できますが、<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性では `internal` 型とメンバーの参照可能範囲を制御することです。</span><span class="sxs-lookup"><span data-stu-id="7270b-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7270b-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="7270b-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="7270b-131">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="7270b-131">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="7270b-132">フレンド アセンブリ</span><span class="sxs-lookup"><span data-stu-id="7270b-132">Friend Assemblies</span></span>](../../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="7270b-133">方法: 署名のないフレンド アセンブリを作成する (C#)</span><span class="sxs-lookup"><span data-stu-id="7270b-133">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="7270b-134">/keyfile</span><span class="sxs-lookup"><span data-stu-id="7270b-134">/keyfile</span></span>](../../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [<span data-ttu-id="7270b-135">Sn.exe (厳密名ツール)</span><span class="sxs-lookup"><span data-stu-id="7270b-135">Sn.exe (Strong Name Tool)</span></span>](../../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="7270b-136">厳密な名前付きアセンブリの作成と使用</span><span class="sxs-lookup"><span data-stu-id="7270b-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="7270b-137">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7270b-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
