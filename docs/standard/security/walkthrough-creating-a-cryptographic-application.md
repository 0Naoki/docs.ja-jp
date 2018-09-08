---
title: 'チュートリアル : 暗号化アプリケーションの作成'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 873b6120929c8c7cf67d53d8f793964361ae88b8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137630"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="20be2-102">チュートリアル : 暗号化アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="20be2-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="20be2-103">このチュートリアルでは、コンテンツの暗号化および復号化の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="20be2-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="20be2-104">コード例は、Windows フォーム アプリケーション向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="20be2-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="20be2-105">このアプリケーションは、スマート カードを使用するなどの実際のシナリオは示していません。</span><span class="sxs-lookup"><span data-stu-id="20be2-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="20be2-106">代わりに、暗号化と復号化の基礎を示しています。</span><span class="sxs-lookup"><span data-stu-id="20be2-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="20be2-107">このチュートリアルでは、次の暗号化のガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="20be2-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
-   <span data-ttu-id="20be2-108">自動生成される <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> と <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A> を使用すると、対称アルゴリズムである <xref:System.Security.Cryptography.RijndaelManaged> クラスでデータの暗号化と復号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="20be2-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
-   <span data-ttu-id="20be2-109">非対称アルゴリズムである <xref:System.Security.Cryptography.RSACryptoServiceProvider> を使用すると、<xref:System.Security.Cryptography.RijndaelManaged> で暗号化されたデータのキーの暗号化と復号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="20be2-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="20be2-110">非対称アルゴリズムは、キーなどの少量のデータに最適です。</span><span class="sxs-lookup"><span data-stu-id="20be2-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20be2-111">暗号化されたコンテンツを他のユーザーと交換するのではなく、コンピューター上のデータを保護する場合は、<xref:System.Security.Cryptography.ProtectedData> クラスまたは <xref:System.Security.Cryptography.ProtectedMemory> クラスの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="20be2-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="20be2-112">次の表は、このトピックの暗号化のタスクをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="20be2-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="20be2-113">タスク</span><span class="sxs-lookup"><span data-stu-id="20be2-113">Task</span></span>|<span data-ttu-id="20be2-114">説明</span><span class="sxs-lookup"><span data-stu-id="20be2-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="20be2-115">Windows フォーム アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="20be2-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="20be2-116">アプリケーションを実行するために必要なコントロールの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="20be2-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="20be2-117">グローバル オブジェクトの宣言</span><span class="sxs-lookup"><span data-stu-id="20be2-117">Declaring global objects</span></span>|<span data-ttu-id="20be2-118">文字列のパスの変数、<xref:System.Security.Cryptography.CspParameters>、および <xref:System.Security.Cryptography.RSACryptoServiceProvider> を宣言して、<xref:System.Windows.Forms.Form> クラスのグローバル コンテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="20be2-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="20be2-119">非対称キーの作成</span><span class="sxs-lookup"><span data-stu-id="20be2-119">Creating an asymmetric key</span></span>|<span data-ttu-id="20be2-120">非対称の公開キーと秘密キーの値のペアを作成し、これにキー コンテナー名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20be2-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="20be2-121">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="20be2-121">Encrypting a file</span></span>|<span data-ttu-id="20be2-122">暗号化するファイルを選択するダイアログ ボックスを表示し、ファイルを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="20be2-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="20be2-123">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="20be2-123">Decrypting a file</span></span>|<span data-ttu-id="20be2-124">復号化する暗号化されたファイルを選択するダイアログ ボックスを表示し、ファイルを復号化します。</span><span class="sxs-lookup"><span data-stu-id="20be2-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="20be2-125">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="20be2-125">Getting a private key</span></span>|<span data-ttu-id="20be2-126">キー コンテナー名を使用して、完全なキーのペアを取得します。</span><span class="sxs-lookup"><span data-stu-id="20be2-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="20be2-127">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="20be2-127">Exporting a public key</span></span>|<span data-ttu-id="20be2-128">パブリック パラメーターのみで XML ファイルにキーを保存します。</span><span class="sxs-lookup"><span data-stu-id="20be2-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="20be2-129">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="20be2-129">Importing a public key</span></span>|<span data-ttu-id="20be2-130">キーを XML ファイルからキー コンテナーに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="20be2-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="20be2-131">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="20be2-131">Testing the application</span></span>|<span data-ttu-id="20be2-132">このアプリケーションをテストするための手順を一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="20be2-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="20be2-133">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="20be2-133">Prerequisites</span></span>  
 <span data-ttu-id="20be2-134">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="20be2-134">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="20be2-135"><xref:System.IO> 名前空間と <xref:System.Security.Cryptography> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="20be2-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="20be2-136">Windows フォーム アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="20be2-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="20be2-137">このチュートリアルにあるほとんどのコード例は、ボタン コントロールのイベント ハンドラーとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="20be2-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="20be2-138">次の表は、サンプル アプリケーションに必要なコントロールと、コード例に一致する必要な名前を示しています。</span><span class="sxs-lookup"><span data-stu-id="20be2-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="20be2-139">コントロール</span><span class="sxs-lookup"><span data-stu-id="20be2-139">Control</span></span>|<span data-ttu-id="20be2-140">名前</span><span class="sxs-lookup"><span data-stu-id="20be2-140">Name</span></span>|<span data-ttu-id="20be2-141">テキストのプロパティ (必要に応じて)</span><span class="sxs-lookup"><span data-stu-id="20be2-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="20be2-142">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="20be2-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="20be2-143">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="20be2-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="20be2-144">キーの作成</span><span class="sxs-lookup"><span data-stu-id="20be2-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="20be2-145">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="20be2-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="20be2-146">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="20be2-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="20be2-147">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="20be2-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="20be2-148">ボタンのイベント ハンドラーを作成するには、Visual Studio デザイナーでボタンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="20be2-148">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="20be2-149">グローバル オブジェクトの宣言</span><span class="sxs-lookup"><span data-stu-id="20be2-149">Declaring Global Objects</span></span>  
 <span data-ttu-id="20be2-150">次のコードをフォームのコンストラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-150">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="20be2-151">環境とユーザー設定のための文字列変数を編集します。</span><span class="sxs-lookup"><span data-stu-id="20be2-151">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="20be2-152">非対称キーの作成</span><span class="sxs-lookup"><span data-stu-id="20be2-152">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="20be2-153">この作業では、<xref:System.Security.Cryptography.RijndaelManaged> キーの暗号化と復号化を行う非対称キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="20be2-153">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="20be2-154">このキーは、コンテンツの暗号化に使用されたもので、ラベル コントロールにキー コンテナー名を表示します。</span><span class="sxs-lookup"><span data-stu-id="20be2-154">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="20be2-155">次のコードを、[`Create Keys`] ボタン (`buttonCreateAsmKeys_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-155">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="20be2-156">ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="20be2-156">Encrypting a File</span></span>  
 <span data-ttu-id="20be2-157">このタスクでは、2 つの方法: イベント ハンドラー メソッド、`Encrypt File`ボタン (`buttonEncryptFile_Click`) および`EncryptFile`メソッド。</span><span class="sxs-lookup"><span data-stu-id="20be2-157">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="20be2-158">最初のメソッドは、ファイルを選択するためのダイアログ ボックスを表示し、暗号化を実行する 2 番目のメソッドにファイル名を渡します。</span><span class="sxs-lookup"><span data-stu-id="20be2-158">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="20be2-159">暗号化されたコンテンツ、キー、および IV は、すべて 1 つの <xref:System.IO.FileStream> に保存されます。これを暗号化パッケージといいます。</span><span class="sxs-lookup"><span data-stu-id="20be2-159">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="20be2-160">この `EncryptFile` メソッドは以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="20be2-160">The `EncryptFile` method does the following:</span></span>  
  
1.  <span data-ttu-id="20be2-161">コンテンツを暗号化する <xref:System.Security.Cryptography.RijndaelManaged> 対称アルゴリズムを作成します。</span><span class="sxs-lookup"><span data-stu-id="20be2-161">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2.  <span data-ttu-id="20be2-162"><xref:System.Security.Cryptography.RijndaelManaged> キーを暗号化する <xref:System.Security.Cryptography.RSACryptoServiceProvider> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20be2-162">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3.  <span data-ttu-id="20be2-163">ソース ファイルの <xref:System.IO.FileStream> の読み取りと暗号化を行う <xref:System.Security.Cryptography.CryptoStream> オブジェクト (バイトのブロック) を使用して、暗号化ファイルの対象の <xref:System.IO.FileStream> オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="20be2-163">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4.  <span data-ttu-id="20be2-164">暗号化されたキーと IV の長さを決定し、長さの値のバイト配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="20be2-164">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5.  <span data-ttu-id="20be2-165">暗号化されたパッケージにキー、IV、および長さの値を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="20be2-165">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="20be2-166">暗号化パッケージでは、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="20be2-166">The encryption package uses the following format:</span></span>  
  
-   <span data-ttu-id="20be2-167">キーの長さ: 0 - 3 バイト</span><span class="sxs-lookup"><span data-stu-id="20be2-167">Key length, bytes 0 - 3</span></span>  
  
-   <span data-ttu-id="20be2-168">IV の長さ: 4 - 7 バイト</span><span class="sxs-lookup"><span data-stu-id="20be2-168">IV length, bytes 4 - 7</span></span>  
  
-   <span data-ttu-id="20be2-169">暗号化されたキー</span><span class="sxs-lookup"><span data-stu-id="20be2-169">Encrypted key</span></span>  
  
-   <span data-ttu-id="20be2-170">IV</span><span class="sxs-lookup"><span data-stu-id="20be2-170">IV</span></span>  
  
-   <span data-ttu-id="20be2-171">暗号化テキスト</span><span class="sxs-lookup"><span data-stu-id="20be2-171">Cipher text</span></span>  
  
 <span data-ttu-id="20be2-172">キーと IV の長さを使用すると、暗号化パッケージのすべての部分の開始点と長さを決定することができます。これを使用してファイルを復号化します。</span><span class="sxs-lookup"><span data-stu-id="20be2-172">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="20be2-173">次のコードを、[`Encrypt File`] ボタン (`buttonEncryptFile_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-173">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="20be2-174">フォームに次の `EncryptFile` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-174">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="20be2-175">ファイルの復号化</span><span class="sxs-lookup"><span data-stu-id="20be2-175">Decrypting a File</span></span>  
 <span data-ttu-id="20be2-176">この作業には、[`Decrypt File`] ボタン (`buttonDecryptFile_Click`) のイベント ハンドラー メソッドと `DecryptFile` メソッドという 2 つのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20be2-176">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonDecryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="20be2-177">最初のメソッドは、ファイルを選択するためのダイアログ ボックスを表示し、復号化を実行する 2 番目のメソッドにファイル名を渡します。</span><span class="sxs-lookup"><span data-stu-id="20be2-177">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="20be2-178">`Decrypt` メソッドは以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="20be2-178">The `Decrypt` method does the following:</span></span>  
  
1.  <span data-ttu-id="20be2-179">コンテンツを復号化する <xref:System.Security.Cryptography.RijndaelManaged> の対称アルゴリズムを作成します。</span><span class="sxs-lookup"><span data-stu-id="20be2-179">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2.  <span data-ttu-id="20be2-180">暗号化されたキーと IV の長さを取得するには、暗号化パッケージの <xref:System.IO.FileStream> の最初の 8 バイトを読み取ってバイト配列にします。</span><span class="sxs-lookup"><span data-stu-id="20be2-180">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3.  <span data-ttu-id="20be2-181">キーと IV を暗号化パッケージから抽出してバイト配列にします。</span><span class="sxs-lookup"><span data-stu-id="20be2-181">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4.  <span data-ttu-id="20be2-182"><xref:System.Security.Cryptography.RijndaelManaged> キーを復号化する <xref:System.Security.Cryptography.RSACryptoServiceProvider> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20be2-182">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5.  <span data-ttu-id="20be2-183"><xref:System.Security.Cryptography.CryptoStream> オブジェクトを使用して、<xref:System.IO.FileStream> の暗号化パッケージの暗号テキスト セクションをバイトのブロックで読み取って復号化し、復号化されたファイルの <xref:System.IO.FileStream> オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="20be2-183">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="20be2-184">これが終了すると、復号化は完了です。</span><span class="sxs-lookup"><span data-stu-id="20be2-184">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="20be2-185">次のコードを、[`Decrypt File`] ボタンの `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-185">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="20be2-186">フォームに次の `DecryptFile` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-186">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="20be2-187">公開キーのエクスポート</span><span class="sxs-lookup"><span data-stu-id="20be2-187">Exporting a Public Key</span></span>  
 <span data-ttu-id="20be2-188">この作業では、[`Create Keys`] ボタンによって作成されたキーをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="20be2-188">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="20be2-189">パブリック パラメーターのみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="20be2-189">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="20be2-190">この作業では、アリスがボブに公開キーを与えるシナリオをシミュレーションします。そうすることで、ボブはアリスのファイルを暗号化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="20be2-190">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="20be2-191">ボブとその公開キーを持つ他のユーザーはファイルを復号化できなくなります。彼らはプライベート パラメーターを持つ完全なキーのペアを持っていないためです。</span><span class="sxs-lookup"><span data-stu-id="20be2-191">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="20be2-192">次のコードを、[`Export Public Key`] ボタン (`buttonExportPublicKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-192">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="20be2-193">公開キーのインポート</span><span class="sxs-lookup"><span data-stu-id="20be2-193">Importing a Public Key</span></span>  
 <span data-ttu-id="20be2-194">この作業では、[`Export Public Key`] ボタンによって作成されたパブリック パラメーターのみを持つキーを読み込み、キー コンテナー名として設定します。</span><span class="sxs-lookup"><span data-stu-id="20be2-194">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="20be2-195">この作業では、ボブがアリスのファイルを暗号化できるように、ボブがパブリック パラメーターのみを持つアリスのキーを読み込むシナリオをシミュレーションします。</span><span class="sxs-lookup"><span data-stu-id="20be2-195">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="20be2-196">次のコードを、[`Import Public Key`] ボタン (`buttonImportPublicKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-196">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="20be2-197">秘密キーの取得</span><span class="sxs-lookup"><span data-stu-id="20be2-197">Getting a Private Key</span></span>  
 <span data-ttu-id="20be2-198">この作業では、[`Create Keys`] ボタンを使用して作成されたキーの名前にキー コンテナー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="20be2-198">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="20be2-199">キー コンテナーには、プライベート パラメーターを持つ完全なキーのペアが格納されます。</span><span class="sxs-lookup"><span data-stu-id="20be2-199">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="20be2-200">この作業では、アリスが自分の秘密キーを使用してボブが暗号化したファイルを復号化するシナリオをシミュレーションします。</span><span class="sxs-lookup"><span data-stu-id="20be2-200">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="20be2-201">次のコードを、[`Get Private Key`] ボタン (`buttonGetPrivateKey_Click`) の `Click` イベント ハンドラーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="20be2-201">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="20be2-202">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="20be2-202">Testing the Application</span></span>  
 <span data-ttu-id="20be2-203">アプリケーションをビルドしたら、次のテスト シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="20be2-203">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="20be2-204">キーの作成、暗号化、および復号化を行うには</span><span class="sxs-lookup"><span data-stu-id="20be2-204">To create keys, encrypt, and decrypt</span></span>  
  
1.  <span data-ttu-id="20be2-205">[`Create Keys`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20be2-205">Click the `Create Keys` button.</span></span> <span data-ttu-id="20be2-206">ラベルはキー名を表示し、完全なキーのペアであることを示します。</span><span class="sxs-lookup"><span data-stu-id="20be2-206">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2.  <span data-ttu-id="20be2-207">[`Export Public Key`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20be2-207">Click the `Export Public Key` button.</span></span> <span data-ttu-id="20be2-208">公開キーのパラメーターのエクスポートにより現在のキーは変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="20be2-208">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3.  <span data-ttu-id="20be2-209">[`Encrypt File`] ボタンをクリックして、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="20be2-209">Click the `Encrypt File` button and select a file.</span></span>  
  
4.  <span data-ttu-id="20be2-210">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="20be2-210">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5.  <span data-ttu-id="20be2-211">復号化したファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="20be2-211">Examine the file just decrypted.</span></span>  
  
6.  <span data-ttu-id="20be2-212">次のシナリオで保持されたキー コンテナーを取得するテストを実行するには、アプリケーションを閉じて再起動します。</span><span class="sxs-lookup"><span data-stu-id="20be2-212">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="20be2-213">公開キーを使用して暗号化するには</span><span class="sxs-lookup"><span data-stu-id="20be2-213">To encrypt using the public key</span></span>  
  
1.  <span data-ttu-id="20be2-214">[`Import Public Key`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20be2-214">Click the `Import Public Key` button.</span></span> <span data-ttu-id="20be2-215">ラベルはキー名を表示し、公開キーのみであることを示します。</span><span class="sxs-lookup"><span data-stu-id="20be2-215">The label displays the key name and shows that it is public only.</span></span>  
  
2.  <span data-ttu-id="20be2-216">[`Encrypt File`] ボタンをクリックして、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="20be2-216">Click the `Encrypt File` button and select a file.</span></span>  
  
3.  <span data-ttu-id="20be2-217">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="20be2-217">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="20be2-218">復号化するには秘密キーが必要であるため、これは失敗します。</span><span class="sxs-lookup"><span data-stu-id="20be2-218">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="20be2-219">このシナリオでは、公開キーのみによる別のユーザーのファイルの暗号化をデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="20be2-219">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="20be2-220">通常、そのユーザーは公開キーのみを与え、秘密キーは復号化のため与えないでおきます。</span><span class="sxs-lookup"><span data-stu-id="20be2-220">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="20be2-221">秘密キーを使用して復号化するには</span><span class="sxs-lookup"><span data-stu-id="20be2-221">To decrypt using the private key</span></span>  
  
1.  <span data-ttu-id="20be2-222">[`Get Private Key`] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20be2-222">Click the `Get Private Key` button.</span></span> <span data-ttu-id="20be2-223">ラベルはキー名を表示し、完全なキーのペアであるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="20be2-223">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2.  <span data-ttu-id="20be2-224">[`Decrypt File`] ボタンをクリックし、暗号化したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="20be2-224">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="20be2-225">復号化するための完全なキーのペアがあるため、これは成功します。</span><span class="sxs-lookup"><span data-stu-id="20be2-225">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20be2-226">関連項目</span><span class="sxs-lookup"><span data-stu-id="20be2-226">See also</span></span>

- [<span data-ttu-id="20be2-227">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="20be2-227">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
