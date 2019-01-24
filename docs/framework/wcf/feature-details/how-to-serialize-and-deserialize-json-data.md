---
title: '方法: および JSON データを逆シリアル化'
ms.date: 03/30/2017
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 797b29fd7ddecd3e3ed85f8cb3a6df93044942ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704343"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>方法: および JSON データを逆シリアル化
JSON (JavaScript Object Notation) は、クライアント ブラウザーと AJAX 対応の Web サービスとの間で、少量のデータを高速に交換できる効率的なデータ エンコード形式です。  
  
 ここでは、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> を使用して .NET 型のオブジェクトを JSON エンコードされたデータにシリアル化し、この JSON 形式のデータを .NET 型のインスタンスに戻すために逆シリアル化する方法について説明します。 この例では、ユーザー定義された `Person` 型のシリアル化と逆シリアル化を示すためにデータ コントラクトを使用します。  
  
 通常、JSON のシリアル化および逆シリアル化が自動的に処理 Windows Communication Foundation (WCF) によって AJAX 対応エンドポイント経由で公開されているサービス操作でデータ コントラクト型を使用する場合。 ただし、特定の場合においては JSON データを直接処理する必要があります。このトピックでは、このようなシナリオについて説明します。  
  
> [!NOTE]
>  サーバー上で送信応答のシリアル化中にエラーが発生した場合、または応答操作がなんらかの理由で例外をスローした場合、エラーにより応答がクライアントに戻らないことがあります。  
  
 このトピックではに基づいて、 [JSON のシリアル化](../../../../docs/framework/wcf/samples/json-serialization.md)サンプル。  
  
### <a name="to-define-the-data-contract-for-a-person"></a>Person のデータ コントラクトを定義するには  
  
1.  クラスに `Person` をアタッチし、シリアル化するメンバーに <xref:System.Runtime.Serialization.DataContractAttribute> 属性をアタッチすることで、<xref:System.Runtime.Serialization.DataMemberAttribute> のデータ コントラクトを定義します。 データ コントラクトの詳細については、次を参照してください。 [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md)します。  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a>Person 型のインスタンスを JSON にシリアル化するには  
  
1.  `Person` 型のインスタンスを作成します。  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  `Person` を使用して、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> オブジェクトをメモリ ストリームにシリアル化します。  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  JSON データをストリームに書き込むには、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> メソッドを使用します。  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  JSON の出力を表示します。  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>JSON から Person 型のインスタンスに逆シリアル化するには  
  
1.  `Person` の <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> メソッドを使用して、JSON エンコードされたデータを <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> の新しいインスタンスに逆シリアル化します。  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  結果を表示します。  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a>例  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  JSON シリアライザーは、次のサンプル コードに示すように、データ コントラクターの複数のメンバーが同じ名前である場合、シリアル化例外をスローします。  
  
```csharp  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}

[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a>関連項目
- [スタンドアロン JSON のシリアル化](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [JSON などのデータ転送形式のサポート](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
