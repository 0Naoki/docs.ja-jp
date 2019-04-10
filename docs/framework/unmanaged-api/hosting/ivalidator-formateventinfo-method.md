---
title: IValidator::FormatEventInfo メソッド
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecbecec86d81357000679ab50e12f06d91c9f50d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217082"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="d8a14-102">IValidator::FormatEventInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="d8a14-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="d8a14-103">指定した検証エラーに対応するエラー メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8a14-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8a14-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8a14-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8a14-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8a14-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="d8a14-106">[in]検証のエラー ハンドラーに渡された HRESULT 値。</span><span class="sxs-lookup"><span data-stu-id="d8a14-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="d8a14-107">[in]A`VEContext`検証エラーに関するコンテキスト情報を格納しているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d8a14-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="d8a14-108">[入力、出力]返されたエラー メッセージを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="d8a14-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="d8a14-109">[in]エラー メッセージの最大長。</span><span class="sxs-lookup"><span data-stu-id="d8a14-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="d8a14-110">[in]エラーを説明する追加のパラメーターを格納するセーフ配列。</span><span class="sxs-lookup"><span data-stu-id="d8a14-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8a14-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d8a14-111">Requirements</span></span>  
 <span data-ttu-id="d8a14-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a14-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8a14-113">**ヘッダー:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="d8a14-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d8a14-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d8a14-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d8a14-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d8a14-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
