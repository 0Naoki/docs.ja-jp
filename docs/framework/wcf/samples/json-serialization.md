---
title: JSON シリアル化
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 389bdc8b064bda9870b33a2e4c46fdf90bb7f3ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="json-serialization"></a>JSON シリアル化
このサンプルでは、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> を使用して、JavaScript Object Notation (JSON) 形式のデータをシリアル化および逆シリアル化する方法を示します。 このシリアル化エンジンによって、JSON データを [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 型のインスタンスに変換したり JSON データに戻したりすることができます。 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> では、<xref:System.Runtime.Serialization.DataContractSerializer> と同じ型をサポートしています。 JSON データ形式は、特に Asynchronous JavaScript and XML (AJAX) スタイルの Web アプリケーションを作成するときに便利です。 Windows Communication Foundation (WCF) での AJAX サポートは、ScriptManager コントロールを介して ASP.NET AJAX と共に使用に適しています。 ASP.NET AJAX を使用した Windows Communication Foundation (WCF) を使用する方法の例については、次を参照してください。、 [AJAX サンプル](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)です。  
  
> [!NOTE]
>  このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。  
  
 このサンプルでは、シリアル化および逆シリアル化を示すために、`Person` データ コントラクトを使用しています。  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 `Person` 型のインスタンスを JSON にシリアル化するには、最初に <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> を作成し、次に `WriteObject` メソッドを使用して JSON データをストリームに書き込みます。  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 メモリ ストリームには有効な JSON データが含まれています。
  
```json  
{"age":42,"name":"John"}  
```  
  
 このサンプルでは、JSON データからオブジェクトへの逆シリアル化を示します。 次に、ストリームを巻き戻し、`ReadObject` を呼び出します。  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 `p2` オブジェクトを調べることで、JSON データが正しく逆シリアル化されていることがわかります。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に、 [Windows Communication Foundation (WCF) および .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](http://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプルです。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>サンプルを設定、ビルド、および実行するには  
  
1.  ソリューションをビルドします JsonSerialization.sln」の説明に従って[Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)です。  
  
2.  作成されたコンソール アプリケーションを実行します。  
  
## <a name="see-also"></a>関連項目
