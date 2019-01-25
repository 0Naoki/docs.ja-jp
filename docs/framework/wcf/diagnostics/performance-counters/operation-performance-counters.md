---
title: 操作パフォーマンス カウンター
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 16608132c6557f8612d42402a2cb2c49fcc29637
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566090"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="1615a-102">操作パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="1615a-102">Operation Performance Counters</span></span>
<span data-ttu-id="1615a-103">操作パフォーマンス カウンターは、パフォーマンス モニター (Perfmon.exe) を使用して表示した場合、`ServiceModelOperation 4.0.0.0` パフォーマンス オブジェクトの下にあります。</span><span class="sxs-lookup"><span data-stu-id="1615a-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="1615a-104">それぞれの操作に個別のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="1615a-104">Each operation has an individual instance.</span></span> <span data-ttu-id="1615a-105">つまり、指定したコントラクトに 10 の操作がある場合、10 の操作カウンター インスタンスがそのコントラクトに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="1615a-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="1615a-106">オブジェクトのインスタンスには次のパターンの名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="1615a-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="1615a-107">このカウンターにより呼び出しがどのように使用されている、操作がどれほど効率的に実行されているかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="1615a-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1615a-108">パフォーマンス カウンターのインスタンス名の長さには制限があります。</span><span class="sxs-lookup"><span data-stu-id="1615a-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="1615a-109">Windows Communication Foundation (WCF) のカウンター インスタンス名は、最大長を超えています、WCF はインスタンス名の一部をハッシュ値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1615a-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1615a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1615a-110">See also</span></span>
- [<span data-ttu-id="1615a-111">パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="1615a-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
