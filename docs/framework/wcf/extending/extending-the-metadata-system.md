---
title: メタデータ システムの拡張
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: d3ce7e1a228e6303be1009c7b72f4e889b40c536
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795719"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="36bbb-102">メタデータ システムの拡張</span><span class="sxs-lookup"><span data-stu-id="36bbb-102">Extending the Metadata System</span></span>
<span data-ttu-id="36bbb-103">Windows Communication Foundation (WCF) メタデータシステムは、サービスベースのアプリケーションを実装するために必要なメタデータを表すクラスとインターフェイスのグループです。</span><span class="sxs-lookup"><span data-stu-id="36bbb-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="36bbb-104">クラスを変更または拡張するか、WSDL (Web サービス記述言語) の拡張子やカスタム WS-PolicyAttachments アサーションなどのカスタム メタデータをエクスポート/インポートするインターフェイスを実装して構成します。</span><span class="sxs-lookup"><span data-stu-id="36bbb-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36bbb-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="36bbb-105">In This Section</span></span>  
 [<span data-ttu-id="36bbb-106">WCF 拡張に対するカスタム メタデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="36bbb-106">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="36bbb-107"><xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> インターフェイスを実装および使用して、カスタム ポリシー アサーションを WSDL ドキュメントに埋め込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="36bbb-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="36bbb-108">WCF 拡張に対するカスタム メタデータのインポート</span><span class="sxs-lookup"><span data-stu-id="36bbb-108">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="36bbb-109"><xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> インターフェイスを実装および使用して、WSDL ドキュメント内のカスタム ポリシー アサーションの読み取りや応答を行う方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="36bbb-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="36bbb-110">カスタム バインディングを介したメタデータの公開と取得</span><span class="sxs-lookup"><span data-stu-id="36bbb-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="36bbb-111">カスタム バインドを介してメタデータを交換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36bbb-111">Describes how to exchange metadata over custom bindings.</span></span>
