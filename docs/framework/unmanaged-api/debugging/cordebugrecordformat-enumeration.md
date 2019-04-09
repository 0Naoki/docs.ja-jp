---
title: CorDebugRecordFormat 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: add1458bb3a50a5e5433e8cc7baaf47d750c927d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083674"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="14e17-102">CorDebugRecordFormat 列挙体</span><span class="sxs-lookup"><span data-stu-id="14e17-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="14e17-103">ネイティブ例外デバッグ イベントに関する情報を格納するバイト配列内のデータの形式を示します。</span><span class="sxs-lookup"><span data-stu-id="14e17-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e17-104">構文</span><span class="sxs-lookup"><span data-stu-id="14e17-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="14e17-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="14e17-105">Members</span></span>  
  
|<span data-ttu-id="14e17-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="14e17-106">Member</span></span>|<span data-ttu-id="14e17-107">説明</span><span class="sxs-lookup"><span data-stu-id="14e17-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="14e17-108">データは、32 ビット Windows 例外レコードです。</span><span class="sxs-lookup"><span data-stu-id="14e17-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="14e17-109">データは、64 ビット Windows 例外レコードです。</span><span class="sxs-lookup"><span data-stu-id="14e17-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e17-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="14e17-110">Remarks</span></span>  
 <span data-ttu-id="14e17-111">メンバー、`CorDebugRecordFormat`に列挙体が渡される、 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)メソッド内のバイト配列の形式を指定するその`pRecord`引数。</span><span class="sxs-lookup"><span data-stu-id="14e17-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14e17-112">この列挙型は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="14e17-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14e17-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="14e17-113">Requirements</span></span>  
 <span data-ttu-id="14e17-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e17-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e17-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14e17-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14e17-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14e17-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="14e17-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="14e17-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14e17-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="14e17-118">See also</span></span>

- [<span data-ttu-id="14e17-119">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="14e17-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
