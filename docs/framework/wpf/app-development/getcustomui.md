---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88c2873a5929e25335b0c6ef64f8121e31177ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="getcustomui"></a>GetCustomUI
実装されている場合に、ホストからカスタムの進行状況とエラー メッセージを取得する PresentationHost.exe によって呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pwzProgressAssemblyName`  
  
 [out]進行中のホストが指定したユーザー インターフェイスが含まれるアセンブリへのポインター。  
  
 `pwzProgressClassName`  
  
 [out]可能であれば、実行中のホストが指定したユーザー インターフェイスであるクラスの名前、[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]ファイルと<xref:System.Windows.Controls.Page>は、最上位要素です。 このクラスがで指定されているアセンブリに存在`pwzProgressAssemblyName`です。  
  
 `pwzErrorAssemblyName`  
  
 [out]ホストが指定したエラーのユーザー インターフェイスが含まれるアセンブリへのポインター。  
  
 `pwzErrorClassName`  
  
 [out]ホストが指定したエラーのユーザーであるクラスの名前のインターフェイス、可能であればの XAML ファイル<xref:System.Windows.Controls.Page>は、最上位要素です。 このクラスがで指定されているアセンブリに存在`pwzErrorAssemblyName`です。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 HRESULT: 無視されます。  
  
## <a name="remarks"></a>コメント  
 ホスト アプリケーションに PresentationHost.exe の既定のユーザー インターフェイスが準拠していない特定のテーマがあります。 大文字と小文字の場合は、ホスト アプリケーションを実装できます[ある GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) PresentationHost.exe に、ユーザー インターフェイスで進行状況とエラーが返される。 PresentationHost.exe が常に呼び出す[ある GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)の既定のユーザー インターフェイスを使用する前にします。  
  
 この関数は PresentationHost の初期化中に 1 回呼び出されます。  
  
## <a name="see-also"></a>参照  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
