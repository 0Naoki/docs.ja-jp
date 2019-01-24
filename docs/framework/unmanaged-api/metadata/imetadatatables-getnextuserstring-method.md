---
title: IMetaDataTables::GetNextUserString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f5e4a36f633b215faaf5930cd2487c26c1d5ce3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696231"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="43979-102">IMetaDataTables::GetNextUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="43979-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="43979-103">現在のテーブル列で [次へ]、ハード コーディングされた文字列を含む行のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="43979-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43979-104">構文</span><span class="sxs-lookup"><span data-stu-id="43979-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43979-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43979-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="43979-106">[in]現在の文字列の列からインデックス値。</span><span class="sxs-lookup"><span data-stu-id="43979-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="43979-107">[out]列には、次の文字列の行インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="43979-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43979-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="43979-108">Remarks</span></span>  
 <span data-ttu-id="43979-109">お勧めしません、このメソッドを使用して一貫性のある結果を返さないためです。</span><span class="sxs-lookup"><span data-stu-id="43979-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="43979-110">GUID の表については、ドキュメントを参照して、共通言語基盤 (CLI)、特に"第 2 部。メタデータの定義およびセマンティクス"。</span><span class="sxs-lookup"><span data-stu-id="43979-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="43979-111">ドキュメントはオンラインで入手できます。MSDN の「[ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212)」 (ECMA の C# および共通言語基盤の標準規格) と、ECMA のインターナショナル Web サイトにある「[Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43979-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43979-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="43979-112">Requirements</span></span>  
 <span data-ttu-id="43979-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43979-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43979-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="43979-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43979-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="43979-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43979-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43979-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43979-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="43979-117">See also</span></span>
- [<span data-ttu-id="43979-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43979-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="43979-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43979-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
