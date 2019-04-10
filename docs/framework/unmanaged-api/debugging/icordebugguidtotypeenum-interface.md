---
title: ICorDebugGuidToTypeEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2ea67c6e4d860d41cfe67aaab73babb51f3ce45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210660"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="6ad1f-102">ICorDebugGuidToTypeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ad1f-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="6ad1f-103">一連の Guid とは、ICorDebugType のインスタンスによって表される、対応する型間のマッピングを定義する列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ad1f-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="6ad1f-104">このインターフェイスは、ICorDebugEnum インターフェイスからメソッドを継承します。</span><span class="sxs-lookup"><span data-stu-id="6ad1f-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ad1f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6ad1f-105">Methods</span></span>  
  
|<span data-ttu-id="6ad1f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="6ad1f-106">Method</span></span>|<span data-ttu-id="6ad1f-107">説明</span><span class="sxs-lookup"><span data-stu-id="6ad1f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ad1f-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="6ad1f-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="6ad1f-109">指定した数を取得[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)インスタンス情報を入力する Guid にマップします。</span><span class="sxs-lookup"><span data-stu-id="6ad1f-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ad1f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ad1f-110">Remarks</span></span>  
 <span data-ttu-id="6ad1f-111">`ICorDebugGuidToTypeEnum`インターフェイス オブジェクトを呼び出すことによって取得できます、 [icordebugappdomain 3::getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6ad1f-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="6ad1f-112">デバッガーは、このインターフェイスを呼び出すことができます[次](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)を取得するメソッド[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)のマッピングを表すオブジェクトの表現を管理する[!INCLUDE[wrt](../../../../includes/wrt-md.md)]に読み込まれた型、呼び出しに使用されるアプリケーション ドメイン、 [icordebugappdomain 3::getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6ad1f-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ad1f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="6ad1f-113">Requirements</span></span>  
 **<span data-ttu-id="6ad1f-114">プラットフォーム: </span><span class="sxs-lookup"><span data-stu-id="6ad1f-114">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="6ad1f-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ad1f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ad1f-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ad1f-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6ad1f-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6ad1f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ad1f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ad1f-118">See also</span></span>

- [<span data-ttu-id="6ad1f-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ad1f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
