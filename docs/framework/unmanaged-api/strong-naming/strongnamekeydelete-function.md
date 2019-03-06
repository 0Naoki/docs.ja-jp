---
title: StrongNameKeyDelete 関数
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364516"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="85074-102">StrongNameKeyDelete 関数</span><span class="sxs-lookup"><span data-stu-id="85074-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="85074-103">指定したキー コンテナーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="85074-103">Deletes the specified key container.</span></span>

<span data-ttu-id="85074-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="85074-104">This function has been deprecated.</span></span> <span data-ttu-id="85074-105">使用して、 [iclrstrongname::strongnamekeydelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="85074-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="85074-106">構文</span><span class="sxs-lookup"><span data-stu-id="85074-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="85074-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="85074-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="85074-108">[in]削除するキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="85074-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="85074-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="85074-109">Return Value</span></span>

<span data-ttu-id="85074-110">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="85074-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="85074-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="85074-111">Remarks</span></span>

<span data-ttu-id="85074-112">使用して、 [StrongNameKeyInstall](strongnamekeyinstall-function.md)公開/秘密キー ペアをコンテナーにインポートする関数。</span><span class="sxs-lookup"><span data-stu-id="85074-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="85074-113">場合、`StrongNameKeyDelete`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="85074-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="85074-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="85074-114">Requirements</span></span>

<span data-ttu-id="85074-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85074-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="85074-116">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="85074-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="85074-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="85074-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="85074-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85074-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="85074-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="85074-119">See also</span></span>

- [<span data-ttu-id="85074-120">StrongNameKeyDelete メソッド</span><span class="sxs-lookup"><span data-stu-id="85074-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="85074-121">StrongNameKeyInstall メソッド</span><span class="sxs-lookup"><span data-stu-id="85074-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="85074-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="85074-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)