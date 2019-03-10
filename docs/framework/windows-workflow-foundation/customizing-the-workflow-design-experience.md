---
title: ワークフロー デザイン操作のカスタマイズ
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 2d6ef24d00baa4df6dfc8e0af69c1d489b79a41f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724659"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="c32c7-102">ワークフロー デザイン操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c32c7-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="c32c7-103">
  [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] では、カスタム アクティビティを設計するシナリオや [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]を再ホストするシナリオが大幅に簡略化されました。</span><span class="sxs-lookup"><span data-stu-id="c32c7-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="c32c7-104">開発も配置も簡単になり、柔軟性も向上しました。</span><span class="sxs-lookup"><span data-stu-id="c32c7-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="c32c7-105">キーのインフラストラクチャの変更は、新しいアクティビティ デザイナー プログラミング モデルで Windows Presentation Foundation (WPF) とが構築されています。</span><span class="sxs-lookup"><span data-stu-id="c32c7-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="c32c7-106">そのため、アクティビティ デザイナーを宣言によって定義することや、他のアプリケーションに[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]を再ホストすることが比較的簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="c32c7-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="c32c7-107">再ホストするときに、カスタム式エディターを開発して、IntelliSense や簡略化された式ドメインをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="c32c7-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="c32c7-108">Windows Communication Foundation (WCF) との統合は、ワークフロー サービスの使用よりシームレスになっています。</span><span class="sxs-lookup"><span data-stu-id="c32c7-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="c32c7-109">カスタム アクティビティ デザイナーおよびモデル アイテム ツリーを使用して、再ホストされたワークフロー デザイナーのデザイン時の操作を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="c32c7-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c32c7-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c32c7-110">In This Section</span></span>

 [<span data-ttu-id="c32c7-111">カスタム アクティビティ デザイナーおよびテンプレートの使用</span><span class="sxs-lookup"><span data-stu-id="c32c7-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="c32c7-112">新しいカスタム アクティビティ デザイナーおよびテンプレートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c32c7-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="c32c7-113">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="c32c7-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="c32c7-114">再ホストする方法について説明します、[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]検証エラーを表示する方法と Visual Studio の外部でします。</span><span class="sxs-lookup"><span data-stu-id="c32c7-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="c32c7-115">カスタム式エディターの使用</span><span class="sxs-lookup"><span data-stu-id="c32c7-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="c32c7-116">Visual Studio 2010 の外部で再ホストされたワークフロー デザイナーで使用するカスタム式エディターを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c32c7-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="c32c7-117">参照</span><span class="sxs-lookup"><span data-stu-id="c32c7-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="c32c7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c32c7-118">See also</span></span>

- [<span data-ttu-id="c32c7-119">Windows Workflow Foundation の拡張</span><span class="sxs-lookup"><span data-stu-id="c32c7-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="c32c7-120">デザイナー</span><span class="sxs-lookup"><span data-stu-id="c32c7-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="c32c7-121">カスタム アクティビティ デザイナー</span><span class="sxs-lookup"><span data-stu-id="c32c7-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="c32c7-122">デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="c32c7-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)