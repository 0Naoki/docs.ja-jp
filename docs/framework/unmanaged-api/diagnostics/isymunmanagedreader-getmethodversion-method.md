---
title: ISymUnmanagedReader::GetMethodVersion メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f45423bb0ff4c755e657729c5725c8d9a22bde3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746764"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="81092-102">ISymUnmanagedReader::GetMethodVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="81092-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="81092-103">メソッドのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="81092-103">Gets the method version.</span></span> <span data-ttu-id="81092-104">メソッドのバージョンでは、1 から開始し、メソッドが再コンパイルされるたびに増分されます。</span><span class="sxs-lookup"><span data-stu-id="81092-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="81092-105">再コンパイルは、メソッドに変更することがなく発生します。</span><span class="sxs-lookup"><span data-stu-id="81092-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81092-106">構文</span><span class="sxs-lookup"><span data-stu-id="81092-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81092-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81092-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="81092-108">[in]バージョンを取得する方法です。</span><span class="sxs-lookup"><span data-stu-id="81092-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="81092-109">[out]メソッドのバージョンを受信する変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="81092-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81092-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="81092-110">Return Value</span></span>  
 <span data-ttu-id="81092-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="81092-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81092-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="81092-112">Requirements</span></span>  
 <span data-ttu-id="81092-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="81092-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81092-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="81092-114">See also</span></span>

- [<span data-ttu-id="81092-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81092-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
