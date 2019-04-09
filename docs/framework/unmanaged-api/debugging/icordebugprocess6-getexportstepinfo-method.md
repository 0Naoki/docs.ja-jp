---
title: ICorDebugProcess6::GetExportStepInfo メソッド
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a891e6d65d159875f5607ac33b0668414cb380
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137216"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="c1557-102">ICorDebugProcess6::GetExportStepInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="c1557-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="c1557-103">マネージド コードのステップ実行に役立つランタイム エクスポート関数の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c1557-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1557-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1557-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1557-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1557-105">Parameters</span></span>  
 <span data-ttu-id="c1557-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="c1557-106">pszExportName</span></span>  
 <span data-ttu-id="c1557-107">[入力] PE エクスポート テーブルに書き込まれるランタイム エクスポート関数の名前。</span><span class="sxs-lookup"><span data-stu-id="c1557-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="c1557-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="c1557-108">invokeKind</span></span>  
 <span data-ttu-id="c1557-109">[out]メンバーへのポインター、 [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)エクスポートされた関数がマネージ コードを呼び出す方法について説明する列挙体。</span><span class="sxs-lookup"><span data-stu-id="c1557-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="c1557-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="c1557-110">invokePurpose</span></span>  
 <span data-ttu-id="c1557-111">[out]メンバーへのポインター、 [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)エクスポートされた関数がマネージ コードを呼び出す理由を示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="c1557-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1557-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1557-112">Return Value</span></span>  
 <span data-ttu-id="c1557-113">メソッドは、次の表に記載されている値を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1557-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="c1557-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1557-114">Return value</span></span>|<span data-ttu-id="c1557-115">説明</span><span class="sxs-lookup"><span data-stu-id="c1557-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="c1557-116">メソッド呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="c1557-116">The method call was successful.</span></span>|  
|`E_POINTER`|`pInvokeKind` <span data-ttu-id="c1557-117">または`pInvokePurpose`は**null**します。</span><span class="sxs-lookup"><span data-stu-id="c1557-117">or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="c1557-118">その他の失敗した `HRESULT` 値。</span><span class="sxs-lookup"><span data-stu-id="c1557-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="c1557-119">必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="c1557-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1557-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="c1557-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1557-121">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1557-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1557-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1557-122">Requirements</span></span>  
 <span data-ttu-id="c1557-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1557-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1557-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1557-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1557-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1557-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c1557-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c1557-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1557-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1557-127">See also</span></span>

- [<span data-ttu-id="c1557-128">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1557-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="c1557-129">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1557-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
