---
title: GUID '<attribute>' の形式が正しくないため、'<number>' を適用できません。
ms.date: 07/20/2015
f1_keywords:
- vbc32500
- bc32500
helpviewer_keywords:
- BC32500
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
ms.openlocfilehash: 1e92c77e6138bbd546d9b837e095e41d5dfaf30c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279865"
---
# <a name="attribute-cannot-be-applied-because-the-format-of-the-guid-number-is-not-correct"></a>'GUID '\<number>' の形式が正しくないため、'\<attribute>' を適用できません。
`COMClassAttribute` 属性ブロックで、グローバル一意識別子 (GUID: globally unique identifier) の形式として有効でない GUID が指定されています。 `COMClassAttribute` は GUID を使ってクラス、インターフェイス、および作成イベントを一意に識別します。  
  
 GUID は 16 バイトで構成され、前の 8 バイトは数値、後の 8 バイトはバイナリです。 GUID は uuidgen.exe などの Microsoft ユーティリティで生成され、空間および時間内で一意であることが保証されています。  
  
 **エラー ID:** BC32500  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  COM オブジェクトを識別するために必要な正しい GUID を決定します。  
  
2.  `COMClassAttribute` 属性ブロックに示される GUID 文字列が正しくコピーされていることを確認します。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Guid>
- [属性の概要](../../../visual-basic/programming-guide/concepts/attributes/index.md)

