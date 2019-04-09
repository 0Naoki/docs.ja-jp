---
title: ValidatorFlags 列挙型
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa10ae1cf67339a6719210f3162f19ac648e8ee5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127414"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="a3d63-102">ValidatorFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="a3d63-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="a3d63-103">呼び出しで実行される検証の種類を示す値を含む、 [iclrvalidator::validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a3d63-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d63-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3d63-104">Syntax</span></span>  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="a3d63-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a3d63-105">Members</span></span>  
  
|<span data-ttu-id="a3d63-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a3d63-106">Member</span></span>|<span data-ttu-id="a3d63-107">説明</span><span class="sxs-lookup"><span data-stu-id="a3d63-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="a3d63-108">のみ Microsoft intermediate language (MSIL) 実行可能ファイルを検証することを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3d63-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="a3d63-109">実行可能ファイルの形式のみを検証することを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3d63-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="a3d63-110">すべての種類の検証の実行し、で報告される必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3d63-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="a3d63-111">実行可能ファイルの形式を検証しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3d63-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="a3d63-112">検証エラー メッセージが検証エラーを発生させるソース コードの行を含める必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3d63-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="a3d63-113">.NET Framework version 2.0 でこのフィールドの値が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="a3d63-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3d63-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="a3d63-114">Requirements</span></span>  
 <span data-ttu-id="a3d63-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3d63-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d63-116">**ヘッダー:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="a3d63-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="a3d63-117">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3d63-117">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a3d63-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="a3d63-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3d63-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3d63-119">See also</span></span>

- [<span data-ttu-id="a3d63-120">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3d63-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="a3d63-121">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="a3d63-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
