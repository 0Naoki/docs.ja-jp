---
title: '方法: ファイルがアセンブリ (Visual Basic) を確認します。'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: ced41279e7e192d6d5bed53dbce7378395b32e6d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089400"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="86070-102">方法: ファイルがアセンブリ (Visual Basic) を確認します。</span><span class="sxs-lookup"><span data-stu-id="86070-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="86070-103">ファイルが管理されていて、ファイルのメタデータにアセンブリ エントリが含まれている場合、そのファイルはアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="86070-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="86070-104">アセンブリとメタデータの詳細については、「[アセンブリ マニフェスト](../../../../framework/app-domains/assembly-manifest.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86070-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="86070-105">ファイルがアセンブリかどうかを手動で確認する方法</span><span class="sxs-lookup"><span data-stu-id="86070-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="86070-106">[Ildasm.exe (IL 逆アセンブラー)](../../../../framework/tools/ildasm-exe-il-disassembler.md) を起動します。</span><span class="sxs-lookup"><span data-stu-id="86070-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2.  <span data-ttu-id="86070-107">テストするファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="86070-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="86070-108">**ILDASM** で、そのファイルが移植可能な実行可能 (PE) ファイルではないと報告された場合、そのファイルはアセンブリでありません。</span><span class="sxs-lookup"><span data-stu-id="86070-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="86070-109">詳細については、「[方法: アセンブリの内容を表示する](../../../../framework/app-domains/how-to-view-assembly-contents.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86070-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="86070-110">ファイルがアセンブリかどうかをプログラムによって確認する方法</span><span class="sxs-lookup"><span data-stu-id="86070-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="86070-111">テストするファイルの完全パスと名前を渡して、<xref:System.Reflection.AssemblyName.GetAssemblyName%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="86070-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="86070-112"><xref:System.BadImageFormatException> 例外がスローされた場合、ファイルはアセンブリでありません。</span><span class="sxs-lookup"><span data-stu-id="86070-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86070-113">例</span><span class="sxs-lookup"><span data-stu-id="86070-113">Example</span></span>  
 <span data-ttu-id="86070-114">次の例では、DLL がアセンブリかどうかをテストして確認します。</span><span class="sxs-lookup"><span data-stu-id="86070-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <span data-ttu-id="86070-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A> メソッドはテスト ファイルを読み込み、情報が読み取られた時点で解放します。</span><span class="sxs-lookup"><span data-stu-id="86070-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86070-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="86070-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>  
- [<span data-ttu-id="86070-117">プログラミングの概念</span><span class="sxs-lookup"><span data-stu-id="86070-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
- [<span data-ttu-id="86070-118">アセンブリとグローバル アセンブリ キャッシュ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86070-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)
