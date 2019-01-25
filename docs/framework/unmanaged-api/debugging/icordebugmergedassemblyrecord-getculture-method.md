---
title: ICorDebugMergedAssemblyRecord::GetCulture メソッド
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fd66ee28ca276aaa31e1e92a42d0fd88ff00d89
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654961"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="6b553-102">ICorDebugMergedAssemblyRecord::GetCulture メソッド</span><span class="sxs-lookup"><span data-stu-id="6b553-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="6b553-103">アセンブリのカルチャ名文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b553-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b553-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b553-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b553-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b553-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="6b553-106">[in] `szCulture` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="6b553-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="6b553-107">[out] `szCulture` バッファーに実際に書き込まれた文字数。</span><span class="sxs-lookup"><span data-stu-id="6b553-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="6b553-108">[out] カルチャ名を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="6b553-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b553-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b553-109">Remarks</span></span>  
 <span data-ttu-id="6b553-110">カルチャ名は、"en-US" (英語 (米国) カルチャ)、"neutral" (ニュートラル カルチャ) など、カルチャを識別する一意の文字列です。</span><span class="sxs-lookup"><span data-stu-id="6b553-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b553-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b553-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b553-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b553-112">Requirements</span></span>  
 <span data-ttu-id="6b553-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b553-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b553-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b553-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b553-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b553-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b553-116">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b553-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b553-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b553-117">See also</span></span>
- [<span data-ttu-id="6b553-118">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b553-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="6b553-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b553-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
