---
title: XML ツリー内の要素、属性、およびノードの変更
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 9567d0c6c5cd4853eeb2a86066cd1a805f20a031
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43777351"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>XML ツリー内の要素、属性、およびノードの変更
次の表は、要素、その子要素、またはその属性の変更に使用できるメソッドとプロパティについてまとめたものです。  
  
 次のメソッドは、<xref:System.Xml.Linq.XElement> を変更します。  
  
|メソッド|説明|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|要素を解析された XML に置き換えます。|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|要素のすべてのコンテンツ (子ノードおよび属性) を削除します。|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|要素の属性を削除します。|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|要素のすべてのコンテンツ (子ノードおよび属性) を置き換えます。|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|要素の属性を置き換えます。|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|属性の値を設定します。 属性が存在しない場合は作成します。 値に `null` が設定された場合は、属性を削除します。|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|子要素の値を設定します。 要素が存在しない場合は作成します。 値に `null` が設定された場合は、要素を削除します。|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|要素のコンテンツ (子ノード) を、指定したテキストに置き換えます。|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|要素の値を設定します。|  
  
 次のメソッドは、<xref:System.Xml.Linq.XAttribute> を変更します。  
  
|メソッド|説明|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|属性の値を設定します。|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|属性の値を設定します。|  
  
 次のメソッドは、<xref:System.Xml.Linq.XNode> (<xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XDocument> を含む) を変更します。  
  
|メソッド|説明|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|ノードを新しいコンテンツに置き換えます。|  
  
 次のメソッドは、<xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> または <xref:System.Xml.Linq.XDocument>) を変更します。  
  
|メソッド|説明|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|子ノードを新しいコンテンツに置き換えます。|  
  
## <a name="see-also"></a>参照

- [XML ツリーの変更 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
