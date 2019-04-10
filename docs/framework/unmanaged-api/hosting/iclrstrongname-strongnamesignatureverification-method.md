---
title: ICLRStrongName::StrongNameSignatureVerification メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9fb7098c29768821cafad6662b646eb0e08a138
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212844"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="06890-102">ICLRStrongName::StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="06890-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="06890-103">指定されたパスにあるアセンブリ マニフェストが指定したフラグに従って検証される、厳密な名前の署名を含むかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="06890-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06890-104">構文</span><span class="sxs-lookup"><span data-stu-id="06890-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06890-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06890-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="06890-106">[in]確認するアセンブリのポータブル実行可能ファイル (.dll または .exe) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="06890-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="06890-107">[in]検証動作を変更するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="06890-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="06890-108">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="06890-108">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="06890-109">(0x00000001) - レジストリ設定を上書きする必要がある場合でも、強制的に検証します。</span><span class="sxs-lookup"><span data-stu-id="06890-109">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="06890-110">(0x00000002) - これが初めてマニフェストの検証であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="06890-110">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="06890-111">(0x00000004) のキャッシュで管理者特権を持つユーザーにのみアクセスを許可することを指定します。</span><span class="sxs-lookup"><span data-stu-id="06890-111">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="06890-112">(0x00000008) のアセンブリが現在のユーザーのみがアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="06890-112">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="06890-113">(0x00000010) - キャッシュはしないことを指定のアクセス制限を保証します。</span><span class="sxs-lookup"><span data-stu-id="06890-113">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="06890-114">(0x80000000) - 内部デバッグのために予約されています。</span><span class="sxs-lookup"><span data-stu-id="06890-114">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="06890-115">[out]厳密な名前の署名が検証されたかどうかを示すフラグです。</span><span class="sxs-lookup"><span data-stu-id="06890-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="06890-116">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="06890-116">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="06890-117">(0x00000001) - この値に設定が`false`レジストリ設定のために、検証が成功したことを指定します。</span><span class="sxs-lookup"><span data-stu-id="06890-117">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06890-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="06890-118">Return Value</span></span>  
 `S_OK` <span data-ttu-id="06890-119">メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="06890-119">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06890-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="06890-120">Requirements</span></span>  
 <span data-ttu-id="06890-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06890-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06890-122">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="06890-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="06890-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="06890-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="06890-124">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="06890-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="06890-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="06890-125">See also</span></span>

- [<span data-ttu-id="06890-126">StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="06890-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="06890-127">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06890-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
