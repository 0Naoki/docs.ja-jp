---
title: ベスト プラクティス:中継局
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 0bd553486bfb89a0ec14c42a1bb7d2ed9c4c540d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131730"
---
# <a name="best-practices-intermediaries"></a><span data-ttu-id="9449e-102">ベスト プラクティス:中継局</span><span class="sxs-lookup"><span data-stu-id="9449e-102">Best Practices: Intermediaries</span></span>
<span data-ttu-id="9449e-103">中継局のサービス側のチャネルが適切に閉じられていることを確認するために中継局を呼び出すときは、エラーが正しく処理されるよう注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9449e-103">Care must be taken to handle faults correctly when calling intermediaries to make sure service side channels on the intermediary are closed properly.</span></span>  
  
 <span data-ttu-id="9449e-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9449e-104">Consider the following scenario.</span></span> <span data-ttu-id="9449e-105">クライアントが中継局を呼び出すと、中継局はバックエンド サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9449e-105">A client makes a call to an intermediary which then calls a back-end service.</span></span>  <span data-ttu-id="9449e-106">バックエンド サービスはエラー コントラクトを定義しないので、そのサービスからスローされるエラーはすべて型指定されていないエラーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="9449e-106">The back-end service defines no fault contract, so any fault thrown from that service will be treated as an un-typed fault.</span></span>  <span data-ttu-id="9449e-107">バックエンド サービスがスローされます、 <xref:System.ApplicationException> WCF が正しく、サービス側チャネルを中止します。</span><span class="sxs-lookup"><span data-stu-id="9449e-107">The back-end service throws an <xref:System.ApplicationException> and WCF correctly aborts the service-side channel.</span></span> <span data-ttu-id="9449e-108"><xref:System.ApplicationException> が <xref:System.ServiceModel.FaultException> として中継局にスローされます。</span><span class="sxs-lookup"><span data-stu-id="9449e-108">The <xref:System.ApplicationException> then surfaces as a <xref:System.ServiceModel.FaultException> that is thrown to the intermediary.</span></span> <span data-ttu-id="9449e-109">中継局は <xref:System.ApplicationException> を再スローします。</span><span class="sxs-lookup"><span data-stu-id="9449e-109">The intermediary re-throws the <xref:System.ApplicationException>.</span></span> <span data-ttu-id="9449e-110">WCF はこれを中継局からの型指定されていないエラーとして解釈し、クライアントに転送します。</span><span class="sxs-lookup"><span data-stu-id="9449e-110">WCF interprets this as an un-typed fault from the intermediary and forwards it on to the client.</span></span> <span data-ttu-id="9449e-111">エラーを受け取ると、中継局とクライアントのクライアント側チャネルはエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="9449e-111">Upon receiving the fault, both the intermediary and the client fault their client-side channels.</span></span> <span data-ttu-id="9449e-112">ただし、WCF にはエラーが致命的であることが通知されていないため、中継局のサービス側チャネルは開いたままです。</span><span class="sxs-lookup"><span data-stu-id="9449e-112">The intermediary’s service-side channel however remains open because WCF doesn’t know the fault is fatal.</span></span>  
  
 <span data-ttu-id="9449e-113">このシナリオのベスト プラクティスとしては、次のコード スニペットに示すように、サービスからスローされたエラーが致命的かどうかを検出し、致命的である場合は、中継局のサービス側チャネルでエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="9449e-113">The best practice in this scenario is to detect if the fault coming from the service is fatal and if so the intermediary should fault its service-side channel as shown in the following code snippet.</span></span>  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9449e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9449e-114">See also</span></span>

- [<span data-ttu-id="9449e-115">WCF エラー処理</span><span class="sxs-lookup"><span data-stu-id="9449e-115">WCF Error Handling</span></span>](../../../docs/framework/wcf/wcf-error-handling.md)
- [<span data-ttu-id="9449e-116">コントラクトおよびサービスのエラーの指定と処理</span><span class="sxs-lookup"><span data-stu-id="9449e-116">Specifying and Handling Faults in Contracts and Services</span></span>](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
