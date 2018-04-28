---
title: データ コントラクト リゾルバーの使用
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 20ef713c67ee21aa8f7a92975bc6e6ce8798a087
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
---
# <a name="using-a-data-contract-resolver"></a>データ コントラクト リゾルバーの使用
データ コントラクト リゾルバーでは、既知の型を動的に構成できます。 データ コントラクトが予期しない型をシリアル化または逆シリアル化するときには、既知の型が必要です。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 、「 [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)サービスからエクスポートするときに、CLR 型を XSD にマッピングします。 通常、既知の型は静的に指定されます。 これは、操作を実装する間に操作が受け取る可能性のあるすべての型を把握しておく必要があることを意味します。 これが当てはまらず、既知の型を動的に指定できることが重要である場合もあります。  
  
## <a name="creating-a-data-contract-resolver"></a>データ コントラクト リゾルバーの作成  
 データ コントラクト リゾルバーを作成する際には、2 つのメソッド、<xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> および <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> を実装します。 これらの 2 つのメソッドは、シリアル化および逆シリアル化の際に使用されるコールバックを実装します。 <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> メソッドはシリアル化の際に呼び出されて、データ コントラクト型を受け取り、それを `xsi:type` の名前および名前空間にマップします。 <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> メソッドは逆シリアル化の際に呼び出されて、`xsi:type` の名前および名前空間を受け取り、それをデータ コントラクト型に解決します。 これらのメソッドの両方には `knownTypeResolver` パラメーターがあり、これを使用して、既定の既知の型のリゾルバーを実装で使用できます。  
  
 次の例は、<xref:System.Runtime.Serialization.DataContractResolver> を実装し、データ コントラクト型 `Customer` から派生した `Person` という名前のデータ コントラクト型との間でマッピングを行う方法を示しています。  
  
```csharp  
public class MyCustomerResolver : DataContractResolver  
{  
    public override bool TryResolveType(Type dataContractType, Type declaredType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        if (dataContractType == typeof(Customer))  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add("SomeCustomer");  
            typeNamespace = dictionary.Add("http://tempuri.com");  
            return true;  
        }  
        else  
        {  
            return knownTypeResolver.TryResolveType(dataContractType, declaredType, null, out typeName, out typeNamespace);  
        }  
    }  
  
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        if (typeName == "SomeCustomer" && typeNamespace == "http://tempuri.com")  
        {  
            return typeof(Customer);  
        }  
        else  
        {  
            return knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        }  
    }  
}  
```  
  
 <xref:System.Runtime.Serialization.DataContractResolver> を定義したら、次の例に示すように、それを <xref:System.Runtime.Serialization.DataContractSerializer> コンストラクターに渡して使用できます。  
  
```  
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 次の例に示すように、<xref:System.Runtime.Serialization.DataContractSerializer> を、<xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A> メソッドまたは <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A> メソッドへの呼び出しで指定できます。  
  
```  
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 また、次の例に示すように、<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> で設定することもできます。  
  
```  
ServiceHost host = new ServiceHost(typeof(MyService));  
  
ContractDescription cd = host.Description.Endpoints[0].Contract;  
OperationDescription myOperationDescription = cd.Operations.Find("Echo");  
  
DataContractSerializerOperationBehavior serializerBehavior = myOperationDescription.Behaviors.Find<DataContractSerializerOperationBehavior>();  
if (serializerBehavior == null)  
{  
    serializerBehavior = new DataContractSerializerOperationBehavior(myOperationDescription);  
    myOperationDescription.Behaviors.Add(serializerBehavior);  
}  
  
SerializerBehavior.DataContractResolver = new MyCustomerResolver();  
```  
  
 サービスに適用できる属性を実装して、データ コントラクト リゾルバーを宣言によって指定できます。  詳細については、次を参照してください。、 [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md)サンプルです。 このサンプルは"KnownAssembly"と呼ばれる属性を実装してカスタム データ コントラクト リゾルバー サービスの動作を追加します。  
  
## <a name="see-also"></a>関連項目  
 [既知のデータ コントラクト型](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [DataContractSerializer サンプル](../../../../docs/framework/wcf/samples/datacontractserializer-sample.md)  
 [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md)
