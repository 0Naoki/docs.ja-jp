---
title: ISymUnmanagedDocument インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33213aced635549dd439cf679d89367a71baa7c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168806"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="331e2-102">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="331e2-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="331e2-103">シンボル ストアによって参照されるドキュメントを表します。</span><span class="sxs-lookup"><span data-stu-id="331e2-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="331e2-104">ドキュメントは、uniform resource locator (URL) と GUID のドキュメントの種類によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="331e2-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="331e2-105">URL を使用して格納する方法に関係なく、ドキュメントを検索でき、ドキュメントの種類の GUID。</span><span class="sxs-lookup"><span data-stu-id="331e2-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="331e2-106">ドキュメントのソースをシンボル ストアに格納でき、このインターフェイスを通じて取得できます。</span><span class="sxs-lookup"><span data-stu-id="331e2-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="331e2-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-107">Methods</span></span>  
  
|<span data-ttu-id="331e2-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-108">Method</span></span>|<span data-ttu-id="331e2-109">説明</span><span class="sxs-lookup"><span data-stu-id="331e2-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="331e2-110">FindClosestLine メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="331e2-111">行を指定したシーケンス ポイントができない可能性がありますが、このドキュメントでは、シーケンス ポイントである最も近い行を返します。</span><span class="sxs-lookup"><span data-stu-id="331e2-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="331e2-112">GetCheckSum メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="331e2-113">チェックサムを取得します。</span><span class="sxs-lookup"><span data-stu-id="331e2-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="331e2-114">GetCheckSumAlgorithmId メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="331e2-115">チェックサム アルゴリズム識別子を取得またはチェックサムがない場合は、すべてゼロの GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="331e2-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="331e2-116">GetDocumentType メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="331e2-117">このドキュメントのドキュメントの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="331e2-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="331e2-118">GetLanguage メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="331e2-119">このドキュメントの言語識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="331e2-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="331e2-120">GetLanguageVendor メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="331e2-121">このドキュメントの言語の販売元を取得します。</span><span class="sxs-lookup"><span data-stu-id="331e2-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="331e2-122">GetSourceLength メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="331e2-123">埋め込まれたソースの長さをバイト数で取得します。</span><span class="sxs-lookup"><span data-stu-id="331e2-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="331e2-124">GetSourceRange メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="331e2-125">指定されたバッファーに埋め込みのソースの指定した範囲を返します。</span><span class="sxs-lookup"><span data-stu-id="331e2-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="331e2-126">GetURL メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="331e2-127">このドキュメントの URL を返します。</span><span class="sxs-lookup"><span data-stu-id="331e2-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="331e2-128">HasEmbeddedSource メソッド</span><span class="sxs-lookup"><span data-stu-id="331e2-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="331e2-129">返します`true`ドキュメントが、デバッグのシンボルに埋め込まれたソースを返しますそれ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="331e2-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="331e2-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="331e2-130">See also</span></span>

- [<span data-ttu-id="331e2-131">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="331e2-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
