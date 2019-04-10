---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 30084143949d2243fd310448c52e6b861505ad66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191251"
---
# <a name="getcustomui"></a><span data-ttu-id="030ee-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="030ee-102">GetCustomUI</span></span>
<span data-ttu-id="030ee-103">実装されている場合に、カスタムの進行状況とエラー メッセージをホストから取得する PresentationHost.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="030ee-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="030ee-104">構文</span><span class="sxs-lookup"><span data-stu-id="030ee-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="030ee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="030ee-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="030ee-106">[out]ホストが指定した進行中のユーザー インターフェイスが含まれるアセンブリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="030ee-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="030ee-107">[out]可能であれば、進行中のホストが指定したユーザー インターフェイスであるクラスの名前、[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]ファイルと<xref:System.Windows.Controls.Page>はその最上位要素です。</span><span class="sxs-lookup"><span data-stu-id="030ee-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="030ee-108">このクラスがで指定されているアセンブリに存在する`pwzProgressAssemblyName`します。</span><span class="sxs-lookup"><span data-stu-id="030ee-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="030ee-109">[out]ホストが指定したエラーのユーザー インターフェイスが含まれるアセンブリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="030ee-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="030ee-110">[out]ホストが指定したエラーのユーザーであるクラスの名前インターフェイス、可能であれば、XAML ファイルで<xref:System.Windows.Controls.Page>はその最上位要素です。</span><span class="sxs-lookup"><span data-stu-id="030ee-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="030ee-111">このクラスがで指定されているアセンブリに存在する`pwzErrorAssemblyName`します。</span><span class="sxs-lookup"><span data-stu-id="030ee-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="030ee-112">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="030ee-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="030ee-113">HRESULT:無視されます。</span><span class="sxs-lookup"><span data-stu-id="030ee-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="030ee-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="030ee-114">Remarks</span></span>  
 <span data-ttu-id="030ee-115">ホスト アプリケーションは、PresentationHost.exe の既定のユーザー インターフェイスに準拠していない特定のテーマがあります。</span><span class="sxs-lookup"><span data-stu-id="030ee-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="030ee-116">大文字と小文字の場合は、ホスト アプリケーションを実装できます[GetCustomUI](getcustomui.md)進行状況とエラー ユーザー インターフェイスを PresentationHost.exe に戻ります。</span><span class="sxs-lookup"><span data-stu-id="030ee-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="030ee-117">PresentationHost.exe は常に呼び出さ[GetCustomUI](getcustomui.md)の既定のユーザー インターフェイスを使用する前にします。</span><span class="sxs-lookup"><span data-stu-id="030ee-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="030ee-118">この関数は、PresentationHost の初期化中に 1 回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="030ee-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="030ee-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="030ee-119">See also</span></span>

- [<span data-ttu-id="030ee-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="030ee-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
