---
title: '方法: DataContractSerializer の使用 (Visual Basic) をシリアル化します。'
ms.date: 07/20/2015
ms.assetid: ecaea518-8a0f-4249-b4e5-9b3fb0cdd8ad
ms.openlocfilehash: cde857e1883d822b442b51c2931fd2fb92c24247
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714322"
---
# <a name="how-to-serialize-using-datacontractserializer-visual-basic"></a><span data-ttu-id="e1244-102">方法: DataContractSerializer の使用 (Visual Basic) をシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="e1244-102">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>
<span data-ttu-id="e1244-103">このトピックでは、<xref:System.Runtime.Serialization.DataContractSerializer> を使用してシリアル化および逆シリアル化を行う例について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1244-103">This topic shows an example that serializes and deserializes using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1244-104">例</span><span class="sxs-lookup"><span data-stu-id="e1244-104">Example</span></span>  
 <span data-ttu-id="e1244-105">次の例では、<xref:System.Xml.Linq.XElement> オブジェクトを含んでいる多数のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1244-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e1244-106">次に、それらのオブジェクトをテキスト ファイルにシリアル化し、テキスト ファイルから逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="e1244-106">It then serializes them to text files, and then deserializes them from the text files.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Linq  
Imports System.IO  
Imports System.Runtime.Serialization  
  
Public Class XLinqTest  
    Shared Sub Main()  
        Test(Of XElement)(CreateXElement())  
        Test(Of XElementContainer)(New XElementContainer())  
        Test(Of XElementNullContainer)(New XElementNullContainer())  
    End Sub  
  
    Public Shared Sub Test(Of T)(ByRef obj)  
        Dim s As DataContractSerializer = New DataContractSerializer(GetType(T))  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Create)  
            Console.WriteLine("Testing for type: {0}", GetType(T))  
            s.WriteObject(fs, obj)  
        End Using  
  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Open)  
            Dim s2 As Object = s.ReadObject(fs)  
            If s2 Is Nothing Then  
                Console.WriteLine("  Deserialized object is null (Nothing in VB)")  
            Else  
                Console.WriteLine("  Deserialized type: {0}", s2.GetType())  
            End If  
        End Using  
    End Sub  
  
    Public Shared Function CreateXElement() As XElement  
        Return New XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"))  
    End Function  
End Class  
  
<DataContract()> _  
Public Class XElementContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementContainer()  
        member = XLinqTest.CreateXElement()  
    End Sub  
End Class  
  
<DataContract()> _  
Public Class XElementNullContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementNullContainer()  
        member = Nothing  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="e1244-107">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e1244-107">This example produces the following output:</span></span>  
  
```  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1244-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1244-108">See also</span></span>
- [<span data-ttu-id="e1244-109">XElement オブジェクト (Visual Basic) を含むオブジェクト グラフをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="e1244-109">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)
