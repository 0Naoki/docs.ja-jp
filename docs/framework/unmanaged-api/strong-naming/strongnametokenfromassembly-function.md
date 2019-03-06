---
title: StrongNameTokenFromAssembly 関数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d8013d43dc14807804502e4a0820a2928f917e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499239"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="78d4f-102">StrongNameTokenFromAssembly 関数</span><span class="sxs-lookup"><span data-stu-id="78d4f-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="78d4f-103">指定したアセンブリ ファイルから、厳密な名前トークンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="78d4f-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="78d4f-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="78d4f-104">This function has been deprecated.</span></span> <span data-ttu-id="78d4f-105">使用して、 [iclrstrongname::strongnametokenfromassembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="78d4f-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d4f-106">構文</span><span class="sxs-lookup"><span data-stu-id="78d4f-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78d4f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78d4f-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="78d4f-108">[in]アセンブリのポータブル実行可能 (PE) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="78d4f-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="78d4f-109">[out]厳密な名前が返されたトークンです。</span><span class="sxs-lookup"><span data-stu-id="78d4f-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="78d4f-110">[out]厳密な名前トークンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="78d4f-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78d4f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="78d4f-111">Return Value</span></span>  
 <span data-ttu-id="78d4f-112">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="78d4f-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78d4f-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="78d4f-113">Remarks</span></span>  
 <span data-ttu-id="78d4f-114">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="78d4f-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="78d4f-115">トークンは、アセンブリの署名に使用する公開キーから作成される 64 ビット ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="78d4f-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="78d4f-116">トークンは、アセンブリの厳密な名前の一部であるし、アセンブリのメタデータから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="78d4f-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="78d4f-117">呼び出す必要があります、トークンが作成された後、 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)割り当てられたメモリを解放する関数。</span><span class="sxs-lookup"><span data-stu-id="78d4f-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="78d4f-118">場合、`StrongNameTokenFromAssembly`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="78d4f-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78d4f-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="78d4f-119">Requirements</span></span>  
 <span data-ttu-id="78d4f-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78d4f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78d4f-121">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="78d4f-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="78d4f-122">**ライブラリ:** Mscoree.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="78d4f-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="78d4f-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78d4f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d4f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="78d4f-124">See also</span></span>
- [<span data-ttu-id="78d4f-125">StrongNameTokenFromAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="78d4f-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="78d4f-126">StrongNameTokenFromAssemblyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="78d4f-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="78d4f-127">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78d4f-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
