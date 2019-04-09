---
title: 暗号化アルゴリズムへのオブジェクト ID の割り当て
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: e035ff04a70a441f7f64bbc230ba6d8036fb2ace
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130612"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="4527d-102">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="4527d-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="4527d-103">データが 1 つのプログラムから別の送信時いない改ざんデジタル署名を確認します。</span><span class="sxs-lookup"><span data-stu-id="4527d-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="4527d-104">通常、デジタル署名がハッシュに署名するデータの数学関数を適用することによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="4527d-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="4527d-105">署名のハッシュ値を書式設定時に、一部のデジタル署名アルゴリズムは、書式設定操作の一部として ASN.1 オブジェクト識別子 (OID) を追加します。</span><span class="sxs-lookup"><span data-stu-id="4527d-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="4527d-106">OID は、ハッシュを計算に使用されたアルゴリズムを識別します。</span><span class="sxs-lookup"><span data-stu-id="4527d-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="4527d-107">アルゴリズムは、カスタム アルゴリズムを使用する暗号化メカニズムを拡張するオブジェクトの識別子にマップできます。</span><span class="sxs-lookup"><span data-stu-id="4527d-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="4527d-108">次の例では、新しいハッシュ アルゴリズムにオブジェクト識別子をマップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4527d-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="4527d-109">[ \<OidEntry > 要素](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)2 つの属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4527d-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="4527d-110">**OID**属性は、オブジェクトの識別番号。</span><span class="sxs-lookup"><span data-stu-id="4527d-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="4527d-111">**名前**属性の値が、**名前**属性を[ \<nameEntry > 要素](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="4527d-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="4527d-112">オブジェクト識別子は、簡易名にマップできる前に、アルゴリズム名からクラスへのマッピングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4527d-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4527d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4527d-113">See also</span></span>

- [<span data-ttu-id="4527d-114">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="4527d-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="4527d-115">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="4527d-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
