---
title: '方法 : オブジェクトを逆シリアル化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: 6da8ec2b78066cd251e4ad492afd2d9d37f7b965
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863240"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="dd86a-102">方法 : オブジェクトを逆シリアル化する</span><span class="sxs-lookup"><span data-stu-id="dd86a-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="dd86a-103">オブジェクトを逆シリアル化する場合、転送形式によって、ストリーム オブジェクトとファイル オブジェクトのどちらを作成するかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="dd86a-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="dd86a-104">転送形式を決定したら、必要に応じて <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> メソッドまたは <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dd86a-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="dd86a-105">オブジェクトを逆シリアル化するには</span><span class="sxs-lookup"><span data-stu-id="dd86a-105">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="dd86a-106">逆シリアル化するオブジェクトの型を使用して、<xref:System.Xml.Serialization.XmlSerializer> を構築します。</span><span class="sxs-lookup"><span data-stu-id="dd86a-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2.  <span data-ttu-id="dd86a-107"><xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> メソッドを呼び出して、オブジェクトのレプリカを生成します。</span><span class="sxs-lookup"><span data-stu-id="dd86a-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="dd86a-108">逆シリアル化を行う際には、次の例に示すように、返されたオブジェクトを元の型にキャストする必要があります。この例では、オブジェクトをファイルに逆シリアル化しています (ストリームに逆シリアル化することもできます)。</span><span class="sxs-lookup"><span data-stu-id="dd86a-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object into a file (although it could also be deserialized into a stream).</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dd86a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd86a-109">See also</span></span>

- [<span data-ttu-id="dd86a-110">XML シリアル化の概要</span><span class="sxs-lookup"><span data-stu-id="dd86a-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
- [<span data-ttu-id="dd86a-111">方法 : オブジェクトをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="dd86a-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
