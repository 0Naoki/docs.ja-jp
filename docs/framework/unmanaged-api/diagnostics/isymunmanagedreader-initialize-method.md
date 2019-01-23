---
title: ISymUnmanagedReader::Initialize メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee68533e95deb4b6efaa9226c047599f233b3954
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494757"
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize メソッド
このリーダーが、モジュールのファイル名と共に使用すると、関連付けられるメタデータ インポーターのインターフェイスで、シンボル リーダーを初期化します。  
  
> [!NOTE]
>  このメソッドは、1 回だけ呼び出すことができ、その他のリーダー メソッドの前に呼び出す必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `importer`  
 [in]このリーダーが関連付けられるメタデータ インポーターのインターフェイス。  
  
 `filename`  
 [in]モジュールのファイル名。 使用することができます、`pIStream`パラメーター代わりにします。  
  
 `searchPath`  
 [in]検索するパス。 このパラメーターは省略できます。  
  
 `pIStream`  
 [in]ファイル ストリームは、filename パラメーターの代替として使用します。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。  
  
## <a name="remarks"></a>Remarks  
 1 つだけ指定する必要がある、`filename`または`pIStream`両方のパラメーター。 `searchPath` パラメーターは省略可能です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>関連項目
- [ISymUnmanagedReader インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
