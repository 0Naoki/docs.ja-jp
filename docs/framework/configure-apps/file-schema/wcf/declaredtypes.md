---
title: '&lt;declaredTypes&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: 0fadb13d4fcfbe87eb2c08fc35323c726c0ac2a6
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146421"
---
# <a name="ltdeclaredtypesgt"></a><span data-ttu-id="2c6d3-102">&lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="2c6d3-102">&lt;declaredTypes&gt;</span></span>
<span data-ttu-id="2c6d3-103">逆シリアル化時に <xref:System.Runtime.Serialization.DataContractSerializer> が使用する既知の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-103">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="2c6d3-104">データ コントラクトと既知の型の詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-104">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="2c6d3-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="2c6d3-105">system.runtime.serialization</span></span>  
<span data-ttu-id="2c6d3-106">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="2c6d3-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="2c6d3-107">\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="2c6d3-107">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6d3-108">構文</span><span class="sxs-lookup"><span data-stu-id="2c6d3-108">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c6d3-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2c6d3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2c6d3-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c6d3-111">属性</span><span class="sxs-lookup"><span data-stu-id="2c6d3-111">Attributes</span></span>  
 <span data-ttu-id="2c6d3-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c6d3-113">子要素</span><span class="sxs-lookup"><span data-stu-id="2c6d3-113">Child Elements</span></span>  
  
|<span data-ttu-id="2c6d3-114">要素</span><span class="sxs-lookup"><span data-stu-id="2c6d3-114">Element</span></span>|<span data-ttu-id="2c6d3-115">説明</span><span class="sxs-lookup"><span data-stu-id="2c6d3-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c6d3-116">\<add></span><span class="sxs-lookup"><span data-stu-id="2c6d3-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="2c6d3-117">既知の型を必要とする型を追加します。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c6d3-118">親要素</span><span class="sxs-lookup"><span data-stu-id="2c6d3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2c6d3-119">要素</span><span class="sxs-lookup"><span data-stu-id="2c6d3-119">Element</span></span>|<span data-ttu-id="2c6d3-120">説明</span><span class="sxs-lookup"><span data-stu-id="2c6d3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c6d3-121">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="2c6d3-121">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="2c6d3-122"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c6d3-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c6d3-123">Remarks</span></span>  
 <span data-ttu-id="2c6d3-124">既知の型の詳細については、次を参照してください。 [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)と<xref:System.Runtime.Serialization.DataContractSerializer>します。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-124">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c6d3-125">例</span><span class="sxs-lookup"><span data-stu-id="2c6d3-125">Example</span></span>  
 <span data-ttu-id="2c6d3-126">宣言された型と既知の型に追加された次の XML コードを示しています、`DataContractSerializer`要素。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="2c6d3-127">この例は、追加された 3 つの型を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-127">The example shows three types being added.</span></span> <span data-ttu-id="2c6d3-128">最初の型は、"Item" という既知の型を使用する "Orders" という名前のカスタム型です。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="2c6d3-129">2 つ目の宣言型は、既知の型として <xref:System.Collections.Generic.List%601> を使用する `Item` です。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="2c6d3-130">最後の 3 つ目の宣言型は、<xref:System.Collections.Generic.Dictionary%602> です。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="2c6d3-131"><xref:System.Collections.Generic.Dictionary%602> クラスの型は、2 種類のパラメーターを持つジェネリック型です。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="2c6d3-132">最初のパラメーターはキーを表し、2 番目のパラメーターは値を表します。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="2c6d3-133">次の例は、2 番目の型 (値) の <xref:System.Collections.Generic.List%601> を既知の型の一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="2c6d3-134">`index` 属性を使用して、既知の型で使用する型パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="2c6d3-135">この場合には、"1" に設定された index 属性 (コレクションは 0 から始まる) によって値型が示されます。</span><span class="sxs-lookup"><span data-stu-id="2c6d3-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="2c6d3-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c6d3-136">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="2c6d3-137">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="2c6d3-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="2c6d3-138">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="2c6d3-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="2c6d3-139">\<add></span><span class="sxs-lookup"><span data-stu-id="2c6d3-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
