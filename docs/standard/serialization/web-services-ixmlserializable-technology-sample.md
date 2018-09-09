---
title: Web サービス IXmlSerializable の技術サンプル
ms.date: 03/30/2017
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
ms.openlocfilehash: 343755c062fc13891d84131a5f7682e2e1466a5a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252793"
---
# <a name="web-services-ixmlserializable-technology-sample"></a>Web サービス IXmlSerializable の技術サンプル
[サンプルのダウンロード](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 このサンプルでは、<xref:System.Xml.Serialization.IXmlSerializable> を使用して、ASP.NET Web サービスでカスタム型のシリアル化を制御する方法を示します。  
  
### <a name="to-build-the-sample-using-visual-studio"></a>Visual Studio を使用してサンプルをビルドするには  
  
1.  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] を起動し、**[ファイル]** メニューの **[新しい Web サイト]** をクリックします。  
  
2.  **[新しい Web サイト]** ダイアログ ボックスの左ペインで、目的のプログラミング言語を選択し、右ペインの **[ASP.NET Web サービス]** をクリックします。  
  
3.  Web サービスの名前として、「**IXmlSerializable**」と入力します。  
  
4.  ソリューション エクスプローラー ウィンドウで、Service.asmx のアイコンを右クリックし、**[削除]** をクリックします。この手順を Service.asmx Codebehind ファイルに対して繰り返します。  
  
5.  プロジェクト ディレクトリを右クリックし、**[既存項目の追加]** をクリックします。 ダイアログ ボックスで、言語固有のディレクトリにある Service サブディレクトリに移動します。  
  
6.  Service.asmx をクリックします。この手順を Service.asmx Codebehind ファイルに対して繰り返します。  
  
7.  [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]を開き、上記の手順 3. で作成した IXmlSerializable ディレクトリを含むディレクトリに移動します。  
  
8.  IXmlSerializable ディレクトリを右クリックし、**[共有とセキュリティ]** をクリックします。  
  
9. [Web 共有] タブで、**[このフォルダーを共有する]** をクリックし、名前 IXmlSerializable など既定の設定を確認します。  
  
10. **[OK]** をクリックします。  
  
### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  Web ブラウザー ウィンドウを開き、アドレス バーをクリックします。  
  
2.  型 **http://localhost/IXmlSerializable/Service.asmx**します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Xml.Serialization.IXmlSerializable>  
- <xref:System.Xml.Serialization>  
- <xref:System.Xml.XmlConvert>  
- <xref:System.Xml.XmlQualifiedName>  
- <xref:System.Xml.XmlReader>  
- <xref:System.Xml.Schema.XmlSchema>  
- <xref:System.Xml.Schema.XmlSchemaSet>  
- <xref:System.Xml.XmlUrlResolver>  
- <xref:System.Xml.XmlWriter>
