---
title: ファイル システムとレジストリ (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 3625f7a108675a3a9ab6be16ef94ae7e7c107612
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2018
ms.locfileid: "44368979"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="36d10-102">ファイル システムとレジストリ (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="36d10-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="36d10-103">以下のトピックでは、C# と .NET Framework を使用して、ファイル、フォルダー、レジストリに対するさまざまな基本操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36d10-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="36d10-104">In This Section</span></span>  
  
|<span data-ttu-id="36d10-105">**タイトル**</span><span class="sxs-lookup"><span data-stu-id="36d10-105">**Title**</span></span>|<span data-ttu-id="36d10-106">**説明**</span><span class="sxs-lookup"><span data-stu-id="36d10-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="36d10-107">方法: ディレクトリ ツリーを反復処理する</span><span class="sxs-lookup"><span data-stu-id="36d10-107">How to: Iterate Through a Directory Tree</span></span>](../../../csharp/programming-guide/file-system/how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="36d10-108">ディレクトリ ツリーを手動で反復処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="36d10-109">方法: ファイル、フォルダー、およびドライブに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="36d10-109">How to: Get Information About Files, Folders, and Drives</span></span>](../../../csharp/programming-guide/file-system/how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="36d10-110">作成時刻やサイズなど、ファイル、フォルダー、ドライブに関する情報を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="36d10-111">方法: ファイルまたはフォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="36d10-111">How to: Create a File or Folder</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-file-or-folder.md)|<span data-ttu-id="36d10-112">新しいファイルまたはフォルダーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="36d10-113">方法: ファイルおよびフォルダーのコピー、削除、および移動を行う (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="36d10-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="36d10-114">ファイルやフォルダーをコピー、削除、および移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-114">Shows how to copy, delete and move files and folders.</span></span>|  
|<span data-ttu-id="36d10-115">[方法: ファイル操作の [進行状況] ダイアログ ボックスを表示する](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)</span><span class="sxs-lookup"><span data-stu-id="36d10-115">[How to: Provide a Progress Dialog Box for File Operations](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)</span></span>|<span data-ttu-id="36d10-116">特定のファイル操作について、Windows の標準的な進行状況ダイアログを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="36d10-117">方法: テキスト ファイルに書き込む</span><span class="sxs-lookup"><span data-stu-id="36d10-117">How to: Write to a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)|<span data-ttu-id="36d10-118">テキスト ファイルに書き込み方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="36d10-119">方法: テキスト ファイルから読み込む</span><span class="sxs-lookup"><span data-stu-id="36d10-119">How to: Read From a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-read-from-a-text-file.md)|<span data-ttu-id="36d10-120">テキスト ファイルから読み取る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="36d10-121">方法: テキスト ファイルを一度に 1 行読み込む</span><span class="sxs-lookup"><span data-stu-id="36d10-121">How to: Read a Text File One Line at a Time</span></span>](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="36d10-122">ファイルから一度に 1 行ずつテキストを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="36d10-123">方法: レジストリにキーを作成する</span><span class="sxs-lookup"><span data-stu-id="36d10-123">How to: Create a Key In the Registry</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="36d10-124">キーをシステム レジストリに書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36d10-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="36d10-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="36d10-125">Related Sections</span></span>  
 [<span data-ttu-id="36d10-126">ファイルおよびストリーム入出力</span><span class="sxs-lookup"><span data-stu-id="36d10-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="36d10-127">方法: ファイルおよびフォルダーのコピー、削除、および移動を行う (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="36d10-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="36d10-128">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="36d10-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
  
 [<span data-ttu-id="36d10-129">ファイル、フォルダー、ドライブ</span><span class="sxs-lookup"><span data-stu-id="36d10-129">Files, Folders and Drives</span></span>](../../../csharp/programming-guide/file-system/index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
