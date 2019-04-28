---
title: 暗号化クラスの設定
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: ba11eed316e227ceae4cb5acecb2b081fa8868f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705533"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="32ab7-102">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="32ab7-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="32ab7-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]コンピューターの管理者は、既定の暗号アルゴリズムと、.NET Framework と適切に記述されたアプリケーションを使用するアルゴリズムの実装を構成します。</span><span class="sxs-lookup"><span data-stu-id="32ab7-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="32ab7-104">たとえば、暗号アルゴリズムの独自の実装を持つエンタープライズは、その実装に出荷された実装ではなく既定、[!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="32ab7-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="32ab7-105">暗号化を使用するマネージ アプリケーションは、特定の実装にバインドするように常に選択できますが、crypto の構成システムを使用して暗号化オブジェクトを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32ab7-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32ab7-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="32ab7-106">In This Section</span></span>  
 [<span data-ttu-id="32ab7-107">暗号化クラスへのアルゴリズム名の割り当て</span><span class="sxs-lookup"><span data-stu-id="32ab7-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="32ab7-108">暗号化クラスに、アルゴリズム名をマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32ab7-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="32ab7-109">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="32ab7-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="32ab7-110">暗号化アルゴリズムにオブジェクト識別子をマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32ab7-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="32ab7-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="32ab7-111">Related Sections</span></span>  
 [<span data-ttu-id="32ab7-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="32ab7-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="32ab7-113">によって提供されるサービスの暗号化の概要、[!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="32ab7-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="32ab7-114">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="32ab7-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="32ab7-115">アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="32ab7-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
