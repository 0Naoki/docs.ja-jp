---
title: "署名は、カスタム ヘッダーを作成して、または暗号化されました。"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ac43be1978a2a6e80b08e0c4bcd5e0e92043719e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a>署名は、カスタム ヘッダーを作成して、または暗号化されました。
WCF クライアントを使用して WCF 以外のサービスを呼び出す場合、状況によっては、カスタム SOAP ヘッダーが必要です。 WCF には正規化のバグがあり、署名および暗号化されたカスタム ヘッダーは、WCF 以外のサービスで使用できません。 この問題は、既定の XML 名前空間に対する正規化の誤りが原因で発生します。 この問題が生じるのは、署名または暗号化、あるいはその両方が行われたカスタム ヘッダーを持つ、WCF 以外のサービスを呼び出す場合のみです。  サービスは、受信したメッセージに署名または暗号化、あるいはその両方が行われたカスタム ヘッダーが含まれている場合、署名を検証できません。 この回避策では正規化のバグを回避し、WCF 以外のサービスとの相互運用が可能になりますが、WCF サービスとの相互運用性は妨げられません。  
  
## <a name="defining-the-custom-header"></a>カスタム ヘッダーの定義  
 カスタム ヘッダーは、メッセージ コントラクトを定義し、ヘッダーとして送信するメンバーを <xref:System.ServiceModel.MessageHeaderAttribute> 属性を使用してマークすることで定義されます。 正規化のバグを回避するには、XML シリアライザーが既定の名前空間の宣言ではなくプレフィックスによってカスタム ヘッダーの名前空間を宣言する必要があります。 次のコードは、メッセージ ヘッダーとして使用されるデータ型を正しい名前空間宣言で定義する方法を示します。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("svcutil", "3.0.4506.648")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://www.example.org/getMessage/")]  
public partial class msgHeaderElement  
{  
   // Define the XML namespace and force it to use an ‘h’ prefix  
    [System.Xml.Serialization.XmlNamespaceDeclarations]  
    public System.Xml.Serialization.XmlSerializerNamespaces _xsns = new System.Xml.Serialization.XmlSerializerNamespaces(new System.Xml.XmlQualifiedName[] { new System.Xml.XmlQualifiedName("h", "http://www.example.org/getMessage/") });  
  
    private string msgHeaderInputField;  
  [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified, Order=0)]  
    public string msgHeaderInput  
    {  
        get  
        {  
            return this.msgHeaderInputField;  
        }  
        set  
        {  
            this.msgHeaderInputField = value;  
        }  
    }  
}  
```  
  
 このコードでは、XML シリアライザーによってシリアル化される `msgHeaderElement` という新しい型を宣言しています。 この型のインスタンスがシリアル化されると、名前空間が "h" プレフィックスで定義されるため、正規化のバグが回避されます。  この後、次の例に示すように、メッセージ コントラクトによって `msgHeaderElement` のインスタンスを定義し、<xref:System.ServiceModel.MessageHeaderAttribute> 属性でそのインスタンスをマークします。  
  
```  
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [既定のメッセージ コントラクト](../../../../docs/framework/wcf/samples/default-message-contract.md)  
 [メッセージ コントラクト](../../../../docs/framework/wcf/samples/message-contracts.md)  
 [メッセージ コントラクトの使用](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
