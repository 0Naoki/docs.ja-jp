---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: afe84db3d4df8914ff1ed001b064439d581ead89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085396"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="b0ed7-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="b0ed7-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="b0ed7-103">サービスが正常に閉じられず、中止された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="b0ed7-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b0ed7-104">説明</span><span class="sxs-lookup"><span data-stu-id="b0ed7-104">Description</span></span>  
 <span data-ttu-id="b0ed7-105">このエラー コードはログ ファイルにのみ記録されます。</span><span class="sxs-lookup"><span data-stu-id="b0ed7-105">This error code only appears in the log file.</span></span> <span data-ttu-id="b0ed7-106">通常は、Abort を既に呼び出した後でサービスを閉じようとした場合などの、プログラミング エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="b0ed7-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b0ed7-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0ed7-107">Troubleshooting</span></span>  
 <span data-ttu-id="b0ed7-108">アプリケーションのソース コードをチェックしてください。</span><span class="sxs-lookup"><span data-stu-id="b0ed7-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ed7-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0ed7-109">See also</span></span>

- [<span data-ttu-id="b0ed7-110">トレース</span><span class="sxs-lookup"><span data-stu-id="b0ed7-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b0ed7-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0ed7-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b0ed7-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="b0ed7-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
