---
title: '方法: ファイル操作の [進行状況] ダイアログ ボックスを表示する (C# プログラミング ガイド)'
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: e93ce06a01046dfaf4465470ba7fdc687effa58d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2018
ms.locfileid: "47207404"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a>方法: ファイル操作の [進行状況] ダイアログ ボックスを表示する (C# プログラミング ガイド)
<xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 名前空間の <xref:Microsoft.VisualBasic?displayProperty=nameWithType> メソッドを使用すると、Windows でのファイル操作に関する進行状況を示す標準ダイアログ ボックスを提供できます。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a>Visual Studio で参照を追加するには  
  
1.  メニュー バーで、**[プロジェクト]**、**[参照の追加]** の順に選択します。  
  
     **[参照マネージャー]** ダイアログ ボックスが表示されます。  
  
2.  **[アセンブリ]** で、**[フレームワーク]** を選択します (選択されていない場合)。  
  
3.  名前の一覧で、**[Microsoft.VisualBasic]** のチェック ボックスをオンにし、**[OK]** をクリックしてダイアログ ボックスを閉じます。  
  
## <a name="example"></a>例  
 次のコードは、`sourcePath` で指定されたディレクトリを `destinationPath` で指定されたディレクトリにコピーします。 また、操作の完了までに必要な残りの予測時間を示す、標準的なダイアログ ボックスを表示します。  
  
 [!code-csharp[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## <a name="see-also"></a>参照

- [ファイル システムとレジストリ (C# プログラミング ガイド)](../../../csharp/programming-guide/file-system/index.md)
