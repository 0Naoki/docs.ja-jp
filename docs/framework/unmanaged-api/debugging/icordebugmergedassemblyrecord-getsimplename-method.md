---
title: ICorDebugMergedAssemblyRecord::GetSimpleName メソッド
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df142ea8f02d5cefc5c63a2d376afb331b4379ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197985"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="d3fe6-102">ICorDebugMergedAssemblyRecord::GetSimpleName メソッド</span><span class="sxs-lookup"><span data-stu-id="d3fe6-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="d3fe6-103">アセンブリの簡易名を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3fe6-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3fe6-104">Syntax</span></span>  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3fe6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3fe6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d3fe6-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d3fe6-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="d3fe6-108">文字配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3fe6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3fe6-109">Remarks</span></span>  
 <span data-ttu-id="d3fe6-110">このメソッドは、アセンブリの簡易名 ("System.Collections" など) を取得します。簡易名には、ファイル拡張子、バージョン、カルチャ、公開キー トークンが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="d3fe6-111">これはマネージド コード内の <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3fe6-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3fe6-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="d3fe6-113">Requirements</span></span>  
 <span data-ttu-id="d3fe6-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3fe6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3fe6-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3fe6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3fe6-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3fe6-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d3fe6-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d3fe6-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3fe6-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3fe6-118">See also</span></span>

- [<span data-ttu-id="d3fe6-119">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3fe6-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="d3fe6-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3fe6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
