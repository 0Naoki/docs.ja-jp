---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 58eb2a9fd9017aaf9966644180936f5871e086d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613897"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="1b4f4-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="1b4f4-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="1b4f4-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="1b4f4-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b4f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b4f4-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1b4f4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1b4f4-105">Methods</span></span>  
 <span data-ttu-id="1b4f4-106">ServiceAuthorizationBehavior クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="1b4f4-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1b4f4-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1b4f4-107">Properties</span></span>  
 <span data-ttu-id="1b4f4-108">ServiceAuthorizationBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1b4f4-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="1b4f4-109">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="1b4f4-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="1b4f4-110">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="1b4f4-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="1b4f4-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1b4f4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b4f4-112">受信メッセージによって提供される資格情報を使用してサービスが偽装を試みるかどうかを制御する値。</span><span class="sxs-lookup"><span data-stu-id="1b4f4-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="1b4f4-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="1b4f4-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="1b4f4-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1b4f4-114">Data type: string</span></span>  
  
 <span data-ttu-id="1b4f4-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1b4f4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b4f4-116">サーバーでの操作を実行するために使用されるプリンシパル。</span><span class="sxs-lookup"><span data-stu-id="1b4f4-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="1b4f4-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="1b4f4-117">RoleProvider</span></span>  
 <span data-ttu-id="1b4f4-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1b4f4-118">Data type: string</span></span>  
  
 <span data-ttu-id="1b4f4-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1b4f4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b4f4-120">ASP.NET ロール プロバイダーの名前。</span><span class="sxs-lookup"><span data-stu-id="1b4f4-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="1b4f4-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="1b4f4-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="1b4f4-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1b4f4-122">Data type: string</span></span>  
  
 <span data-ttu-id="1b4f4-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1b4f4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b4f4-124">カスタム承認で使用される承認マネージャー。</span><span class="sxs-lookup"><span data-stu-id="1b4f4-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b4f4-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="1b4f4-125">Requirements</span></span>  
  
|<span data-ttu-id="1b4f4-126">MOF</span><span class="sxs-lookup"><span data-stu-id="1b4f4-126">MOF</span></span>|<span data-ttu-id="1b4f4-127">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="1b4f4-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1b4f4-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="1b4f4-128">Namespace</span></span>|<span data-ttu-id="1b4f4-129">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="1b4f4-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b4f4-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b4f4-130">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
