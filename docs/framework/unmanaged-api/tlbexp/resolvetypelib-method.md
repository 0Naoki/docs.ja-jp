---
title: ResolveTypeLib メソッド
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2558e760be8519e528baeff438273c8871f320
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924470"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="f43b1-102">ResolveTypeLib メソッド</span><span class="sxs-lookup"><span data-stu-id="f43b1-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="f43b1-103">完全修飾パスを返すことによって、タイプ ライブラリの簡易名を解決します。</span><span class="sxs-lookup"><span data-stu-id="f43b1-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f43b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="f43b1-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f43b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f43b1-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="f43b1-106">[in]A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr)タイプ ライブラリの簡易名を格納しています。</span><span class="sxs-lookup"><span data-stu-id="f43b1-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="f43b1-107">[in]レジストリでタイプ ライブラリに割り当てられた GUID です。</span><span class="sxs-lookup"><span data-stu-id="f43b1-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="f43b1-108">[in]タイプ ライブラリのローカリゼーション ID。</span><span class="sxs-lookup"><span data-stu-id="f43b1-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="f43b1-109">[in]タイプ ライブラリのメジャー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f43b1-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="f43b1-110">たとえば、バージョン*x.y*、メジャー バージョン番号は*x*します。</span><span class="sxs-lookup"><span data-stu-id="f43b1-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="f43b1-111">[in]タイプ ライブラリのマイナー バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f43b1-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="f43b1-112">たとえば、バージョン*x.y*、マイナー バージョン番号は*y*します。</span><span class="sxs-lookup"><span data-stu-id="f43b1-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="f43b1-113">[in]A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind)オペレーティング環境を識別するフラグ。</span><span class="sxs-lookup"><span data-stu-id="f43b1-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="f43b1-114">一般的な値は SYS_WIN32 および SYS_WIN64 です。</span><span class="sxs-lookup"><span data-stu-id="f43b1-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="f43b1-115">[out]ポインターを[BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr)でという名前のタイプ ライブラリの完全なパスを格納している、`bstrSimpleName`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f43b1-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f43b1-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="f43b1-116">Remarks</span></span>  
 <span data-ttu-id="f43b1-117">`ResolveTypeLib`メソッドを呼び出して、 [LoadTypeLibWithResolver 関数](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)中に[Tlbexp.exe (タイプ ライブラリ エクスポーター)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)処理します。</span><span class="sxs-lookup"><span data-stu-id="f43b1-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="f43b1-118">このインターフェイスのカスタム実装を返す必要があります、 [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr)でという名前のタイプ ライブラリの完全なパスを格納している、`bstrSimpleName`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f43b1-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f43b1-119">要件</span><span class="sxs-lookup"><span data-stu-id="f43b1-119">Requirements</span></span>  
 <span data-ttu-id="f43b1-120">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f43b1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f43b1-121">**ヘッダー:** TlbRef.idl、TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="f43b1-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="f43b1-122">**ライブラリ:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="f43b1-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="f43b1-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f43b1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43b1-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f43b1-124">See Also</span></span>  
 [<span data-ttu-id="f43b1-125">Tlbexp ヘルパー関数</span><span class="sxs-lookup"><span data-stu-id="f43b1-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="f43b1-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="f43b1-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
