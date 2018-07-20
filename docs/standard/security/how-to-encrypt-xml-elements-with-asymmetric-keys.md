---
title: '方法 : 非対称キーで XML 要素を暗号化する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- AES algorithm
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys [.NET Framework]
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- key containers
- Advanced Encryption Standard algorithm
- Rijndael
- encryption [.NET Framework], asymmetric keys
ms.assetid: a164ba4f-e596-4bbe-a9ca-f214fe89ed48
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6840a9005aaca4805252298e1ceaf7e51f38971
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591461"
---
# <a name="how-to-encrypt-xml-elements-with-asymmetric-keys"></a>方法 : 非対称キーで XML 要素を暗号化する
<xref:System.Security.Cryptography.Xml> 名前空間のクラスを使用して、XML ドキュメント内の要素を暗号化することができます。  XML 暗号化は、データが簡単に読み取られる心配なく、暗号化された XML データを交換または保存する標準的な方法です。  標準の XML 暗号化の詳細については、仕様を参照して、World Wide Web Consortium (W3C) XML の暗号化にあるに対して http://www.w3.org/TR/xmldsig-core/ です。  
  
 XML の暗号化を使用すると、任意の XML 要素またはドキュメントを、暗号化された XML データを含む <`EncryptedData`> 要素があるドキュメントに置き換えることができます。  また、<`EncryptedData`> 要素には、暗号化時に使用されたキーとプロセスに関する情報が含まれているサブ要素を含めることもできます。  XML 暗号化を使用すると、ドキュメントに複数の暗号化された要素を含められるだけでなく、要素を複数回暗号化することができます。  この手順のコード例は、<`EncryptedData`> 要素および後の復号化時に使用するいくつかの他のサブ要素の作成方法を示しています。  
  
 この例では、2 つのキーを使用して XML 要素を暗号化します。  RSA の公開キーと秘密キーのペアを生成し、キーのペアをセキュリティで保護されたキー コンテナーに保存します。  この例では、Rijndael アルゴリズムとも呼ばれる Advanced Encryption Standard (AES) アルゴリズムを使用して、別のセッション キーを作成します。  この例では、XML ドキュメントの暗号化に AES セッション キーを使用してから、AES セッション キーを暗号化するために RSA 公開キーを使用しています。  最後に、この例では、暗号化された AES セッション キーと暗号化された XML データを、新しい <`EncryptedData`> 要素内の XML ドキュメントに保存します。  
  
 XML 要素を復号化するには、キー コンテナーから RSA 秘密キーを取得し、これを使用してセッション キーを復号化してから、セッション キーを使用してドキュメントを復号化します。  この手順を使用して暗号化された XML 要素を復号化する方法の詳細については、次を参照してください。[する方法: 非対称キーで XML 要素を復号化](../../../docs/standard/security/how-to-decrypt-xml-elements-with-asymmetric-keys.md)です。  
  
 この例は、複数のアプリケーションが暗号化されたデータを共有する必要がある状況や、1 つのアプリケーションが、実行する時間の間に暗号化されたデータを保存する必要がある状況に適しています。  
  
### <a name="to-encrypt-an-xml-element-with-an-asymmetric-key"></a>非対称キーで XML 要素を暗号化するには  
  
1.  <xref:System.Security.Cryptography.CspParameters> オブジェクトを作成し、キーのコンテナーの名前を指定します。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2.  <xref:System.Security.Cryptography.RSACryptoServiceProvider> クラスを使用して対称キーを生成します。  <xref:System.Security.Cryptography.CspParameters> オブジェクトを <xref:System.Security.Cryptography.RSACryptoServiceProvider> クラスのコンストラクターに渡すと、キーは自動的にキー コンテナーに保存されます。  このキーは、AES のセッション キーの暗号化に使用され、後で復号化するために取得することができます。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3.  ディスクから XML ファイルを読み込んで <xref:System.Xml.XmlDocument> オブジェクトを作成します。  <xref:System.Xml.XmlDocument> オブジェクトには、暗号化する XML 要素が含まれています。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#4)]  
  
4.  <xref:System.Xml.XmlDocument> オブジェクトで指定された要素を検索し、暗号化する要素を表す新しい <xref:System.Xml.XmlElement> オブジェクトを作成します。 この例では、`"creditcard"` 要素が暗号化されます。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
5.  <xref:System.Security.Cryptography.RijndaelManaged> クラスを使用してセッション キーを新規作成します。  このキーは、XML 要素を暗号化してから、このキー自体が暗号化されて XML ドキュメントに配置されます。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
6.  <xref:System.Security.Cryptography.Xml.EncryptedXml> クラスのインスタンスを新規作成し、これを使用して、セッション キーによって指定された要素を暗号化します。  <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> メソッドは、暗号化された要素を、暗号化されたバイトの配列として返します。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
7.  <xref:System.Security.Cryptography.Xml.EncryptedData> オブジェクトを構築し、暗号化された XML 要素の URL 識別子をそれに読み込みます。  この URL 識別子は、復号化側に、XML に暗号化された要素が含まれていることを知らせます。  [<xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl>] フィールドを使用すると、URL 識別子を指定することができます。  プレーン テキストの XML 要素は、この <xref:System.Security.Cryptography.Xml.EncryptedData> オブジェクトによってカプセル化された <`EncryptedData`> 要素に置き換えられます。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
8.  セッション キーの生成に使用する暗号化アルゴリズムの URL 識別子に初期化された <xref:System.Security.Cryptography.Xml.EncryptionMethod> オブジェクトを作成します。  <xref:System.Security.Cryptography.Xml.EncryptionMethod> オブジェクトを <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> プロパティに渡します。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#9)]  
  
9. 暗号化されたセッション キーを格納する <xref:System.Security.Cryptography.Xml.EncryptedKey> オブジェクトを作成します。  セッション キーを暗号化し、<xref:System.Security.Cryptography.Xml.EncryptedKey> オブジェクトに追加して、セッション キーの名前とキーの識別子の URL を入力します。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#10)]  
  
10. 暗号化されたデータを特定のセッション キーにマップする <xref:System.Security.Cryptography.Xml.DataReference> オブジェクトを新規作成します。  (省略可能) この手順を使用すると、XML ドキュメントの複数の部分が 1 つのキーによって暗号化されたことを簡単に指定できます。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#11)]  
  
11. 暗号化されたキーを <xref:System.Security.Cryptography.Xml.EncryptedData> オブジェクトに追加します。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#12)]  
  
12. RSA キーの名前を指定する <xref:System.Security.Cryptography.Xml.KeyInfo> オブジェクトを新規作成します。  このオブジェクトを <xref:System.Security.Cryptography.Xml.EncryptedData> オブジェクトに追加します。 これにより、復号化側は、適切な非対称キーを識別して、セッション キーを復号化する際に使用できるようになります。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#13)]  
  
13. 暗号化された要素のデータを <xref:System.Security.Cryptography.Xml.EncryptedData> オブジェクトに追加します。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#14)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#14)]  
  
14. 元の <xref:System.Xml.XmlDocument> オブジェクトの要素を <xref:System.Security.Cryptography.Xml.EncryptedData> 要素に置き換えます。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#15)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#15)]  
  
15. <xref:System.Xml.XmlDocument> オブジェクトを保存します。  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#16)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#16)]  
  
## <a name="example"></a>例  
 この例では、`"test.xml"` という名前のファイルがコンパイル済みのプログラムと同じディレクトリに存在することを前提としています。  また、`"test.xml"` には `"creditcard"` 要素が含まれることも前提としています。  次の XML を `test.xml` というファイルに配置し、この例で使用することができます。  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
-   この例をコンパイルするには、`System.Security.dll` への参照を含める必要があります。  
  
-   名前空間 <xref:System.Xml>、<xref:System.Security.Cryptography>、および <xref:System.Security.Cryptography.Xml> を含めます。  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 対称暗号化キーをプレーンテキストで保存したり、対称キーをコンピューター間でプレーンテキストで転送したりしないでください。  加えて、非対称キー ペアの秘密キーをプレーンテキストで保存または転送しないでください。  対称キーと非対称暗号化キーの詳細については、次を参照してください。[暗号化と復号化キーの生成](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)です。  
  
 キーをソース コードに直接埋め込まないでください。  使用してアセンブリから、埋め込まれたキーを簡単に読み取ることができます、 [Ildasm.exe (IL 逆アセンブラー)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)またはメモ帳などのテキスト エディターで、アセンブリを開くことができます。  
  
 暗号化キーを使用して完了したら、各バイトをゼロ (0) にするか、マネージ暗号化クラスの <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> メソッドを呼び出してメモリから消去します。  暗号化キーは、デバッガーによってメモリから読み取られるか、メモリの位置がディスクにページングされている場合はハード ドライブから読み取られることがあります。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Security.Cryptography.Xml>  
 [方法: 非対称キーで XML 要素を復号化する](../../../docs/standard/security/how-to-decrypt-xml-elements-with-asymmetric-keys.md)
