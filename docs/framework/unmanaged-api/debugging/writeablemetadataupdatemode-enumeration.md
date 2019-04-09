---
title: WriteableMetadataUpdateMode 列挙型
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62e4328b75a7f6fecc28cd620ec3ac18460316c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111138"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="4f335-102">WriteableMetadataUpdateMode 列挙型</span><span class="sxs-lookup"><span data-stu-id="4f335-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="4f335-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="4f335-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4f335-104">メモリ内のメタデータ更新をデバッガーに対して可視にするかどうかを指定する値を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f335-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f335-105">構文</span><span class="sxs-lookup"><span data-stu-id="4f335-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="4f335-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4f335-106">Members</span></span>  
  
|<span data-ttu-id="4f335-107">メンバー名</span><span class="sxs-lookup"><span data-stu-id="4f335-107">Member name</span></span>|<span data-ttu-id="4f335-108">説明</span><span class="sxs-lookup"><span data-stu-id="4f335-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="4f335-109">メモリ内のメタデータ更新を可視にするときに、.NET Framework の以前のバージョンとの互換性を保持します。</span><span class="sxs-lookup"><span data-stu-id="4f335-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="4f335-110">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f335-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="4f335-111">メモリ内のメタデータ更新をデバッガーに対して可視にします。</span><span class="sxs-lookup"><span data-stu-id="4f335-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f335-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f335-112">Remarks</span></span>  
 <span data-ttu-id="4f335-113">メンバー、`WriteableMetadataUpdateMode`に列挙体を渡すことができます、 [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)メモリ内がターゲット プロセス内のメタデータを更新するかどうかを制御するメソッドは、デバッガーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f335-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="4f335-114">`LegacyCompatPolicy` オプションは、4.5.2 より前の .NET Framework のバージョンと同じ動作を適用します。</span><span class="sxs-lookup"><span data-stu-id="4f335-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="4f335-115">これは多くの場合、メタデータの更新が可視でないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4f335-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="4f335-116">しかし、多数のデバッグ メソッドを呼び出すとデバッガーは明示的に強制変換し、更新を可視にします。</span><span class="sxs-lookup"><span data-stu-id="4f335-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="4f335-117">たとえば、デバッガーを渡します[icordebugilframe::getlocalvariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)の現在の状態に一致するスナップショットが更新され、モジュールのメソッドの元のメタデータ、すべてのメタデータに見つかりません変数のインデックス、プロセスです。</span><span class="sxs-lookup"><span data-stu-id="4f335-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="4f335-118">言い換えれば、`LegacyCompatPolicy` オプションでは、メタデータの更新によりアンマネージ デバギング API のその他の部分がどのように使用されているかによって、使用可能なメタデータ更新がデバッガーに対して全く可視でない場合、一部が可視になる場合、すべてが可視になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f335-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f335-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f335-119">Requirements</span></span>  
 <span data-ttu-id="4f335-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f335-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f335-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f335-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f335-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f335-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4f335-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="4f335-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f335-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f335-124">See also</span></span>

- [<span data-ttu-id="4f335-125">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="4f335-125">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="4f335-126">SetWriteableMetadataUpdateMode メソッド</span><span class="sxs-lookup"><span data-stu-id="4f335-126">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
