---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: bd6d22635c4403e0526270a4ee50cf809c88989b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371069"
---
# <a name="securitybindingelement"></a><span data-ttu-id="0dee3-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="0dee3-102">SecurityBindingElement</span></span>
<span data-ttu-id="0dee3-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="0dee3-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dee3-104">構文</span><span class="sxs-lookup"><span data-stu-id="0dee3-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0dee3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0dee3-105">Methods</span></span>  
 <span data-ttu-id="0dee3-106">SecurityBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="0dee3-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0dee3-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0dee3-107">Properties</span></span>  
 <span data-ttu-id="0dee3-108">SecurityBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="0dee3-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="0dee3-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="0dee3-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="0dee3-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="0dee3-110">Data type: string</span></span>  
  
 <span data-ttu-id="0dee3-111">アクセスの種類 : 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0dee3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dee3-112">バインディングで使用するアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="0dee3-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="0dee3-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="0dee3-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="0dee3-114">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="0dee3-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="0dee3-115">アクセスの種類 : 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0dee3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dee3-116">各メッセージにタイムスタンプが含まれるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="0dee3-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="0dee3-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="0dee3-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="0dee3-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="0dee3-118">Data type: string</span></span>  
  
 <span data-ttu-id="0dee3-119">アクセスの種類 : 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0dee3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dee3-120">キーの作成に使用されるエントロピのソースです。</span><span class="sxs-lookup"><span data-stu-id="0dee3-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="0dee3-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="0dee3-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="0dee3-122">データ型 : LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="0dee3-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="0dee3-123">アクセスの種類 : 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0dee3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dee3-124">ローカル サービスに対するバインディング固有のセキュリティ プロパティです。</span><span class="sxs-lookup"><span data-stu-id="0dee3-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="0dee3-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="0dee3-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="0dee3-126">データ型: string</span><span class="sxs-lookup"><span data-stu-id="0dee3-126">Data type: string</span></span>  
  
 <span data-ttu-id="0dee3-127">アクセスの種類 : 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0dee3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dee3-128">メッセージ セキュリティで使用されるバージョンです。</span><span class="sxs-lookup"><span data-stu-id="0dee3-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="0dee3-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="0dee3-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="0dee3-130">データ型: string</span><span class="sxs-lookup"><span data-stu-id="0dee3-130">Data type: string</span></span>  
  
 <span data-ttu-id="0dee3-131">アクセスの種類 : 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="0dee3-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0dee3-132">このバインディングのセキュリティ ヘッダー内の要素の順序です。</span><span class="sxs-lookup"><span data-stu-id="0dee3-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dee3-133">要件</span><span class="sxs-lookup"><span data-stu-id="0dee3-133">Requirements</span></span>  
  
|<span data-ttu-id="0dee3-134">MOF</span><span class="sxs-lookup"><span data-stu-id="0dee3-134">MOF</span></span>|<span data-ttu-id="0dee3-135">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="0dee3-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0dee3-136">Namespace</span><span class="sxs-lookup"><span data-stu-id="0dee3-136">Namespace</span></span>|<span data-ttu-id="0dee3-137">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="0dee3-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0dee3-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dee3-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
