---
title: '方法: 指定された属性または名前のファイルをクエリする (C#)'
ms.date: 07/20/2015
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
ms.openlocfilehash: e600899251fe08884088275307f4311f3b9787cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564160"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a><span data-ttu-id="ae739-102">方法: 指定された属性または名前のファイルをクエリする (C#)</span><span class="sxs-lookup"><span data-stu-id="ae739-102">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>
<span data-ttu-id="ae739-103">この例では、指定されたディレクトリ ツリーで、指定されたファイル名拡張子 (".txt" など) を持つすべてのファイルを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae739-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="ae739-104">また、ファイルの作成日時に基づいて、ツリー内の最も新しいファイルまたは最も古いファイルを返す方法も示します。</span><span class="sxs-lookup"><span data-stu-id="ae739-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae739-105">例</span><span class="sxs-lookup"><span data-stu-id="ae739-105">Example</span></span>  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous   
        // query as a starting point. fileQuery is not   
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae739-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ae739-106">Compiling the Code</span></span>  
 <span data-ttu-id="ae739-107">.NET Framework Version 3.5 以降を対象とするプロジェクトを作成します。System.Core.dll を参照設定し、System.Linq 名前空間と System.IO 名前空間を `using` ディレクティブで指定します。</span><span class="sxs-lookup"><span data-stu-id="ae739-107">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae739-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae739-108">See also</span></span>

- [<span data-ttu-id="ae739-109">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="ae739-109">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="ae739-110">LINQ とファイル ディレクトリ (C#)</span><span class="sxs-lookup"><span data-stu-id="ae739-110">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
