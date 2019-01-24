---
title: クリップボードの形式が有効ではありません。
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 0a5d06b381df3af8de1d092b600239c9acfce39a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735780"
---
# <a name="clipboard-format-is-not-valid"></a>クリップボードの形式が有効ではありません。
指定されたクリップボードの形式は、実行中のメソッドと互換性がありません。 このエラーの考えられる原因には。  
  
-   クリップボードを使用して`GetText`または`SetText`メソッド以外のクリップボード形式を`vbCFText`または`vbCFLink`します。  
  
-   クリップボードを使用して`GetData`または`SetData`メソッド以外のクリップボード形式を`vbCFBitmap`、 `vbCFDIB`、または`vbCFMetafile`します。  
  
-   使用して、`GetData`または`SetData`のメソッド、`DataObject`登録されている形式 (& HC000 - & HFFFF)、Microsoft Windows によって予約された範囲内のクリップボード形式のときにそのクリップボードの形式で Microsoft Windows 登録されていません.  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   無効な形式を削除し、有効なものを指定します。  
  
## <a name="see-also"></a>関連項目
- [クリップボード:その他のデータ形式の追加](/cpp/mfc/clipboard-adding-other-formats)
