---
title: ISymUnmanagedNamespace::GetNamespaces メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a874c1493e1f8aaa18354de26905fabd3a793129
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674545"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a>ISymUnmanagedNamespace::GetNamespaces メソッド
この名前空間の子を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cNameSpaces`  
 [in]A`ULONG32`のサイズを示す、`namespaces`配列。  
  
 `pcNameSpaces`  
 [out]ポインターを`ULONG32`名前空間の格納に必要なバッファーの文字のサイズを受け取る。  
  
 `namespaces`  
 [out]名前空間を格納しているバッファーへのポインター。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>関連項目
- [ISymUnmanagedNamespace インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
