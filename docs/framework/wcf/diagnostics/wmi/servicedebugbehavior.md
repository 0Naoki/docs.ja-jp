---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: d6f0e4741aa10bff450a29cfd7a9e63e226c6495
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498883"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="379e9-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="379e9-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="379e9-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="379e9-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="379e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="379e9-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="379e9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="379e9-105">Methods</span></span>  
 <span data-ttu-id="379e9-106">ServiceDebugBehavior クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="379e9-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="379e9-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="379e9-107">Properties</span></span>  
 <span data-ttu-id="379e9-108">ServiceDebugBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="379e9-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="379e9-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="379e9-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="379e9-110">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="379e9-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="379e9-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="379e9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="379e9-112">`HttpGetUrl` 属性によって制御されるアドレスで、サービスが WSDL を公開するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="379e9-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="379e9-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="379e9-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="379e9-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="379e9-114">Data type: string</span></span>  
  
 <span data-ttu-id="379e9-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="379e9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="379e9-116">HTTP を使用した取得のために、サービス WSDL が公開される場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="379e9-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="379e9-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="379e9-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="379e9-118">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="379e9-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="379e9-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="379e9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="379e9-120">`HttpsGetUrl` 属性によって制御されるアドレスで、サービスが HTTPS を介して WSDL を公開するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="379e9-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="379e9-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="379e9-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="379e9-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="379e9-122">Data type: string</span></span>  
  
 <span data-ttu-id="379e9-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="379e9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="379e9-124">HTTPS を使用した取得のために、サービス WSDL が公開される場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="379e9-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="379e9-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="379e9-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="379e9-126">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="379e9-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="379e9-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="379e9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="379e9-128">デバッグの目的でクライアントに返される SOAP エラーの詳細に、マネージド例外情報を含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="379e9-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="379e9-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="379e9-129">Requirements</span></span>  
  
|<span data-ttu-id="379e9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="379e9-130">MOF</span></span>|<span data-ttu-id="379e9-131">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="379e9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="379e9-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="379e9-132">Namespace</span></span>|<span data-ttu-id="379e9-133">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="379e9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="379e9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="379e9-134">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
