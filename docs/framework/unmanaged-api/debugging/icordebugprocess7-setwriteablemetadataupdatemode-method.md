---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94e2f1c13c91c50daa5730898adf0aedf00f6579
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092618"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="dfff4-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode メソッド</span><span class="sxs-lookup"><span data-stu-id="dfff4-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="dfff4-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="dfff4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dfff4-104">デバッガーが、ターゲット プロセス内のメタデータに対するメモリ内更新をどのように処理するかを設定します。</span><span class="sxs-lookup"><span data-stu-id="dfff4-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfff4-105">構文</span><span class="sxs-lookup"><span data-stu-id="dfff4-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfff4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dfff4-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="dfff4-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)ターゲット プロセス内のメタデータをメモリ内の更新プログラムが表示されているかどうかを指定する列挙値 (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) または非表示 (`WriteableMetadataUpdateMode::LegacyCompatPolicy`)、デバッガーにします。</span><span class="sxs-lookup"><span data-stu-id="dfff4-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfff4-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="dfff4-108">Remarks</span></span>  
 <span data-ttu-id="dfff4-109">ターゲット プロセスのメタデータに対する更新は、[編集]、[続行] で行うか、プロファイラー、または <xref:System.Reflection.Emit?displayProperty=nameWithType> で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dfff4-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfff4-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="dfff4-110">Requirements</span></span>  
 <span data-ttu-id="dfff4-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfff4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfff4-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfff4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfff4-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfff4-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dfff4-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="dfff4-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dfff4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfff4-115">See also</span></span>

- [<span data-ttu-id="dfff4-116">ICorDebugProcess7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dfff4-116">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)
- [<span data-ttu-id="dfff4-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="dfff4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
