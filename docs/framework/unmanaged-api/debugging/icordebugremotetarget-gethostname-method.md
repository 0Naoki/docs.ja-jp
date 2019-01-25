---
title: ICorDebugRemoteTarget::GetHostName メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf35715564e58f1811618b6859a860008e9660c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655401"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="9ca69-102">ICorDebugRemoteTarget::GetHostName メソッド</span><span class="sxs-lookup"><span data-stu-id="9ca69-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="9ca69-103">リモート デバッグ対象コンピューターの完全修飾ドメイン名または IPv4 アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="9ca69-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="9ca69-104">IPV6 はこの時点ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9ca69-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca69-105">構文</span><span class="sxs-lookup"><span data-stu-id="9ca69-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ca69-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ca69-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="9ca69-107">[入力] `szHostName` バッファーのサイズ (文字単位)。</span><span class="sxs-lookup"><span data-stu-id="9ca69-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="9ca69-108">このパラメーターが 0 である場合、`szHostName` は null であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="9ca69-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="9ca69-109">[出力] 配列に返される文字数。ホスト名または IP アドレスの null 終端文字を含みます。</span><span class="sxs-lookup"><span data-stu-id="9ca69-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="9ca69-110">このパラメーターには、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9ca69-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="9ca69-111">[出力] ホスト名または IP アドレスを含むバッファー。</span><span class="sxs-lookup"><span data-stu-id="9ca69-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ca69-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="9ca69-112">Return Value</span></span>  
 <span data-ttu-id="9ca69-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ca69-113">S_OK</span></span>  
 <span data-ttu-id="9ca69-114">ホスト名または IP アドレスは正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="9ca69-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="9ca69-115">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="9ca69-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9ca69-116">ホスト名または IP アドレスを返すことができません。</span><span class="sxs-lookup"><span data-stu-id="9ca69-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ca69-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ca69-117">Remarks</span></span>  
 <span data-ttu-id="9ca69-118">このメソッドは、デバッガー ライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="9ca69-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="9ca69-119">複数の呼び出しパラダイムに従う必要があります。最初の呼び出しでは、呼び出し元に null を渡し両方`cchHostName`と`szHostName`、および`pcchHostName`必要なバッファーのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="9ca69-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer .</span></span> <span data-ttu-id="9ca69-120">第 2 の呼び出しでは、以前に返されたサイズが `cchHostName` に渡され、適切にサイズ設定されたバッファーが `szHostName` に渡されます。</span><span class="sxs-lookup"><span data-stu-id="9ca69-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ca69-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ca69-121">Requirements</span></span>  
 <span data-ttu-id="9ca69-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca69-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca69-123">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="9ca69-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="9ca69-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ca69-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ca69-125">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9ca69-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca69-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ca69-126">See also</span></span>
- [<span data-ttu-id="9ca69-127">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ca69-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="9ca69-128">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ca69-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
