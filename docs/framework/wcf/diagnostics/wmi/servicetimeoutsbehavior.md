---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 58e872f2b15776d65bccdcc47c353ce566cd9d2f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116013"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="e253b-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="e253b-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="e253b-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="e253b-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e253b-104">構文</span><span class="sxs-lookup"><span data-stu-id="e253b-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e253b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e253b-105">Methods</span></span>  
 <span data-ttu-id="e253b-106">ServiceTimeoutsBehavior クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="e253b-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e253b-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e253b-107">Properties</span></span>  
 <span data-ttu-id="e253b-108">ServiceTimeoutsBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="e253b-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="e253b-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="e253b-109">TransactionTimeout</span></span>  
 <span data-ttu-id="e253b-110">データ型 : datetime</span><span class="sxs-lookup"><span data-stu-id="e253b-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="e253b-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="e253b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e253b-112">トランザクションを完了しなければならない期間。</span><span class="sxs-lookup"><span data-stu-id="e253b-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e253b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e253b-113">Requirements</span></span>  
  
|<span data-ttu-id="e253b-114">MOF</span><span class="sxs-lookup"><span data-stu-id="e253b-114">MOF</span></span>|<span data-ttu-id="e253b-115">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="e253b-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e253b-116">名前空間</span><span class="sxs-lookup"><span data-stu-id="e253b-116">Namespace</span></span>|<span data-ttu-id="e253b-117">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="e253b-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e253b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e253b-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
