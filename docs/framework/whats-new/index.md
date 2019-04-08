---
title: .NET Framework の新機能
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e6ce15c344ecd6e5f8d73cb98a06c8ccb40c9e7
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "58466440"
---
# <a name="whats-new-in-the-net-framework"></a><span data-ttu-id="f2d3b-102">.NET Framework の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-102">What's new in the .NET Framework</span></span>

<span data-ttu-id="f2d3b-103">この記事は、.NET Framework の次のバージョンにおける主な新機能と機能強化の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-103">This article summarizes key new features and improvements in the following versions of the .NET Framework:</span></span>

- [<span data-ttu-id="f2d3b-104">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="f2d3b-104">.NET Framework 4.7.2</span></span>](#v472)
- [<span data-ttu-id="f2d3b-105">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="f2d3b-105">.NET Framework 4.7.1</span></span>](#v471)
- [<span data-ttu-id="f2d3b-106">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f2d3b-106">.NET Framework 4.7</span></span>](#v47)
- [<span data-ttu-id="f2d3b-107">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f2d3b-107">.NET Framework 4.6.2</span></span>](#v462)
- [<span data-ttu-id="f2d3b-108">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f2d3b-108">.NET Framework 4.6.1</span></span>](#v461)
- [<span data-ttu-id="f2d3b-109">.NET 2015 と .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="f2d3b-109">.NET 2015 and .NET Framework 4.6</span></span>](#v46)
- [<span data-ttu-id="f2d3b-110">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f2d3b-110">.NET Framework 4.5.2</span></span>](#v452)
- [<span data-ttu-id="f2d3b-111">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="f2d3b-111">.NET Framework 4.5.1</span></span>](#v451)
- [<span data-ttu-id="f2d3b-112">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f2d3b-112">.NET Framework 4.5</span></span>](#v45)

<span data-ttu-id="f2d3b-113">この記事は、各新機能の包括的な情報を説明するものではありません。また、この内容は変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-113">This article does not provide comprehensive information about each new feature and is subject to change.</span></span> <span data-ttu-id="f2d3b-114">.NET Framework の概要については、「[.NET Framework の概要](../get-started/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-114">For general information about the .NET Framework, see [Getting Started](../get-started/index.md).</span></span> <span data-ttu-id="f2d3b-115">サポートされているプラットフォームについては、「[.NET Framework システム要件](~/docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-115">For supported platforms, see [System Requirements](~/docs/framework/get-started/system-requirements.md).</span></span> <span data-ttu-id="f2d3b-116">ダウンロード リンクとインストール手順については、「[.NET Framework のインストール](../install/guide-for-developers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-116">For download links and installation instructions, see [Installation Guide](../install/guide-for-developers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f2d3b-117">また .NET Framework チームは、NuGet により OOB 機能をリリースすることによって、プラットフォーム サポートを拡張し、新しい機能 (変更できないコレクションや SIMD 対応ベクター型など) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-117">The .NET Framework team also releases features out of band with NuGet to expand platform support and to introduce new functionality, such as immutable collections and SIMD-enabled vector types.</span></span> <span data-ttu-id="f2d3b-118">詳細については、「[その他のクラス ライブラリと API](../additional-apis/index.md)」および[.NET Framework と OOB リリース](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-118">For more information, see [Additional Class Libraries and APIs](../additional-apis/index.md) and [The .NET Framework and Out-of-Band Releases](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md).</span></span> <span data-ttu-id="f2d3b-119">.NET Framework 用の [NuGet パッケージの完全な一覧](https://blogs.msdn.microsoft.com/dotnet/p/nugetpackages/)をご確認いただくか、[Microsoft のフィード](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/)をサブスクライブしてください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-119">See a [complete list of NuGet packages](https://blogs.msdn.microsoft.com/dotnet/p/nugetpackages/) for the .NET Framework, or subscribe to [our feed](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).</span></span>

<a name="v472" />

## <a name="introducing-the-net-framework-472"></a><span data-ttu-id="f2d3b-120">.NET Framework 4.7.2 の概要</span><span class="sxs-lookup"><span data-stu-id="f2d3b-120">Introducing the .NET Framework 4.7.2</span></span>

<span data-ttu-id="f2d3b-121">.NET Framework 4.7.2 は、.NET Framework 4.x の以前のバージョンを基に、多数の新しい修正といくつかの新機能を追加したものであり、これまでと同様に非常に安定した製品です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-121">The .NET Framework 4.7.2 builds on previous versions of the .NET Framework 4.x by adding many new fixes and several new features while remaining a very stable product.</span></span>

### <a name="downloading-and-installing-the-net-framework-472"></a><span data-ttu-id="f2d3b-122">.NET Framework 4.7.2 のダウンロードとインストール</span><span class="sxs-lookup"><span data-stu-id="f2d3b-122">Downloading and installing the .NET Framework 4.7.2</span></span>

<span data-ttu-id="f2d3b-123">.NET Framework 4.7.2 は、次の場所からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-123">You can download the .NET Framework 4.7.2  from the following locations:</span></span>

- [<span data-ttu-id="f2d3b-124">.NET Framework 4.7.2 の Web インストーラー</span><span class="sxs-lookup"><span data-stu-id="f2d3b-124">.NET Framework 4.7.2 Web Installer</span></span>](https://go.microsoft.com/fwlink/?LinkId=863262)

- [<span data-ttu-id="f2d3b-125">.NET Framework 4.7.2 のオフライン インストーラー</span><span class="sxs-lookup"><span data-stu-id="f2d3b-125">NET Framework 4.7.2 Offline Installer</span></span>](https://go.microsoft.com/fwlink/?LinkId=863265)

<span data-ttu-id="f2d3b-126">.NET Framework 4.7.2 は、Windows 10、Windows 8.1、Windows 7 SP1、および Windows Server 2008 R2 SP1 以降に相当するサーバー プラットフォームにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-126">The .NET Framework 4.7.2 can be installed on Windows 10, Windows 8.1, Windows 7 SP1, and the corresponding server platforms starting with Windows Server 2008 R2 SP1.</span></span> <span data-ttu-id="f2d3b-127">.NET Framework 4.7.2 は、Web インストーラーまたはオフライン インストーラーを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-127">You can install the .NET Framework 4.7.2 by using either the web installer or the offline installer.</span></span> <span data-ttu-id="f2d3b-128">ほとんどのユーザーにお勧めする方法は、Web インストーラーの使用です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-128">The recommended way for most users is to use the web installer.</span></span>

<span data-ttu-id="f2d3b-129">[.NET Framework 4.7.2 Developer Pack](https://go.microsoft.com/fwlink/?LinkId=874338) をインストールすれば、Visual Studio 2012 以降で、.NET Framework 4.7.2 をインストール対象に設定できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-129">You can target the .NET Framework 4.7.2 in Visual Studio 2012 or later by installing the [.NET Framework 4.7.2 Developer Pack](https://go.microsoft.com/fwlink/?LinkId=874338).</span></span>

### <a name="whats-new-in-the-net-framework-472"></a><span data-ttu-id="f2d3b-130">.NET Framework 4.7.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-130">What's new in the .NET Framework 4.7.2</span></span>

<span data-ttu-id="f2d3b-131">.NET Framework 4.7.2 には、次の領域における新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-131">The .NET Framework 4.7.2 includes new features in the following areas:</span></span>

- [<span data-ttu-id="f2d3b-132">コア</span><span class="sxs-lookup"><span data-stu-id="f2d3b-132">Core</span></span>](#core-472)
- [<span data-ttu-id="f2d3b-133">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-133">ASP.NET</span></span>](#asp-net472)
- [<span data-ttu-id="f2d3b-134">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="f2d3b-134">Networking</span></span>](#net472)
- [<span data-ttu-id="f2d3b-135">SQL</span><span class="sxs-lookup"><span data-stu-id="f2d3b-135">SQL</span></span>](#sql472)
- [<span data-ttu-id="f2d3b-136">WPF</span><span class="sxs-lookup"><span data-stu-id="f2d3b-136">WPF</span></span>](#wpf472)
- [<span data-ttu-id="f2d3b-137">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="f2d3b-137">ClickOnce</span></span>](#clickonce)

<span data-ttu-id="f2d3b-138">.NET Framework 4.7.2 では引き続きアクセシビリティ機能の向上を重視し、支援技術のユーザーに適切なエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-138">A continuing focus in the .NET Framework 4.7.2 is improved accessibility, which allows an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="f2d3b-139">.NET Framework 4.7.2 のアクセシビリティ機能の改善の詳細については、「[What's new in accessibility in the .NET Framework](whats-new-in-accessibility.md)」 (.NET Framework のアクセシビリティの新機能) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-139">For information on accessibility improvement in the .NET Framework 4.7.2, see [What's new in accessibility in the .NET Framework](whats-new-in-accessibility.md).</span></span>

<a name="core-472" />

#### <a name="core"></a><span data-ttu-id="f2d3b-140">コア</span><span class="sxs-lookup"><span data-stu-id="f2d3b-140">Core</span></span>

<span data-ttu-id="f2d3b-141">.NET Framework 4.7.2 は、大量の暗号化の機能強化、ZIP アーカイブの圧縮解除サポートの向上、および追加のコレクションの API を備えています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-141">The .NET Framework 4.7.2 features a large number of cryptographic enhancements, better decompression support for ZIP archives, and additional collection APIs.</span></span>

<span data-ttu-id="f2d3b-142">**RSA.Create および DSA.Create の新しいオーバーロード**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-142">**New overloads of RSA.Create and DSA.Create**</span></span>

<span data-ttu-id="f2d3b-143"><xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType> および <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> メソッドを使うと、新しい <xref:System.Security.Cryptography.DSA> または <xref:System.Security.Cryptography.RSA> キーをインスタンス化するときにキーのパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-143">The <xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType> and <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> methods let you supply key parameters when instantiating a new <xref:System.Security.Cryptography.DSA> or <xref:System.Security.Cryptography.RSA> key.</span></span> <span data-ttu-id="f2d3b-144">次のようなコードを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-144">They allow you to replace code like the following:</span></span>

```csharp
// Before .NET Framework 4.7.2
using (RSA rsa = RSA.Create())
{
   rsa.ImportParameters(rsaParameters);
   // Other code to execute using the RSA instance.
}
```

```vb
' Before .NET Framework 4.7.2
Using rsa = RSA.Create()
   rsa.ImportParameters(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```
<span data-ttu-id="f2d3b-145">次のようなコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-145">with code like this:</span></span>
```csharp
// Starting with .NET Framework 4.7.2
using (RSA rsa = RSA.Create(rsaParameters))
{
   // Other code to execute using the rsa instance.
}
```
```vb
' Starting with .NET Framework 4.7.2
Using rsa = RSA.Create(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

<span data-ttu-id="f2d3b-146"><xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType> および <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType> メソッドでは、特定のキー サイズを指定して、新しい <xref:System.Security.Cryptography.DSA> または <xref:System.Security.Cryptography.RSA> キーを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-146">The <xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType> and <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType> methods let you generate new <xref:System.Security.Cryptography.DSA> or <xref:System.Security.Cryptography.RSA> keys with a specific key size.</span></span> <span data-ttu-id="f2d3b-147">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-147">For example:</span></span>

```csharp
using (DSA dsa = DSA.Create(2048))
{
   // Other code to execute using the dsa instance.
}
```

```vb
Using dsa = DSA.Create(2048)
   ' Other code to execute using the dsa instance.
End Using
```

<span data-ttu-id="f2d3b-148">**Rfc2898DeriveBytes コンストラクターは、ハッシュ アルゴリズムの名前を受け入れる**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-148">**Rfc2898DeriveBytes constructors accept a hash algorithm name**</span></span>

<span data-ttu-id="f2d3b-149"><xref:System.Security.Cryptography.Rfc2898DeriveBytes> クラスには、3 つの新しいコンストラクターがあり、キーを派生するときに使用する HMAC アルゴリズムを識別する <xref:System.Security.Cryptography.HashAlgorithmName> パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-149">The <xref:System.Security.Cryptography.Rfc2898DeriveBytes> class has three new constructors with a <xref:System.Security.Cryptography.HashAlgorithmName> parameter that identifies the HMAC algorithm to use when deriving keys.</span></span> <span data-ttu-id="f2d3b-150">SHA-1 を使用する代わりに、開発者は、次の例に示すように SHA-256 などの SHA-2 ベースの HMAC を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-150">Instead of using SHA-1, developers should use a SHA-2-based HMAC like SHA-256, as shown in the following example:</span></span>

```csharp
private static byte[] DeriveKey(string password, out int iterations, out byte[] salt,
                                out HashAlgorithmName algorithm)
{
   iterations = 100000;
   algorithm = HashAlgorithmName.SHA256;

   const int SaltSize = 32;
   const int DerivedValueSize = 32;

   using (Rfc2898DeriveBytes pbkdf2 = new Rfc2898DeriveBytes(password, SaltSize,
                                                             iterations, algorithm))
   {
      salt = pbkdf2.Salt;
      return pbkdf2.GetBytes(DerivedValueSize);
   }
}
```

```vb
Private Shared Function DeriveKey(password As String, ByRef iterations As Integer,
                                  ByRef salt AS Byte(), ByRef algorithm As HashAlgorithmName) As Byte()
   iterations = 100000
   algorithm = HashAlgorithmName.SHA256

   Const SaltSize As Integer = 32
   Const  DerivedValueSize As Integer = 32

   Using pbkdf2 = New Rfc2898DeriveBytes(password, SaltSize, iterations, algorithm)
      salt = pbkdf2.Salt
      Return pbkdf2.GetBytes(DerivedValueSize)
   End Using
End Function
```

<span data-ttu-id="f2d3b-151">**一時的なキーのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-151">**Support for ephemeral keys**</span></span>

<span data-ttu-id="f2d3b-152">PFX のインポートでは、必要に応じてハード ドライブをバイパスして、メモリから直接秘密キーを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-152">PFX import can optionally load private keys directly from memory, bypassing the hard drive.</span></span><span data-ttu-id="f2d3b-153"> 新しい <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> フラグが、<xref:System.Security.Cryptography.X509Certificates.X509Certificate2> コンストラクターまたは <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType> メソッドのいずれかのオーバーロードで指定されているときには、一時的なキーとして秘密キーが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-153"> When the new <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> flag is specified in an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> constructor or one of the overloads of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType> method, the private keys will be loaded as ephemeral keys.</span></span> <span data-ttu-id="f2d3b-154">これにより、キーがディスク上に表示されることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-154">This prevents the keys from being visible on the disk.</span></span> <span data-ttu-id="f2d3b-155">ただし、</span><span class="sxs-lookup"><span data-stu-id="f2d3b-155">However:</span></span>

- <span data-ttu-id="f2d3b-156">キーは、ディスク上に持続しないので、このフラグで読み込まれた証明書は、X509Store に追加する適切な候補ではありません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-156">Since the keys are not persisted to disk, certificates loaded with this flag are not good candidates to add to an X509Store.</span></span>

- <span data-ttu-id="f2d3b-157">この方法で読み込まれたキーは、ほとんどの場合、Windows CNG を使用して読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-157">Keys loaded in this manner are almost always loaded via Windows CNG.</span></span> <span data-ttu-id="f2d3b-158">そのため呼び出し元は、[cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A) などの拡張メソッドを呼び出すことによって秘密キーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-158">Therefore, callers must access the private key by calling extension methods, such as [cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A).</span></span> <span data-ttu-id="f2d3b-159"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> プロパティは機能しません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-159">The <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> property does not function.</span></span>

- <span data-ttu-id="f2d3b-160">従来の <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> プロパティは、証明書では機能しないので、開発者は、一時的なキーに切り替える前に厳格なテストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-160">Since the legacy <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> property does not work with certificates, developers should perform rigorous testing before switching to ephemeral keys.</span></span>

<span data-ttu-id="f2d3b-161">**PKCS #10 証明書署名要求と X.509 公開キー証明書のプログラムによる作成**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-161">**Programmatic creation of PKCS#10 certification signing requests and X.509 public key certificates**</span></span>

<span data-ttu-id="f2d3b-162">.NET Framework 4.7.2 以降、ワークロードは、証明書署名要求 (CSR) を生成できるようになりました。これにより、証明書要求の生成を既存のツールにステージングすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-162">Starting with the .NET Framework 4.7.2, workloads can generate certificate signing requests (CSRs), which allows certificate request generation to be staged into existing tooling.</span></span> <span data-ttu-id="f2d3b-163">これは、テストのシナリオでよく役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-163">This is frequently useful in test scenarios.</span></span>

<span data-ttu-id="f2d3b-164">詳細およびコードの例については、[.NET ブログ](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/)の「Programmatic creation of PKCS#10 certification signing requests and X.509 public key certificates」(PKCS #10 証明書署名要求と X.509 公開キー証明書のプログラムによる作成) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-164">For more information and code examples, see "Programmatic creation of PKCS#10 certification signing requests and X.509 public key certificates" in the [.NET Blog](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).</span></span>

<span data-ttu-id="f2d3b-165">**新しい SignerInfo メンバー**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-165">**New SignerInfo members**</span></span>

<span data-ttu-id="f2d3b-166">.NET Framework 4.7.2 以降、<xref:System.Security.Cryptography.Pkcs.SignerInfo> クラスは、署名の詳細を公開します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-166">Starting with the .NET Framework 4.7.2, the <xref:System.Security.Cryptography.Pkcs.SignerInfo> class exposes more information about the signature.</span></span> <span data-ttu-id="f2d3b-167"><xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName> プロパティの値を取得して、署名者によって使用される署名アルゴリズムを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-167">You can retrieve the value of the <xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName> property to determine the signature algorithm used by the signer.</span></span> <span data-ttu-id="f2d3b-168"><xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType> を呼び出して、この署名者の暗号化署名のコピーを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-168"><xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType> can be called to get a copy of the cryptographic signature for this signer.</span></span>

<span data-ttu-id="f2d3b-169">**CryptoStream が破棄された後にラップされたストリームを開いたままにする**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-169">**Leaving a wrapped stream open after CryptoStream is disposed**</span></span>

<span data-ttu-id="f2d3b-170">.NET Framework 4.7.2 以降、<xref:System.Security.Cryptography.CryptoStream> クラスの追加のコンストラクターを使用して、<xref:System.Security.Cryptography.CryptoStream.Dispose%2A> でラップされたストリームを開いたままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-170">Starting with the .NET Framework 4.7.2, the <xref:System.Security.Cryptography.CryptoStream> class has an additional constructor that allows <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> to not close the wrapped stream.</span></span><span data-ttu-id="f2d3b-171"> <xref:System.Security.Cryptography.CryptoStream> のインスタンスが破棄された後でラップされたストリームを開いたままにするには、次のように新しい <xref:System.Security.Cryptography.CryptoStream> コンストラクターを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-171"> To leave the wrapped stream open after the <xref:System.Security.Cryptography.CryptoStream> instance is disposed, call the new <xref:System.Security.Cryptography.CryptoStream> constructor as follows:</span></span>

```csharp
var cStream = new CryptoStream(stream, transform, mode, leaveOpen: true);
```

```vb
Dim cStream = New CryptoStream(stream, transform, mode, leaveOpen:=true)
```

<span data-ttu-id="f2d3b-172">**DeflateStream の圧縮解除の変更**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-172">**Decompression changes in DeflateStream**</span></span>

<span data-ttu-id="f2d3b-173">.NET Framework 4.7.2 以降では、<xref:System.IO.Compression.DeflateStream> クラスの圧縮解除操作の実装の際に、既定でネイティブの Windows API を使用するように変更されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-173">Starting with the .NET Framework 4.7.2, the implementation of decompression operations in the <xref:System.IO.Compression.DeflateStream> class has changed to use native Windows APIs by default.</span></span> <span data-ttu-id="f2d3b-174">通常は、これによりパフォーマンスが大幅に改善されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-174">Typically, this results in a substantial performance improvement.</span></span>

<span data-ttu-id="f2d3b-175">Windows API を使用した圧縮解除のサポートは .NET Framework 4.7.2 を対象とするアプリケーションで既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-175">Support for decompression by using Windows APIs is enabled by default for applications that target .NET Framework 4.7.2.</span></span> <span data-ttu-id="f2d3b-176">以前のバージョンの .NET Framework を対象とするアプリケーションが .NET Framework 4.7.2 未満で実行される場合は、次の [AppContext スイッチ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)をアプリケーション構成ファイルに追加することで、この動作を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-176">Applications that target earlier versions of .NET Framework but are running under .NET Framework 4.7.2 can opt into this behavior by adding the following [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=false" />
```

<span data-ttu-id="f2d3b-177">**追加のコレクション API**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-177">**Additional collection APIs**</span></span>

<span data-ttu-id="f2d3b-178">.NET Framework 4.7.2 でいくつかの新しい API が <xref:System.Collections.Generic.SortedSet%601> および <xref:System.Collections.Generic.HashSet%601> 型に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-178">The .NET Framework 4.7.2 adds a number of new APIs to the <xref:System.Collections.Generic.SortedSet%601> and <xref:System.Collections.Generic.HashSet%601> types.</span></span> <span data-ttu-id="f2d3b-179">次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-179">These include:</span></span>

- <span data-ttu-id="f2d3b-180">`TryGetValue` メソッドは、他のコレクション型で使用する try パターンを次の 2 つの型に拡張します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-180">`TryGetValue` methods, which extend the try pattern used in other collection types to these two types.</span></span> <span data-ttu-id="f2d3b-181">これらのメソッドを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-181">The methods are:</span></span>

   - [<span data-ttu-id="f2d3b-182">public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-182">public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)</span></span>](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)
   - [<span data-ttu-id="f2d3b-183">public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-183">public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)</span></span>](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)

- <span data-ttu-id="f2d3b-184"><xref:System.Collections.Generic.HashSet%601> 拡張メソッドは、コレクションを `Enumerable.To*` に変換します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-184">`Enumerable.To*` extension methods, which convert a collection to a <xref:System.Collections.Generic.HashSet%601>:</span></span>

   - [<span data-ttu-id="f2d3b-185">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-185">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)</span></span>](xref:System.Linq.Enumerable.ToHashSet%2A)
   - [<span data-ttu-id="f2d3b-186">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-186">public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)</span></span>](xref:System.Linq.Enumerable.ToHashSet%2A)

- <span data-ttu-id="f2d3b-187">新しい <xref:System.Collections.Generic.HashSet%601> コンストラクターを使用して、<xref:System.Collections.Generic.HashSet%601> のサイズが事前にわかっている場合に、コレクションの容量を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-187">New <xref:System.Collections.Generic.HashSet%601> constructors that let you set the collection's capacity, which yields a performance benefit when you know the size of the <xref:System.Collections.Generic.HashSet%601> in advance:</span></span>

   - <span data-ttu-id="f2d3b-188">[public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="f2d3b-188">[public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))</span></span>
   - <span data-ttu-id="f2d3b-189">[public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))</span><span class="sxs-lookup"><span data-stu-id="f2d3b-189">[public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))</span></span>

<span data-ttu-id="f2d3b-190"><xref:System.Collections.Concurrent.ConcurrentDictionary%602> クラスには、<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> および <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> メソッドの新しいオーバーロードが含まれています、これにより、ディクショナリから値を取得したり、またはそれが見つからない場合にそれを追加したり、値が既に存在する場合に、値をディクショナリに追加するか更新したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-190">The <xref:System.Collections.Concurrent.ConcurrentDictionary%602> class includes new overloads of the <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> and <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> methods to retrieve a value from the dictionary or to add it if it is not found, and to add a value to the dictionary or to update it if it already exists.</span></span>

```csharp
public TValue AddOrUpdate<TArg>(TKey key, Func<TKey, TArg, TValue> addValueFactory, Func<TKey, TValue, TArg, TValue> updateValueFactory, TArg factoryArgument)

public TValue GetOrAdd<TArg>(TKey key, Func<TKey, TArg, TValue> valueFactory, TArg factoryArgument)
```

```vb
Public AddOrUpdate(Of TArg)(key As TKey, addValueFactory As Func(Of TKey, TArg, TValue), updateValueFactory As Func(Of TKey, TValue, TArg, TValue), factoryArgument As TArg) As TValue

Public GetOrAdd(Of TArg)(key As TKey, valueFactory As Func(Of TKey, TArg, TValue), factoryArgument As TArg) As TValue
```

<a name="asp-net472" />

#### <a name="aspnet"></a><span data-ttu-id="f2d3b-191">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-191">ASP.NET</span></span>

<span data-ttu-id="f2d3b-192">**Web フォームでの依存関係挿入のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-192">**Support for dependency injection in Web Forms**</span></span>

<span data-ttu-id="f2d3b-193">[依存性挿入 (DI)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection) は、オブジェクトとその依存関係を分離し、依存関係の変更だけを理由としてオブジェクトのコードを変更する必要がないようにします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-193">[Dependency injection (DI)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection) decouples objects and their dependencies so that an object's code no longer needs to be changed just because a dependency has changed.</span></span> <span data-ttu-id="f2d3b-194">.NET Framework 4.7.2 を対象とする ASP.NET アプリケーションを開発するときに次のことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-194">When developing ASP.NET applications that target the .NET Framework 4.7.2, you can:</span></span>

- <span data-ttu-id="f2d3b-195">ASP.NET Web アプリケーション プロジェクトの[ハンドラーとモジュール](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100))、[ページ インスタンス](xref:System.Web.UI.Page)、および[ユーザー コントロール](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100))でアクセス操作子ベース、インターフェイス ベース、およびコンストラクター ベースの挿入を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-195">Use setter-based, interface-based, and constructor-based injection in [handlers and modules](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [Page instances](xref:System.Web.UI.Page), and [user controls](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) of ASP.NET web application projects.</span></span>

- <span data-ttu-id="f2d3b-196">ASP.NET Web サイト プロジェクトの[ハンドラーとモジュール](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100))、[ページ インスタンス](xref:System.Web.UI.Page)、および[ユーザー コントロール](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100))でアクセス操作子ベースおよびインターフェイス ベースの挿入を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-196">Use setter-based and interface-based injection in [handlers and modules](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [Page instances](xref:System.Web.UI.Page), and [user controls](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) of ASP.NET web site projects.</span></span>

- <span data-ttu-id="f2d3b-197">別の依存関係の挿入のフレームワークにプラグインします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-197">Plug in different dependency injection frameworks.</span></span>

<span data-ttu-id="f2d3b-198">**同じサイトの cookie のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-198">**Support for same-site cookies**</span></span>

<span data-ttu-id="f2d3b-199">[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07) は、ブラウザーがサイト間の要求と共に cookie を送信するのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-199">[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07) prevents a browser from sending a cookie along with a cross-site request.</span></span> <span data-ttu-id="f2d3b-200">.NET Framework 4.7.2 では、<xref:System.Web.SameSiteMode?displayProperty=nameWithType> 列挙体のメンバーの値を持つ <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType> プロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-200">The .NET Framework 4.7.2 adds a <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType> property whose value is a <xref:System.Web.SameSiteMode?displayProperty=nameWithType> enumeration member.</span></span> <span data-ttu-id="f2d3b-201">値が <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> または <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType> の場合、ASP.NET は `SameSite` 属性を set-cookie ヘッダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-201">If its value is <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> or <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType>, ASP.NET adds the `SameSite` attribute to the set-cookie header.</span></span> <span data-ttu-id="f2d3b-202">SameSite のサポートは、<xref:System.Web.HttpCookie> オブジェクト、および <xref:System.Web.Security.FormsAuthentication> と <xref:System.Web.SessionState> cookie に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-202">SameSite support applies to <xref:System.Web.HttpCookie> objects, as well as to <xref:System.Web.Security.FormsAuthentication> and <xref:System.Web.SessionState> cookies.</span></span>

<span data-ttu-id="f2d3b-203"><xref:System.Web.HttpCookie> オブジェクトの SameSite を次のように設定できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-203">You can set SameSite for an <xref:System.Web.HttpCookie> object as follows:</span></span>

```csharp
var c = new HttpCookie("secureCookie", "same origin");
c.SameSite = SameSiteMode.Lax;
```

```vb
Dim c As New HttpCookie("secureCookie", "same origin")
c.SameSite = SameSiteMode.Lax
```
<span data-ttu-id="f2d3b-204">Web.config ファイルを変更して、アプリケーション レベルで SameSite cookie を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-204">You can also configure SameSite cookies at the application level by modifying the web.config file:</span></span>

```xml
<system.web>
   <httpCookies sameSite="Strict" />
</system.web>
```
<span data-ttu-id="f2d3b-205">web config ファイルを変更することによって、<xref:System.Web.Security.FormsAuthentication> および <xref:System.Web.SessionState> cookie の SameSite を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-205">You can add SameSite for <xref:System.Web.Security.FormsAuthentication> and <xref:System.Web.SessionState> cookies by modifying the web config file:</span></span>

```xml
<system.web>
   <authentication mode="Forms">
      <forms cookieSameSite="Lax">
         <!-- ...   -->
      </forms>
   <authentication />
   <sessionSate cookieSameSite="Lax"></sessionState>
</system.web>
```

<a name="net472" />

#### <a name="networking"></a><span data-ttu-id="f2d3b-206">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="f2d3b-206">Networking</span></span>

<span data-ttu-id="f2d3b-207">**HttpClientHandler プロパティの実装**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-207">**Implementation of HttpClientHandler properties**</span></span>

<span data-ttu-id="f2d3b-208">.NET Framework 4.7.1 で 8 個のプロパティが、<xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> クラスに追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-208">The .NET Framework 4.7.1 added eight properties to the <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="f2d3b-209">ただし、2 つは <xref:System.PlatformNotSupportedException> をスローしていました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-209">However, two threw a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="f2d3b-210">.NET Framework 4.7.2 では、それらのプロパティの実装を提供するようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-210">The .NET Framework 4.7.2 now provides an implementation for these properties.</span></span> <span data-ttu-id="f2d3b-211">次のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-211">The properties are:</span></span>

- <xref:System.Net.Http.HttpClientHandler.CheckCertificateRevocationList>
- <xref:System.Net.Http.HttpClientHandler.SslProtocols>

<a name="sql472" />

#### <a name="sqlclient"></a><span data-ttu-id="f2d3b-212">SQLClient</span><span class="sxs-lookup"><span data-stu-id="f2d3b-212">SQLClient</span></span>

<span data-ttu-id="f2d3b-213">**Azure Active Directory のユニバーサル認証と多要素認証のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-213">**Support for Azure Active Directory Universal Authentication and Multi-Factor authentication**</span></span>

<span data-ttu-id="f2d3b-214">コンプライアンスとセキュリティのニーズが高まったために、多くのお客様が多要素認証 (MFA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-214">Growing compliance and security demands require that many customers use multi-factor authentication (MFA).</span></span> <span data-ttu-id="f2d3b-215">さらに、現在のベスト プラクティスでは、接続文字列内に直接ユーザーのパスワードを含めることは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-215">In addition, current best practices discourage including user passwords directly in connection strings.</span></span> <span data-ttu-id="f2d3b-216">これらの変更をサポートするために、.NET Framework 4.7.2 では、[SQLClient 接続文字列](xref:System.Data.SqlClient.SqlConnection.ConnectionString)を拡張しています。このために MFA および [Azure AD 認証](/azure/sql-database/sql-database-aad-authentication-configure)をサポートするための既存の "Authentication" キーワードに対して新しい値 "Active Directory Interactive" を追加しました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-216">To support these changes, the .NET Framework 4.7.2 extends [SQLClient connection strings](xref:System.Data.SqlClient.SqlConnection.ConnectionString) by adding a new value, "Active Directory Interactive", for the existing "Authentication" keyword to support MFA and [Azure AD Authentication](/azure/sql-database/sql-database-aad-authentication-configure).</span></span> <span data-ttu-id="f2d3b-217">新しい対話型メソッドでは、ネイティブおよびフェデレーションの Azure AD ユーザーだけでなく Azure AD ゲスト ユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-217">The new interactive method supports native and federated Azure AD users as well as Azure AD guest users.</span></span> <span data-ttu-id="f2d3b-218">このメソッドを使用する場合は、Azure AD によって課される MFA 認証が SQL データベースに対してサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-218">When this method is used, the MFA authentication imposed by Azure AD is supported for SQL databases.</span></span> <span data-ttu-id="f2d3b-219">さらに、認証プロセスは、セキュリティのベスト プラクティスに準拠するためにユーザーのパスワードを要求します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-219">In addition, the authentication process requests a user password to adhere to security best practices.</span></span>

<span data-ttu-id="f2d3b-220">以前のバージョンの .NET Framework では、SQL 接続は、<xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType> と <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType> のオプションのみをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-220">In previous versions of the .NET Framework, SQL connectivity supported only the <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType> and <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="f2d3b-221">これらはどちらも非対話型の [ADAL プロトコル](/azure/active-directory/develop/active-directory-authentication-libraries) の一部で、MFA はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-221">Both of these are part of the non-interactive [ADAL protocol](/azure/active-directory/develop/active-directory-authentication-libraries), which does not support MFA.</span></span> <span data-ttu-id="f2d3b-222">新しい <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType> オプションを使用して、SQL 接続は MFA および既存の認証方法 (パスワードや統合認証) をサポートします。これにより、ユーザーが接続文字列でパスワードを永続化せずに、対話形式でパスワードを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-222">With the new <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType> option, SQL connectivity supports MFA as well as existing authentication methods (password and integrated authentication), which allows users to enter user passwords interactively without persisting passwords in the connection string.</span></span>

<span data-ttu-id="f2d3b-223">詳細および例については、[.NET ブログ](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/)の「SQL -- Azure AD Universal and Multi-factor Authentication Support」(SQL--Azure AD ユニバーサルおよび多要素認証のサポート) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-223">For more information and an example, see "SQL -- Azure AD Universal and Multi-factor Authentication Support" in the [.NET Blog](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).</span></span>

<span data-ttu-id="f2d3b-224">**Always Encrypted バージョン 2 のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-224">**Support for Always Encrypted version 2**</span></span>

<span data-ttu-id="f2d3b-225">NET Framework 4.7.2 では、エンクレーブ ベースの Always Encrypted のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-225">NET Framework 4.7.2 adds supports for enclave-based Always Encrypted.</span></span> <span data-ttu-id="f2d3b-226">Always Encrypted の元のバージョンは、暗号化キーがクライアントから離れないクライアント側暗号化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-226">The original version of Always Encrypted is a client-side encryption technology in which encryption keys never leave the client.</span></span> <span data-ttu-id="f2d3b-227">エンクレーブ ベースの Always Encrypted では、クライアントが、オプションで暗号化キーをセキュアなエンクレーブに送信することができます。エンクレーブは、SQL Server の一部と見なされても SQL Server のコードを改ざんできないセキュアなコンピューティング エンティティです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-227">In enclave-based Always Encrypted, the client can optionally send the encryption keys to a secure enclave, which is a secure computational entity that can be considered part of SQL Server but that SQL Server code cannot tamper with.</span></span> <span data-ttu-id="f2d3b-228">エンクレーブ ベースの Always Encrypted をサポートするために、.NET Framework 4.7.2 では、次の型とメンバーが <xref:System.Data.SqlClient> 名前空間に追加されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-228">To support enclave-based Always Encrypted, the .NET Framework 4.7.2 adds the following types and members to the <xref:System.Data.SqlClient> namespace:</span></span>

- <span data-ttu-id="f2d3b-229"><xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType>。エンクレーブ ベースの Always Encrypted の URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-229"><xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType>, which specifies the Uri for enclave-based Always Encrypted.</span></span>

- <span data-ttu-id="f2d3b-230"><xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider>。すべてのエンクレーブ プロバイダーの派生元の抽象クラスです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-230"><xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider>, which is an abstract class from which all enclave providers are derived.</span></span>

- <span data-ttu-id="f2d3b-231"><xref:System.Data.SqlClient.SqlEnclaveSession>。指定されたエンクレーブ セッションの状態をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-231"><xref:System.Data.SqlClient.SqlEnclaveSession>, which encapsulates the state for a given enclave session.</span></span>

- <span data-ttu-id="f2d3b-232"><xref:System.Data.SqlClient.SqlEnclaveAttestationParameters>。SQL Server によって、特定の構成証明プロトコルを実行するために必要な情報を取得するために使用される構成証明パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-232"><xref:System.Data.SqlClient.SqlEnclaveAttestationParameters>, which provides the attestation parameters used by SQL Server to get information required to execute a particular Attestation Protocol.</span></span>

<span data-ttu-id="f2d3b-233">アプリケーション構成ファイルで、エンクレーブ プロバイダーの機能を提供する抽象 <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType> クラスの完全な実装を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-233">The application configuration file then specifies a concrete implementation of the abstract <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType> class that provides the functionality for the enclave provider.</span></span> <span data-ttu-id="f2d3b-234">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-234">For example:</span></span>

```xml
<configuration>
  <configSections>
    <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/> 
  </configSections>
  <SqlColumnEncryptionEnclaveProviders>
    <providers>
      <add name="Azure" type="Microsoft.SqlServer.Management.AlwaysEncrypted.AzureEnclaveProvider,MyApp"/>
      <add name="HGS" type="Microsoft.SqlServer.Management.AlwaysEncrypted.HGSEnclaveProvider,MyApp" />
    </providers>
  </SqlColumnEncryptionEnclaveProviders >
</configuration>
```

<span data-ttu-id="f2d3b-235">エンクレーブ ベースの Always Encrypted の基本的な流れを示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-235">The basic flow of enclave-based Always Encrypted is:</span></span>

1. <span data-ttu-id="f2d3b-236">ユーザーが、エンクレーブ ベースの Always Encrypted をサポートしていた SQL Server への AlwaysEncrypted 接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-236">The user creates an AlwaysEncrypted connection to SQL Server that supported enclave-based Always Encrypted.</span></span> <span data-ttu-id="f2d3b-237">ドライバーが、構成証明サービスにアクセスし、正しいエンクレーブに接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-237">The driver contacts the attestation service to ensure that it is connecting to right enclave.</span></span>

1. <span data-ttu-id="f2d3b-238">エンクレーブが証明されると、ドライバーが、SQL Server でホストされているセキュリティで保護されたエンクレーブとのセキュリティで保護されたチャネルを確立します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-238">Once the enclave has been attested, the driver establishes a secure channel with the secure enclave hosted on SQL Server.</span></span>

1. <span data-ttu-id="f2d3b-239">ドライバーは、SQL 接続の間にセキュリティで保護されたエンクレーブとクライアントによって承認された暗号化キーを共有します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-239">The driver shares encryption keys authorized by the client with the secure enclave for the duration of the SQL connection.</span></span>

<a name="wpf472" />

#### <a name="windows-presentation-foundation"></a><span data-ttu-id="f2d3b-240">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="f2d3b-240">Windows Presentation Foundation</span></span>

<span data-ttu-id="f2d3b-241">**ソースによる ResourceDictionaries の検索**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-241">**Finding ResourceDictionaries by Source**</span></span>

<span data-ttu-id="f2d3b-242">.NET Framework 4.7.2 以降、診断アシスタントでは、特定のソース URI から作成された  <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries> を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-242">Starting with the .NET Framework 4.7.2, a diagnostic assistant can locate the <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries> that have been created from a given source Uri.</span></span><span data-ttu-id="f2d3b-243"> (この機能は、実稼働アプリケーションではなく診断アシスタントによって使用されます)。Visual Studio の "エディット コンティニュ" 機能などの診断アシスタントでは、ユーザーが、実行中のアプリケーションに変更を適用する目的で ResourceDictionary を編集できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-243"> (This feature is for use by diagnostic assistants, not by production applications.) A diagnostic assistant such as Visual Studio’s “Edit-and-Continue” facility lets its user edit a ResourceDictionary with the intent that the changes be applied to the running application.</span></span> <span data-ttu-id="f2d3b-244">これを実現するための 1 つの手順は、実行中のアプリケーションが編集されているディクショナリから作成したすべての ResourceDictionaries を見つけることです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-244">One step in achieving this is finding all the ResourceDictionaries that the running application has created from the dictionary that’s being edited.</span></span> <span data-ttu-id="f2d3b-245">たとえば、アプリケーションは、コンテンツが特定のソース URI からコピーされる ResourceDictionary を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-245">For example, an application can declare a ResourceDictionary whose content is copied from a given source URI:</span></span>

```xml
<ResourceDictionary Source="MyRD.xaml">
```

<span data-ttu-id="f2d3b-246">*MyRD.xaml*  の元のマークアップを編集する診断アシスタントでは、ディクショナリを検索する新しい機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-246">A diagnostic assistant that edits the original markup in *MyRD.xaml* can use the new feature to locate the dictionary.</span></span><span data-ttu-id="f2d3b-247"> この機能は、新しい静的メソッド <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType> によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-247"> The feature is implemented by a new static method, <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2d3b-248">診断のアシスタントは、次のコードに示すように、元のマークアップを識別する絶対 URI を使用して新しいメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-248">The diagnostic assistant calls the new method using an absolute Uri that identifies the original markup, as illustrated by the following code:</span></span>

```csharp
IEnumerable<ResourceDictionary> dictionaries = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(new Uri("pack://application:,,,/MyApp;component/MyRD.xaml"));
```

```vb
Dim dictionaries As IEnumerable(Of ResourceDictionary) = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(New Uri("pack://application:,,,/MyApp;component/MyRD.xaml"))
```

<span data-ttu-id="f2d3b-249">このメソッドは、 <xref:System.Windows.Diagnostics.VisualDiagnostics> が有効で、かつ [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A)  環境変数が設定されている場合を除き、空白の列挙を返します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-249">The method returns an empty enumerable unless <xref:System.Windows.Diagnostics.VisualDiagnostics> is enabled and the [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) environment variable is set.</span></span>

<span data-ttu-id="f2d3b-250">**ResourceDictionary 所有者の検索**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-250">**Finding ResourceDictionary owners**</span></span>

<span data-ttu-id="f2d3b-251">.NET Framework 4.7.2 以降、診断アシスタントでは、特定の <xref:Windows.UI.Xaml.ResourceDictionary> の所有者を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-251">Starting with the .NET Framework 4.7.2, a diagnostic assistant can locate the owners of a given <xref:Windows.UI.Xaml.ResourceDictionary>.</span></span><span data-ttu-id="f2d3b-252"> (この機能は、実稼働アプリケーションではなく診断アシスタントによって使用されます。)<xref:Windows.UI.Xaml.ResourceDictionary> の変更が行われたときに、WPF が、変更の影響を受ける可能性があるすべての [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md) の参照を自動的に見つけます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-252"> (The feature is for use by diagnostic assistants and not by production applications.) Whenever a change is made to a <xref:Windows.UI.Xaml.ResourceDictionary>, WPF automatically finds all [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md) references that might be affected by the change.</span></span>

<span data-ttu-id="f2d3b-253">Visual Studio の "エディット コンティニュ" 機能などの診断アシスタントが、場合によっては [StaticResource](../wpf/advanced/staticresource-markup-extension.md) 参照を処理するためにこれを拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-253">A diagnostic assistant such as Visual Studio’s “Edit-and-Continue” facility may want extend this to handle [StaticResource](../wpf/advanced/staticresource-markup-extension.md) references.</span></span> <span data-ttu-id="f2d3b-254">このプロセスの最初の手順は、ディクショナリの所有者を検索することです。つまり、`Resources` プロパティがディクショナリを (直接または <xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType> プロパティを使用して間接的に) 参照しているすべてのオブジェクトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-254">The first step in this process is to find the owners of the dictionary; that is, to find all the objects whose `Resources` property refers to the dictionary (either directly, or indirectly via the <xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="f2d3b-255"><xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType> クラスに実装された 3 つの新しい静的メソッドは、`Resources` プロパティを持つ各基本データ型ごとに 1 つずつあり、次の手順をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-255">Three new static methods implemented on the <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType> class, one for each of the base types that has a `Resources` property, support this step:</span></span>

- [`public static IEnumerable<FrameworkElement> GetFrameworkElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkElementOwners%2A)

- [`public static IEnumerable<FrameworkContentElement> GetFrameworkContentElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkContentElementOwners%2A)

- [`public static IEnumerable<Application> GetApplicationOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetApplicationOwners%2A)

<span data-ttu-id="f2d3b-256">これらのメソッドは、 <xref:System.Windows.Diagnostics.VisualDiagnostics> が有効で、かつ [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A)  環境変数が設定されている場合を除き、空白の列挙を返します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-256">These methods return an empty enumerable unless <xref:System.Windows.Diagnostics.VisualDiagnostics> is enabled and the [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) environment variable is set.</span></span>

<span data-ttu-id="f2d3b-257">**StaticResource 参照の検索**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-257">**Finding StaticResource references**</span></span>

<span data-ttu-id="f2d3b-258">診断アシスタントで、[StaticResource](../wpf/advanced/staticresource-markup-extension.md) 参照が解決されるたびに通知を受け取ることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-258">A diagnostic assistant can now receive a notification whenever a [StaticResource](../wpf/advanced/staticresource-markup-extension.md) reference is resolved.</span></span><span data-ttu-id="f2d3b-259"> (この機能は、実稼働アプリケーションではなく診断アシスタントによって使用されます。)Visual Studio の "エディット コンティニュ" 機能などの診断アシスタントは、場合によっては <xref:Windows.UI.Xaml.ResourceDictionary> の値が変更されたときにリソースのすべての使用を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-259"> (The feature is for use by diagnostic assistants, not by production applications.) A diagnostic assistant such as Visual Studio’s “Edit-and-Continue” facility may want to update all uses of a resource when its value in a <xref:Windows.UI.Xaml.ResourceDictionary> changes.</span></span> <span data-ttu-id="f2d3b-260">WPF は、[DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md) 参照に関してこれを自動的に実行しますが、[StaticResource](../wpf/advanced/staticresource-markup-extension.md) 参照に関しては意図的に実行しません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-260">WPF does this automatically for [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md) references, but it intentionally does not do so for [StaticResource](../wpf/advanced/staticresource-markup-extension.md) references.</span></span> <span data-ttu-id="f2d3b-261">.NET Framework 4.7.2 以降、診断アシスタントは、静的リソースのそれらの使用を検索するのにこれらの通知を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-261">Starting with the .NET Framework 4.7.2, the diagnostic assistant can use these notifications to locate those uses of the static resource.</span></span>

<span data-ttu-id="f2d3b-262">通知は、新しい <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType> イベントによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-262">The notification is implemented by the new <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType> event:</span></span>

```csharp
public static event EventHandler<StaticResourceResolvedEventArgs> StaticResourceResolved;
```

```vb
Public Shared Event StaticResourceResolved As EventHandler(Of StaticResourceResolvedEventArgs)
```

<span data-ttu-id="f2d3b-263">このイベントは、ランタイムが [StaticResource](../wpf/advanced/staticresource-markup-extension.md) 参照を解決するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-263">This event is raised whenever the runtime resolves a [StaticResource](../wpf/advanced/staticresource-markup-extension.md) reference.</span></span><span data-ttu-id="f2d3b-264"> <xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs> 引数によって解決が記述され、[StaticResource](../wpf/advanced/staticresource-markup-extension.md) 参照をホストするオブジェクトとプロパティ、および解決に使用される  <xref:Windows.UI.Xaml.ResourceDictionary> とキーが示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-264"> The <xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs> arguments describe the resolution, and indicate the object and property that host the [StaticResource](../wpf/advanced/staticresource-markup-extension.md) reference and the <xref:Windows.UI.Xaml.ResourceDictionary> and key used for the resolution:</span></span>

```csharp
public class StaticResourceResolvedEventArgs : EventArgs
{
   public Object TargetObject { get; }

   public Object TargetProperty { get; }

   public ResourceDictionary ResourceDictionary { get; }

   public object ResourceKey { get; }
}
```

<span data-ttu-id="f2d3b-265"> <xref:System.Windows.Diagnostics.VisualDiagnostics> が有効で、かつ [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A)  環境変数が設定されていない限り、イベントを発生しません (その `add` アクセサーは無視されます)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-265">The event is not raised (and its `add` accessor is ignored) unless <xref:System.Windows.Diagnostics.VisualDiagnostics> is enabled and the [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) environment variable is set.</span></span>

#### <a name="clickonce"></a><span data-ttu-id="f2d3b-266">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="f2d3b-266">ClickOnce</span></span>

<span data-ttu-id="f2d3b-267">ClickOnce を使用して、Windows フォームの HDPI 対応アプリケーション、Windows Presentation Foundation (WPF)、および Visual Studio Tools for Office (VSTO) のすべてを配置できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-267">HDPI-aware applications for Windows Forms, Windows Presentation Foundation (WPF), and Visual Studio Tools for Office (VSTO) can all be deployed by using ClickOnce.</span></span> <span data-ttu-id="f2d3b-268">次のエントリがアプリケーション マニフェストに見つかった場合、.NET Framework 4.7.2 で展開が成功します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-268">If the following entry is found in the application manifest, deployment will succeed under .NET Framework 4.7.2:</span></span>

```xml
<windowsSettings>
   <dpiAware xmlns="http://schemas.microsoft.com/SMI/2005/WindowsSettings">true</dpiAware>
</windowsSettings>
```

<span data-ttu-id="f2d3b-269">Windows フォーム アプリケーションの場合、DPI 認識をアプリケーション マニフェストではなくアプリケーション構成ファイルで設定するという以前の回避策は、ClickOnce 展開を成功させるために必要ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-269">For Windows Forms application, the previous workaround of setting DPI awareness in the application configuration file rather than the application manifest is no longer necessary for ClickOnce deployment to succeed.</span></span>

<a name="v471" />

## <a name="whats-new-in-the-net-framework-471"></a><span data-ttu-id="f2d3b-270">.NET Framework 4.7.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-270">What's new in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="f2d3b-271">.NET Framework 4.7.1 には、次の領域における新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-271">The .NET Framework 4.7.1 includes new features in the following areas:</span></span>

- [<span data-ttu-id="f2d3b-272">コア</span><span class="sxs-lookup"><span data-stu-id="f2d3b-272">Core</span></span>](#core471)
- [<span data-ttu-id="f2d3b-273">共通言語ランタイム (CLR)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-273">Common language runtime (CLR)</span></span>](#clr)
- [<span data-ttu-id="f2d3b-274">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="f2d3b-274">Networking</span></span>](#net471)
- [<span data-ttu-id="f2d3b-275">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-275">ASP.NET</span></span>](#asp-net471)

<span data-ttu-id="f2d3b-276">さらに、.NET Framework 4.7.1 ではアクセシビリティ機能が向上し、支援技術のユーザーに適切なエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-276">In addition, a major focus in the .NET Framework 4.7.1 is improved accessibility, which allows an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="f2d3b-277">.NET Framework 4.7.1 のアクセシビリティ機能の改善の詳細については、「[What's new in accessibility in the .NET Framework](whats-new-in-accessibility.md)」 (.NET Framework のアクセシビリティの新機能) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-277">For information on accessibility improvements in the .NET Framework 4.7.1, see [What's new in accessibility in the .NET Framework](whats-new-in-accessibility.md).</span></span>

<a name="core471" />

#### <a name="core"></a><span data-ttu-id="f2d3b-278">コア</span><span class="sxs-lookup"><span data-stu-id="f2d3b-278">Core</span></span>

<span data-ttu-id="f2d3b-279">**.NET Standard 2.0 のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-279">**Support for .NET Standard 2.0**</span></span>

<span data-ttu-id="f2d3b-280">[.NET Standard](~/docs/standard/net-standard.md) は、そのバージョンの標準をサポートする各 .NET 実装で使用する必要がある API のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-280">[.NET Standard](~/docs/standard/net-standard.md) defines a set of APIs that must be available on each .NET implementation that supports that version of the standard.</span></span> <span data-ttu-id="f2d3b-281">.NET Framework 4.7.1 は、.NET Standard 2.0 を完全にサポートし、.NET Standard 2.0 で定義され、.NET Framework 4.6.1、4.6.2、および 4.7 にはなかった[約 200 の API](https://github.com/dotnet/standard/blob/master/netstandard/src/ApiCompatBaseline.net461.txt) を追加します </span><span class="sxs-lookup"><span data-stu-id="f2d3b-281">The .NET Framework 4.7.1 fully supports .NET Standard 2.0 and adds [about 200 APIs](https://github.com/dotnet/standard/blob/master/netstandard/src/ApiCompatBaseline.net461.txt) that are defined in .NET Standard 2.0 and are missing from the .NET Framework 4.6.1, 4.6.2, and 4.7.</span></span> <span data-ttu-id="f2d3b-282">(これらのバージョンの .NET Framework は、追加の .NET Standard サポート ファイルもターゲット システムにも展開されている場合にのみ .NET Standard 2.0 をサポートします)。詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「BCL - .NET Standard 2.0 Support」(BCL - .NET Standard 2.0 のサポート) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-282">(Note that these versions of the .NET Framework support .NET Standard 2.0 only if additional .NET Standard support files are also deployed on the target system.) For more information, see "BCL - .NET Standard 2.0 Support" in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span>

<span data-ttu-id="f2d3b-283">**構成ビルダーのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-283">**Support for configuration builders**</span></span>

<span data-ttu-id="f2d3b-284">構成ビルダーを使用して、開発者が、実行時にアプリケーションの構成設定を動的に注入およびビルドすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-284">Configuration builders allow developers to inject and build configuration settings for applications dynamically at run time.</span></span> <span data-ttu-id="f2d3b-285">カスタム構成ビルダーを使用して、構成セクションの既存のデータを変更したり、最初から完全に構成セクション全体をビルドしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-285">Custom configuration builders can be used to modify existing data in a configuration section or to build a configuration section entirely from scratch.</span></span> <span data-ttu-id="f2d3b-286">構成ビルダーを使用しない場合は、構成ファイルは静的であり、それらの設定はアプリケーションが起動されるしばらく前に定義されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-286">Without configuration builders, .config files are static, and their settings are defined some time before an application is launched.</span></span>

<span data-ttu-id="f2d3b-287">カスタム構成ビルダーを作成するには、抽象 <xref:System.Configuration.ConfigurationBuilder> クラスからビルダーを派生させ、その <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> と <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType> をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-287">To create a custom configuration builder, you derive your builder from the abstract <xref:System.Configuration.ConfigurationBuilder> class and override its <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> and <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2d3b-288">また、.config ファイルでもビルダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-288">You also define your builders in your .config file.</span></span> <span data-ttu-id="f2d3b-289">詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「Configuration Builders」(構成ビルダー) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-289">For more information, see the "Configuration Builders" section in the [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<span data-ttu-id="f2d3b-290">**実行時の機能の検出**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-290">**Run-time feature detection**</span></span>

<span data-ttu-id="f2d3b-291"><xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> クラスは、コンパイル時または実行時に特定の .NET の実装上で事前に定義された機能がサポートされているかどうかを判断するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-291">The <xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> class provides a mechanism for determine whether a predefined feature is supported on a given .NET implementation at compile time or run time.</span></span> <span data-ttu-id="f2d3b-292">コンパイラは、コンパイル時に、指定されたフィールドが存在するかどうかを確認し、その機能がサポートされているかどうかを判断します。サポートされている場合は、その機能を利用するコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-292">At compile time, a compiler can check whether a specified field exists to determine whether the feature is supported; if so, it can emit code that takes advantage of that feature.</span></span> <span data-ttu-id="f2d3b-293">実行時に、アプリケーションは、コードを生成する前に <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-293">At run time, an application can call the <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> method before emitting code at runtime.</span></span> <span data-ttu-id="f2d3b-294">詳細については、「[Add helper method to describe features supported by the runtime](https://github.com/dotnet/corefx/issues/17116)」(ランタイムでサポートされる機能を記述するヘルパー メソッドを追加する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-294">For more information, see [Add helper method to describe features supported by the runtime](https://github.com/dotnet/corefx/issues/17116).</span></span>

<span data-ttu-id="f2d3b-295">**値のタプル型はシリアル化できる**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-295">**Value tuple types are serializable**</span></span>

<span data-ttu-id="f2d3b-296">.NET Framework 4.7.1 以降、<xref:System.ValueTuple?displayProperty=nameWithType> および関連するジェネリック型は、[Serializable](xref:System.SerializableAttribute) としてマークされ、バイナリのシリアル化ができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-296">Starting with the .NET Framework 4.7.1, <xref:System.ValueTuple?displayProperty=nameWithType> and its associated generic types are marked as [Serializable](xref:System.SerializableAttribute), which allows binary serialization.</span></span> <span data-ttu-id="f2d3b-297">これにより、<xref:System.Tuple%603> や <xref:System.Tuple%604> などのタプル型を簡単に値のタプル型に移行できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-297">This should make migrating Tuple types, such as <xref:System.Tuple%603> and <xref:System.Tuple%604>, to value tuple types easier.</span></span> <span data-ttu-id="f2d3b-298">詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「Compiler -- ValueTuple is Serializable」(コンパイラ -- 値タプルはシリアル化できる) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-298">For more information, see "Compiler -- ValueTuple is Serializable" in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span>

<span data-ttu-id="f2d3b-299">**読み取り専用の参照のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-299">**Support for read-only references**</span></span>

<span data-ttu-id="f2d3b-300">.NET Framework 4.7.1 では、<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType> が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-300">The .NET Framework 4.7.1 adds the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2d3b-301">この属性は、読み取り専用の ref 戻り値型またはパラメーターを持つメンバーをマークする言語コンパイラで使用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-301">This attribute is used by language compilers to mark members that have read-only ref return types or parameters.</span></span> <span data-ttu-id="f2d3b-302">詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「Compiler - Support for ReadOnlyReferences」(コンパイラ - ReadOnlyReferences のサポート) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-302">For more information, see "Compiler -- Support for ReadOnlyReferences" in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span> <span data-ttu-id="f2d3b-303">Ref 戻り値の詳細については、「[Ref return values and ref locals (C# Guide)](~/docs/csharp/programming-guide/classes-and-structs/ref-returns.md)」(Ref 戻り値と ref ローカル変数 (C# ガイド)) および「[Ref return values (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md)」(Ref 戻り値 (Visual Basic)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-303">For information on ref return values, see [Ref return values and ref locals (C# Guide)](~/docs/csharp/programming-guide/classes-and-structs/ref-returns.md) and [Ref return values (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md).</span></span>

<a name="clr" />

#### <a name="common-language-runtime-clr"></a><span data-ttu-id="f2d3b-304">共通言語ランタイム (CLR)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-304">Common language runtime (CLR)</span></span>

<span data-ttu-id="f2d3b-305">**ガベージ コレクションのパフォーマンス改善**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-305">**Garbage collection performance improvements**</span></span>

<span data-ttu-id="f2d3b-306">.NET Framework 4.7.1 のガベージ コレクション (GC) への変更は、特に大きなオブジェクト ヒープ (LOH) の割り当ての場合の全体的なパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-306">Changes to garbage collection (GC) in the .NET Framework 4.7.1 improve overall performance, especially for Large Object Heap (LOH) allocations.</span></span> <span data-ttu-id="f2d3b-307">.NET Framework 4.7.1 では、小さなオブジェクト ヒープ (SOH) と LOH の割り当てに個別のロックを使用します。これにより、バックグラウンドの GC (BGC) が SOH をスイープするときに LOH の割り当てが許可されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-307">In the .NET Framework 4.7.1, separate locks are used for Small Object Heap (SOH) and LOH allocations, which allows LOH allocations to occur when Background GC (BGC) is sweeping the SOH.</span></span> <span data-ttu-id="f2d3b-308">その結果、多数の LOH の割り当てを行うアプリケーションでは、割り当てのロックの競合が減少し、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-308">As a result, applications that make a large number of LOH allocations should see a reduction in allocation lock contention and improved performance.</span></span> <span data-ttu-id="f2d3b-309">詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「Runtime -- GC Performance Improvements」(ランタイム - GC のパフォーマンスの向上) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-309">For more information, see the "Runtime -- GC Performance Improvements" section in the [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) blog post.</span></span>

<a name="net471"/>

#### <a name="networking"></a><span data-ttu-id="f2d3b-310">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="f2d3b-310">Networking</span></span>

<span data-ttu-id="f2d3b-311">**Message.HashAlgorithm 用の SHA-2 のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-311">**SHA-2 support for Message.HashAlgorithm**</span></span>

<span data-ttu-id="f2d3b-312">.NET Framework 4.7 およびそれ以前のバージョンでは、<xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> プロパティは値 <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> および <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType> のみをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-312">In the .NET Framework 4.7 and earlier versions, the <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> property supported values of <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> and <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType> only.</span></span> <span data-ttu-id="f2d3b-313">.NET Framework 4.7.1 以降では、<xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>、<xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType>、<xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType> もサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-313">Starting with the .NET Framework 4.7.1, <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType>, and <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType> are also supported.</span></span> <span data-ttu-id="f2d3b-314"><xref:System.Messaging.Message> インスタンス自体は、ハッシュは行わず、MSMQ に値を渡すだけですなので、この値が実際に使用されるかどうかは MSMQ によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-314">Whether this value is actually used depends on MSMQ, since the <xref:System.Messaging.Message> instance itself does no hashing but simply passes on values to MSMQ.</span></span> <span data-ttu-id="f2d3b-315">詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「SHA-2 support for Message.HashAlgorithm」(Message.HashAlgorithm 用の SHA-2 のサポート) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-315">For more information, see the "SHA-2 support for Message.HashAlgorithm" section in the [.NET Framework 4.7.1 ASP.NET and Configuration features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<a name="asp-net471" />

#### <a name="aspnet"></a><span data-ttu-id="f2d3b-316">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-316">ASP.NET</span></span>

<span data-ttu-id="f2d3b-317">**ASP.NET アプリケーションの実行ステップ**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-317">**Execution steps in ASP.NET applications**</span></span>

<span data-ttu-id="f2d3b-318">ASP.NET は、23 のイベントを含む定義済みのパイプラインで要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-318">ASP.NET processes requests in a predefined pipeline that includes 23 events.</span></span> <span data-ttu-id="f2d3b-319">ASP.NET は、実行ステップとして、各イベント ハンドラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-319">ASP.NET executes each event handler as an execution step.</span></span> <span data-ttu-id="f2d3b-320">バージョンの .NET Framework 4.7 までの ASP.NET のバージョンでは、ASP.NET は、ネイティブ スレッドとマネージド スレッドの切り替えのために、実行コンテキストをフローすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-320">In versions of ASP.NET up to the .NET Framework 4.7, ASP.NET can't flow the execution context due to switching between native and managed threads.</span></span> <span data-ttu-id="f2d3b-321">代わりに、ASP.NET は、<xref:System.Web.HttpContext> のみを選択的にフローします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-321">Instead, ASP.NET selectively flows only the <xref:System.Web.HttpContext>.</span></span> <span data-ttu-id="f2d3b-322">.NET Framework 4.7.1 以降、<xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> メソッドでは、モジュールがアンビエント データを復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-322">Starting with the .NET Framework 4.7.1, the <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> method also allows modules to restore ambient data.</span></span> <span data-ttu-id="f2d3b-323">この機能は、アプリケーションの実行フローを考慮する、トレース、プロファイリング、診断、トランザクションなどに関連するライブラリを対象とします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-323">This feature is targeted at libraries concerned with tracing, profiling, diagnostics, or transactions, for example, that care about the execution flow of the application.</span></span> <span data-ttu-id="f2d3b-324">詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「ASP.NET Execution Step Feature」(ASP.NET 実行ステップの機能) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-324">For more information, see the "ASP.NET Execution Step Feature" in the [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<span data-ttu-id="f2d3b-325">**ASP.NET HttpCookie 解析**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-325">**ASP.NET HttpCookie parsing**</span></span>

<span data-ttu-id="f2d3b-326">.NET Framework 4.7.1 には、新しいメソッド <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType> が含まれています。これは、文字列から <xref:System.Web.HttpCookie> オブジェクトを作成し、有効期限日やパスなどの cookie の値を正確に割り当てるための標準化された方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-326">The .NET Framework 4.7.1 includes a new method, <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>, that provides a standardized way to create an <xref:System.Web.HttpCookie> object from a string and accurately assign cookie values such as expiration date and path.</span></span> <span data-ttu-id="f2d3b-327">詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「ASP.NET HttpCookie parsing」(ASP.NET HttpCookie の解析) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-327">For more information, see "ASP.NET HttpCookie parsing" in the [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) blog post.</span></span>

<span data-ttu-id="f2d3b-328">**ASP.NET フォーム認証資格情報の SHA-2 ハッシュ オプション**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-328">**SHA-2 hash options for ASP.NET forms authentication credentials**</span></span>

<span data-ttu-id="f2d3b-329">.NET Framework 4.7 およびそれ以前のバージョンでは、ASP.NET を使用して開発者が、MD5 または SHA1 を使用し、構成ファイルにハッシュされたパスワードを含むユーザーの資格情報を格納することができました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-329">In the .NET Framework 4.7 and earlier versions, ASP.NET allowed developers to store user credentials with hashed passwords in configuration files using either MD5 or SHA1.</span></span> <span data-ttu-id="f2d3b-330">.NET Framework 4.7.1 以降では、ASP.NET はまた、SHA256、SHA384、SHA512 などの新しい安全な SHA-2 ハッシュ オプションもサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-330">Starting with the .NET Framework 4.7.1, ASP.NET also supports new secure SHA-2 hash options such as SHA256, SHA384, and SHA512.</span></span> <span data-ttu-id="f2d3b-331">SHA1 は既定のまま残り、Web 構成ファイルで既定以外のハッシュ アルゴリズムを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-331">SHA1 remains the default, and a non-default hash algorithm can be defined in the web configuration file.</span></span> <span data-ttu-id="f2d3b-332">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-332">For example:</span></span>

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47" />

## <a name="whats-new-in-the-net-framework-47"></a><span data-ttu-id="f2d3b-333">.NET Framework 4.7 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-333">What's new in the .NET Framework 4.7</span></span>

<span data-ttu-id="f2d3b-334">.NET Framework 4.7 には、次の領域における新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-334">The .NET Framework 4.7 includes new features in the following areas:</span></span>

- [<span data-ttu-id="f2d3b-335">コア</span><span class="sxs-lookup"><span data-stu-id="f2d3b-335">Core</span></span>](#Core47)
- [<span data-ttu-id="f2d3b-336">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="f2d3b-336">Networking</span></span>](#net47)
- [<span data-ttu-id="f2d3b-337">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-337">ASP.NET</span></span>](#ASP-NET47)
- [<span data-ttu-id="f2d3b-338">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-338">Windows Communication Foundation (WCF)</span></span>](#wcf47)
- [<span data-ttu-id="f2d3b-339">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="f2d3b-339">Windows Forms</span></span>](#wf47)
- [<span data-ttu-id="f2d3b-340">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-340">Windows Presentation Foundation (WPF)</span></span>](#WPF47)

<span data-ttu-id="f2d3b-341">.NET Framework 4.7 に追加された新しい API の一覧については、GitHub で [.NET Framework 4.7 API の変更点](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-341">For a list of new APIs added to the .NET Framework 4.7, see [.NET Framework 4.7 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) on GitHub.</span></span> <span data-ttu-id="f2d3b-342">.NET Framework 4.7 における機能の改善とバグ修正の一覧については、GitHub で [.NET Framework 4.7 の変更点](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-342">For a list of feature improvements and bug fixes in the .NET Framework 4.7, see [.NET Framework 4.7 List of Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) on GitHub.</span></span>  <span data-ttu-id="f2d3b-343">詳細については、.NET Blog の「[Announcing the .NET Framework 4.7 (.NET Framework 4.7 の発表)](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-343">For additional information, see [Announcing the .NET Framework 4.7](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/) in the .NET blog.</span></span>

<a name="Core47" />

#### <a name="core"></a><span data-ttu-id="f2d3b-344">コア</span><span class="sxs-lookup"><span data-stu-id="f2d3b-344">Core</span></span>

<span data-ttu-id="f2d3b-345">.NET Framework 4.7 で、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> によるシリアル化が改善されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-345">The .NET Framework 4.7 improves serialization by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>

<span data-ttu-id="f2d3b-346">**楕円曲線暗号 (ECC) による機能強化**\*</span><span class="sxs-lookup"><span data-stu-id="f2d3b-346">**Enhanced functionality with Elliptic Curve Cryptography (ECC)**\*</span></span>

<span data-ttu-id="f2d3b-347">.NET Framework 4.7 では、`ImportParameters(ECParameters)` メソッドが <xref:System.Security.Cryptography.ECDsa> クラスと <xref:System.Security.Cryptography.ECDiffieHellman> クラスに追加され、既に確立されたキーをオブジェクトで表すことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-347">In the .NET Framework 4.7, `ImportParameters(ECParameters)` methods were added to the <xref:System.Security.Cryptography.ECDsa> and <xref:System.Security.Cryptography.ECDiffieHellman> classes to allow for an object to represent an already-established key.</span></span> <span data-ttu-id="f2d3b-348">明示的な曲線パラメーターを使ってキーをエクスポートするための `ExportParameters(Boolean)` メソッドも追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-348">An `ExportParameters(Boolean)` method was also added for exporting the key using explicit curve parameters.</span></span>

<span data-ttu-id="f2d3b-349">また、.NET Framework 4.7 は、その他の曲線 (Brainpool 曲線スイートなど) のサポートと、新しい <xref:System.Security.Cryptography.ECDsa.Create%2A> および <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A> ファクトリ メソッドによる作成しやすい事前定義も追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-349">The .NET Framework 4.7 also adds support for additional curves (including the Brainpool curve suite), and has added predefined definitions for ease-of-creation through the new <xref:System.Security.Cryptography.ECDsa.Create%2A> and <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A> factory methods.</span></span>

<span data-ttu-id="f2d3b-350">GitHub で [.NET Framework 4.7 の暗号化の向上の例](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e)を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-350">You can see an [example of .NET Framework 4.7 cryptography improvements](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e) on GitHub.</span></span>

<span data-ttu-id="f2d3b-351">**DataContractJsonSerializer による制御文字のサポートの向上**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-351">**Better support for control characters by the DataContractJsonSerializer**</span></span>

<span data-ttu-id="f2d3b-352">.NET Framework 4.7 の <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> では、ECMAScript 6 標準に準拠して制御文字をシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-352">In the .NET Framework 4.7, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serializes control characters in conformity with the ECMAScript 6 standard.</span></span> <span data-ttu-id="f2d3b-353">この動作は、.NET Framework 4.7 を対象とするアプリケーションでは既定で有効になり、.NET Framework 4.7 で実行していても対象は以前のバージョンの .NET Framework であるアプリケーションの場合はオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-353">This behavior is enabled by default for applications that target the .NET Framework 4.7, and is an opt-in feature for applications that are running under the .NET Framework 4.7 but target a previous version of the .NET Framework.</span></span> <span data-ttu-id="f2d3b-354">詳細については、「[.NET Framework 4.7 における再ターゲットの変更点](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-354">For more information, see [Retargeting Changes in the .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).</span></span>

<a name="net47" />

#### <a name="networking"></a><span data-ttu-id="f2d3b-355">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="f2d3b-355">Networking</span></span>

<span data-ttu-id="f2d3b-356">.NET Framework 4.7 では、次のネットワーク関連機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-356">The .NET Framework 4.7 adds the following network-related feature:</span></span>

<span data-ttu-id="f2d3b-357">**TLS プロトコルの既定のオペレーティング システム サポート**\*</span><span class="sxs-lookup"><span data-stu-id="f2d3b-357">**Default operating system support for TLS protocols**\*</span></span>

<span data-ttu-id="f2d3b-358"><xref:System.Net.Security.SslStream?displayProperty=nameWithType> および HTTP、FTP、SMTP などの上位スタック コンポーネントによって使われる TLS スタックにより、開発者はオペレーティング システムによってサポートされる既定の TLS プロトコルを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-358">The TLS stack, which is used by <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and up-stack components such as HTTP, FTP, and SMTP, allows developers to use the default TLS protocols supported by the operating system.</span></span> <span data-ttu-id="f2d3b-359">TLS バージョンをハード コーディングする必要はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-359">Developers need no longer hard-code a TLS version.</span></span>

<a name="ASP-NET47" />

#### <a name="aspnet"></a><span data-ttu-id="f2d3b-360">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-360">ASP.NET</span></span>

<span data-ttu-id="f2d3b-361">.NET Framework 4.7 の ASP.NET には、次の新機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-361">In the .NET Framework 4.7, ASP.NET includes the following new features:</span></span>

<span data-ttu-id="f2d3b-362">**オブジェクト キャッシュの拡張性**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-362">**Object Cache Extensibility**</span></span>

<span data-ttu-id="f2d3b-363">.NET Framework 4.7 以降では、ASP.NET で追加された新しい API セットを使うことで、開発者は、メモリ内オブジェクト キャッシュとメモリ監視に関する既定の ASP.NET の実装を置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-363">Starting with the .NET Framework 4.7, ASP.NET adds a new set of APIs that allow developers to replace the default ASP.NET implementations for in-memory object caching and memory monitoring.</span></span> <span data-ttu-id="f2d3b-364">ASP.NET の実装が適切ではない場合、次の 3 つのコンポーネントを置き換えることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-364">Developers can now replace any of the following three components if the ASP.NET implementation is not adequate:</span></span>

- <span data-ttu-id="f2d3b-365">**オブジェクト キャッシュ ストア**。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-365">**Object Cache Store**.</span></span> <span data-ttu-id="f2d3b-366">新しいキャッシュ プロバイダー構成セクションを使うことで、開発者は、新しい **ICacheStoreProvider** インターフェイスを使って、ASP.NET アプリケーション用のオブジェクト キャッシュの新しい実装をプラグインできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-366">By using the new cache providers configuration section, developers can plug in new implementations of an object cache for an ASP.NET application by using the new **ICacheStoreProvider** interface.</span></span>

- <span data-ttu-id="f2d3b-367">**メモリ監視**。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-367">**Memory monitoring**.</span></span> <span data-ttu-id="f2d3b-368">ASP.NET の既定のメモリ モニターは、アプリケーションがプロセスに構成されているプライベート バイト制限に近づくと、またはコンピューターの使用可能な合計物理 RAM が低下すると、アプリケーションに通知します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-368">The default memory monitor in ASP.NET notifies applications when they are running close to the configured private bytes limit for the process, or when the machine is low on total available physical RAM.</span></span> <span data-ttu-id="f2d3b-369">これらの制限に近づくと、通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-369">When these limits are near, notifications are fired.</span></span> <span data-ttu-id="f2d3b-370">一部のアプリケーションでは、通知の発生が構成されている制限に近すぎるため、有効な対応を取れません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-370">For some applications, notifications are fired too close to the configured limits to allow for useful reactions.</span></span> <span data-ttu-id="f2d3b-371">開発者は、<xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType> プロパティを使用して既定値を置き換える独自のメモリ モニターを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-371">Developers can now write their own memory monitors to replace the default by using the <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="f2d3b-372">**メモリ制限への対応**。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-372">**Memory Limit Reactions**.</span></span> <span data-ttu-id="f2d3b-373">既定では、プライベート バイト プロセス制限が近づくと、ASP.NET はオブジェクト キャッシュの削減を試み、<xref:System.GC.Collect%2A?displayProperty=nameWithType> を定期的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-373">By default, ASP.NET attempts to trim the object cache and periodically call <xref:System.GC.Collect%2A?displayProperty=nameWithType> when the private byte process limit is near.</span></span> <span data-ttu-id="f2d3b-374">アプリケーションによっては、<xref:System.GC.Collect%2A?displayProperty=nameWithType> の呼び出し頻度またはトリミングされるキャッシュ量が非効率になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-374">For some applications, the frequency of calls to <xref:System.GC.Collect%2A?displayProperty=nameWithType> or the amount of cache that is trimmed are inefficient.</span></span> <span data-ttu-id="f2d3b-375">開発者は、アプリケーションのメモリ モニターに **IObserver** の実装をサブスクライブすることにより、既定の動作を置換または補完できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-375">Developers can now replace or supplement the default behavior by subscribing **IObserver** implementations to the application's memory monitor.</span></span>

<a name="wcf47" />

#### <a name="windows-communication-foundation-wcf"></a><span data-ttu-id="f2d3b-376">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-376">Windows Communication Foundation (WCF)</span></span>

<span data-ttu-id="f2d3b-377">Windows Communication Foundation (WCF) では以下の機能が追加または変更されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-377">Windows Communication Foundation (WCF) adds the following features and changes:</span></span>

<span data-ttu-id="f2d3b-378">**既定のメッセージ セキュリティ設定を TLS1.1 または TLS1.2 に構成する機能。**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-378">**Ability to configure the default message security settings to TLS 1.1 or TLS 1.2**</span></span>

<span data-ttu-id="f2d3b-379">.NET Framework 4.7 以降の WCF では、既定のメッセージ セキュリティ プロトコルとして、SSL 3.0 と TSL 1.0 に加えて、TSL 1.1 または TLS 1.2 を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-379">Starting with the .NET Framework 4.7, WCF allows you to configure TSL 1.1 or TLS 1.2 in addition to SSL 3.0 and TSL 1.0 as the default message security protocol.</span></span> <span data-ttu-id="f2d3b-380">これはオプトイン設定です。有効にするには、アプリケーション構成ファイルに次のエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-380">This is an opt-in setting; to enable it, you must add the following entry to your application configuration file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

<span data-ttu-id="f2d3b-381">**WCF アプリケーションと WCF シリアル化の信頼性の向上**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-381">**Improved reliability of WCF applications and WCF serialization**</span></span>

<span data-ttu-id="f2d3b-382">WCF に競合状態を除去する複数のコード変更が追加され、シリアル化オプションの信頼性とパフォーマンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-382">WCF includes a number of code changes that eliminate race conditions, thereby improving performance and the reliability of serialization options.</span></span> <span data-ttu-id="f2d3b-383">次の設定があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-383">These include:</span></span>

- <span data-ttu-id="f2d3b-384">**SocketConnection.BeginRead** および **SocketConnection.Read** の呼び出しでの非同期コードと同期コードの併用のサポートの向上。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-384">Better support for mixing asynchronous and synchronous code in calls to **SocketConnection.BeginRead** and **SocketConnection.Read**.</span></span>
- <span data-ttu-id="f2d3b-385">**SharedConnectionListener** および **DuplexChannelBinder** で接続を中止するときの信頼性の向上。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-385">Improved reliability when aborting a connection with **SharedConnectionListener** and **DuplexChannelBinder**.</span></span>
- <span data-ttu-id="f2d3b-386"><xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType> メソッドの呼び出し時のシリアル化操作の信頼性を向上しました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-386">Improved reliability of serialization operations when calling the <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="f2d3b-387">**ChannelSynchronizer.RemoveWaiter** メソッドを呼び出して待機を削除するときの信頼性の向上。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-387">Improved reliability when removing a waiter by calling the **ChannelSynchronizer.RemoveWaiter** method.</span></span>

<a name="wf47" />

#### <a name="windows-forms"></a><span data-ttu-id="f2d3b-388">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="f2d3b-388">Windows Forms</span></span>

<span data-ttu-id="f2d3b-389">.NET Framework 4.7 では、Windows フォームによる高 DPI モニターのサポートが向上しました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-389">In the .NET Framework 4.7, Windows Forms improves support for high DPI monitors.</span></span>

<span data-ttu-id="f2d3b-390">**高 DPI のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-390">**High DPI support**</span></span>

<span data-ttu-id="f2d3b-391">.NET Framework 4.7 を対象とするアプリケーションでは、Windows フォーム アプリケーションに対して高 DPI および動的 DPI がサポートされるようになっています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-391">Starting with applications that target the .NET Framework 4.7, the .NET Framework features high DPI and dynamic DPI support for Windows Forms applications.</span></span> <span data-ttu-id="f2d3b-392">高 DPI のサポートにより、フォームのレイアウトと外観および高 DPI モニターでのコントロールが向上します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-392">High DPI support improves the layout and appearance of forms and controls on high DPI monitors.</span></span> <span data-ttu-id="f2d3b-393">動的 DPI は、ユーザーが実行中のアプリケーションの DPI または表示倍率を変更すると、フォームのレイアウトと外観およびコントロールを変更します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-393">Dynamic DPI changes the layout and appearance of forms and controls when the user changes the DPI or display scale factor of a running application.</span></span>

<span data-ttu-id="f2d3b-394">高 DPI のサポートはオプトイン機能であり、アプリケーション構成ファイルの [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) セクションを定義することで構成します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-394">High DPI support is an opt-in feature that you configure by defining a [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) section in your application configuration file.</span></span> <span data-ttu-id="f2d3b-395">Windows フォーム アプリケーションへの高 DPI サポートおよび動的 DPI サポート追加の詳細については、「[Windows フォームの高 DPI サポート](../winforms/high-dpi-support-in-windows-forms.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-395">For more information on adding high DPI support and dynamic DPI support to your Windows Forms application, see [High DPI Support in Windows Forms](../winforms/high-dpi-support-in-windows-forms.md).</span></span>

<a name="WPF47" />

#### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f2d3b-396">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-396">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f2d3b-397">.NET Framework 4.7 では、WPF の機能が次のように強化されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-397">In the .NET Framework 4.7, WPF includes the following enhancements:</span></span>

<span data-ttu-id="f2d3b-398">**Windows WM_POINTER メッセージに基づくタッチ/スタイラス スタックのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-398">**Support for a touch/stylus stack based on Windows WM_POINTER messages**</span></span>

<span data-ttu-id="f2d3b-399">Windows Ink Services Platform (WISP) の代わりに [WM_POINTER メッセージ](https://docs.microsoft.com/previous-versions/windows/desktop/InputMsg/messages)に基づいてタッチ/スタイラス スタックを使うオプションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-399">You now have the option of using a touch/stylus stack based on [WM_POINTER messages](https://docs.microsoft.com/previous-versions/windows/desktop/InputMsg/messages) instead of the Windows Ink Services Platform (WISP).</span></span> <span data-ttu-id="f2d3b-400">これは、.NET Framework のオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-400">This is an opt-in feature in the .NET Framework.</span></span> <span data-ttu-id="f2d3b-401">詳細については、「[.NET Framework 4.7 における再ターゲットの変更点](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-401">For more information, see [Retargeting Changes in the .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).</span></span>

<span data-ttu-id="f2d3b-402">**WPF 印刷 API の新しい実装**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-402">**New implementation for WPF printing APIs**</span></span>

<span data-ttu-id="f2d3b-403"><xref:System.Printing.PrintQueue?displayProperty=nameWithType> クラスの WPF 印刷 API は、非推奨になった [XPS 印刷 API](/windows/desktop/printdocs/xps-printing) ではなく Windows [ドキュメント印刷パッケージ API](/windows/desktop/printdocs/tailored-app-printing-api) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-403">WPF's printing APIs in the <xref:System.Printing.PrintQueue?displayProperty=nameWithType> class call the Windows [Print Document Package API](/windows/desktop/printdocs/tailored-app-printing-api) instead of the deprecated [XPS Print API](/windows/desktop/printdocs/xps-printing).</span></span> <span data-ttu-id="f2d3b-404">アプリケーションの互換性に対するこの変更の影響については、「[.NET Framework 4.7 における再ターゲットの変更点](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-404">For the impact of this change on application compatibility, see [Retargeting Changes in the .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).</span></span>

<a name="v462" />

## <a name="whats-new-in-the-net-framework-462"></a><span data-ttu-id="f2d3b-405">.NET Framework 4.6.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-405">What's new in the .NET Framework 4.6.2</span></span>

<span data-ttu-id="f2d3b-406">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] には、次の領域における新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-406">The [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] includes new features in the following areas:</span></span>

- [<span data-ttu-id="f2d3b-407">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-407">ASP.NET</span></span>](#ASPNET462)

- [<span data-ttu-id="f2d3b-408">文字カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f2d3b-408">Character categories</span></span>](#Strings)

- [<span data-ttu-id="f2d3b-409">暗号</span><span class="sxs-lookup"><span data-stu-id="f2d3b-409">Cryptography</span></span>](#Crypto462)

- [<span data-ttu-id="f2d3b-410">SQLClient</span><span class="sxs-lookup"><span data-stu-id="f2d3b-410">SqlClient</span></span>](#SQLClient)

- [<span data-ttu-id="f2d3b-411">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f2d3b-411">Windows Communication Foundation</span></span>](#WCF)

- [<span data-ttu-id="f2d3b-412">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-412">Windows Presentation Foundation (WPF)</span></span>](#WPF462)

- [<span data-ttu-id="f2d3b-413">Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-413">Windows Workflow Foundation (WF)</span></span>](#WF462)

- [<span data-ttu-id="f2d3b-414">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="f2d3b-414">ClickOnce</span></span>](#clickonce-1)

- [<span data-ttu-id="f2d3b-415">Windows フォームおよび WPF アプリの UWP アプリへの変換</span><span class="sxs-lookup"><span data-stu-id="f2d3b-415">Converting Windows Forms and WPF apps to UWP apps</span></span>](#UWPConvert)

- [<span data-ttu-id="f2d3b-416">デバッグの機能強化</span><span class="sxs-lookup"><span data-stu-id="f2d3b-416">Debugging improvements</span></span>](#Debug462)

<span data-ttu-id="f2d3b-417">.NET Framework 4.6.2 に追加された新しい API の一覧については、GitHub で [.NET Framework 4.6.2 API の変更点](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-417">For a list of new APIs added to the .NET Framework 4.6.2, see [.NET Framework 4.6.2 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) on GitHub.</span></span> <span data-ttu-id="f2d3b-418">.NET Framework 4.6.2 における機能の改善とバグ修正の一覧については、GitHub で「[.NET Framework 4.6.2 List of Changes (.NET Framework 4.6.2 API の変更点の一覧)](https://go.microsoft.com/fwlink/?LinkId=708778)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-418">For a list of feature improvements and bug fixes in the .NET Framework 4.6.2, see [.NET Framework 4.6.2 List of Changes](https://go.microsoft.com/fwlink/?LinkId=708778) on GitHub.</span></span>  <span data-ttu-id="f2d3b-419">詳細については、.NET Blog の「[Announcing .NET Framework 4.6.2](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/)」(.NET Framework 4.6.2 の発表) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-419">For additional information, see [Announcing .NET Framework 4.6.2](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/) in the .NET blog.</span></span>

<a name="ASPNET462" />

### <a name="aspnet"></a><span data-ttu-id="f2d3b-420">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-420">ASP.NET</span></span>

<span data-ttu-id="f2d3b-421">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、ASP.NET の機能が次のように強化されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-421">In the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ASP.NET includes the following enhancements:</span></span>

<span data-ttu-id="f2d3b-422">**データ注釈検証コントロールのローカライズされたエラー メッセージのサポート強化**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-422">**Improved support for localized error messages in data annotation validators**</span></span>

<span data-ttu-id="f2d3b-423">データ注釈検証コントロールを使用して、1 つ以上の属性をクラス プロパティに追加して検証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-423">Data annotation validators enable you to perform validation by adding one or more attributes to a class property.</span></span> <span data-ttu-id="f2d3b-424">属性の <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> 要素は、検証が失敗した場合にエラー メッセージのテキストを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-424">The attribute's <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> element defines the text of the error message if validation fails.</span></span> <span data-ttu-id="f2d3b-425">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 以降では、ASP.NET でエラー メッセージを簡単にローカライズできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-425">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ASP.NET makes it easy to localize error messages.</span></span> <span data-ttu-id="f2d3b-426">エラー メッセージは次のような場合にローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-426">Error messages will be localized if:</span></span>

1.  <span data-ttu-id="f2d3b-427"><xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> が検証属性で指定されている。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-427">The <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> is provided in the validation attribute.</span></span>

2.  <span data-ttu-id="f2d3b-428">リソース ファイルが App_LocalResources フォルダーに格納されている。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-428">The resource file is stored in the App_LocalResources folder.</span></span>

3.  <span data-ttu-id="f2d3b-429">ローカライズされたリソース ファイル名の形式が `DataAnnotation.Localization.{`*名前*`}.resx` (この*名前*は、*languageCode*`-`*country/regionCode* または *languageCode* 形式のカルチャ名) である。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-429">The name of the localized resources file has the form `DataAnnotation.Localization.{`*name*`}.resx`, where *name* is a culture name in the format *languageCode*`-`*country/regionCode* or *languageCode*.</span></span>

4.  <span data-ttu-id="f2d3b-430">リソースのキー名が <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> 属性に割り当てられている文字列で、その値がローカライズされたエラー メッセージである。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-430">The key name of the resource is the string assigned to the <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> attribute,  and its value is the localized error message.</span></span>

<span data-ttu-id="f2d3b-431">たとえば、次のデータ注釈属性では、無効な評価の場合に表示する、既定のカルチャのエラー メッセージを定義します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-431">For example, the following data annotation attribute defines the default culture's error message for an invalid rating.</span></span>

```csharp
public class RatingInfo
{
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]
   [Display(Name = "Your Rating")]
   public int Rating { get; set; }
}
```

```vb
Public Class RatingInfo
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

<span data-ttu-id="f2d3b-432">キーがエラー メッセージ文字列であり、その値がローカライズされたエラー メッセージであるようにリソース ファイル DataAnnotation.Localization.fr.resx を作成します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-432">You can then create a resource file, DataAnnotation.Localization.fr.resx, whose key is the error message string and whose value is the localized error message.</span></span> <span data-ttu-id="f2d3b-433">ファイルは `App.LocalResources` フォルダーになければいけません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-433">The file must be found in the `App.LocalResources` folder.</span></span> <span data-ttu-id="f2d3b-434">たとえば下記は、キーとその値で、値はローカライズされたフランス語 (fr) のエラー メッセージです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-434">For example, the following is the key and its value in a localized French (fr) language error message:</span></span>

| <span data-ttu-id="f2d3b-435">name</span><span class="sxs-lookup"><span data-stu-id="f2d3b-435">Name</span></span>                                 | <span data-ttu-id="f2d3b-436">[値]</span><span class="sxs-lookup"><span data-stu-id="f2d3b-436">Value</span></span>                                     |
| ------------------------------------ | ----------------------------------------- |
| <span data-ttu-id="f2d3b-437">評価は、1 から 10 の範囲である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-437">The rating must be between 1 and 10.</span></span> | <span data-ttu-id="f2d3b-438">La note doit être comprise entre 1 et 10.</span><span class="sxs-lookup"><span data-stu-id="f2d3b-438">La note doit être comprise entre 1 et 10.</span></span> |

 <span data-ttu-id="f2d3b-439">また、データ注釈ローカリゼーションを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-439">In addition, data annotation localization is extensible.</span></span> <span data-ttu-id="f2d3b-440">開発者は、<xref:System.Web.Globalization.IStringLocalizerProvider> インターフェイスを実装してリソース ファイル以外の場所にローカリゼーション文字列を格納することで、独自の文字列ローカライザー プロバイダーにプラグインできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-440">Developers can plug in their own string localizer provider by implementing the <xref:System.Web.Globalization.IStringLocalizerProvider> interface to store localization string somewhere other than in a resource file.</span></span>

 <span data-ttu-id="f2d3b-441">**セッション状態ストア プロバイダーでの非同期サポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-441">**Async support with session-state store providers**</span></span>

 <span data-ttu-id="f2d3b-442">ASP.NET では、セッション状態ストア プロバイダーでタスクを返すメソッドを使用できるようになりました。これにより、ASP.NET アプリで非同期のスケーラビリティのメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-442">ASP.NET now allows task-returning methods to be used with session-state store providers, thereby allowing ASP.NET apps to get the scalability benefits of async.</span></span> <span data-ttu-id="f2d3b-443">セッション状態ストア プロバイダーでの非同期操作をサポートするために、ASP.NET には新しいインターフェイスである <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType> が含まれています。これは <xref:System.Web.IHttpModule> から継承され、開発者はこれを使用して独自のセッション状態モジュールと非同期セッション ストア プロバイダーを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-443">To supports asynchronous operations with session state store providers, ASP.NET includes  a new interface, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>, which inherits from <xref:System.Web.IHttpModule> and allows developers to implement their own session-state module and async session store providers.</span></span> <span data-ttu-id="f2d3b-444">このインターフェイスは次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-444">The interface is defined as follows:</span></span>

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

 <span data-ttu-id="f2d3b-445">また、<xref:System.Web.SessionState.SessionStateUtility> クラスには <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> および <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A> という 2 つの新しいメソッドが含まれています。これらを使用して、非同期操作をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-445">In addition, the <xref:System.Web.SessionState.SessionStateUtility> class includes two new methods, <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> and <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, that can be used to support asynchronous operations.</span></span>

 <span data-ttu-id="f2d3b-446">**出力キャッシュ プロバイダーの非同期サポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-446">**Async support for output-cache providers**</span></span>

 <span data-ttu-id="f2d3b-447">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 以降では、タスクを返すメソッドを出力キャッシュ プロバイダーで使用して、非同期のスケーラビリティのメリットを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-447">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], task-returning methods can be used with output-cache providers to provide the scalability benefits of async.</span></span>  <span data-ttu-id="f2d3b-448">これらのメソッドを実装するプロバイダーは、Web サーバー上のスレッド ブロックを減らし、ASP.NET サービスのスケーラビリティを向上させます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-448">Providers that implement these methods reduce thread-blocking on a web server and improve the scalability of an ASP.NET service.</span></span>

 <span data-ttu-id="f2d3b-449">非同期出力キャッシュ プロバイダーをサポートするために、次の API が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-449">The following APIs have been added to support asynchronous output-cache providers:</span></span>

- <span data-ttu-id="f2d3b-450"><xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> から継承される <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType> クラス。これにより、開発者は非同期出力キャッシュ プロバイダーを実装できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-450">The <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType> class, which inherits from <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> and allows developers to implement an asynchronous output-cache provider.</span></span>

- <span data-ttu-id="f2d3b-451"><xref:System.Web.Caching.OutputCacheUtility> クラス。出力キャッシュを構成するためのヘルパー メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-451">The <xref:System.Web.Caching.OutputCacheUtility> class, which provides helper methods for configuring the output cache.</span></span>

- <span data-ttu-id="f2d3b-452"><xref:System.Web.HttpCachePolicy?displayProperty=nameWithType> クラスの新しい 18 個のメソッド。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-452">18 new methods in the <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="f2d3b-453">これらのメソッドには、<xref:System.Web.HttpCachePolicy.GetCacheability%2A>、<xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>、<xref:System.Web.HttpCachePolicy.GetETag%2A>、<xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>、<xref:System.Web.HttpCachePolicy.GetMaxAge%2A>、<xref:System.Web.HttpCachePolicy.GetMaxAge%2A>、<xref:System.Web.HttpCachePolicy.GetNoStore%2A>、<xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>、<xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>、<xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>、<xref:System.Web.HttpCachePolicy.GetRevalidation%2A>、<xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>、<xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>、<xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>、および <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A> が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-453">These include <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>, and <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.</span></span>

- <span data-ttu-id="f2d3b-454"><xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType> クラスの新しい 2 つのメソッド (<xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> と <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-454">2 new methods in the <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType> class:  <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> and <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.</span></span>

- <span data-ttu-id="f2d3b-455"><xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType> クラスの新しい 2 つのメソッド (<xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> と <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-455">2 new methods in the <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType> class: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> and <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.</span></span>

- <span data-ttu-id="f2d3b-456"><xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType> クラスの新しい 2 つのメソッド (<xref:System.Web.HttpCacheVaryByParams.GetParams%2A> と <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-456">2 new methods in the <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType> class: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> and <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.</span></span>

- <span data-ttu-id="f2d3b-457"><xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType> クラスの <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> メソッド。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-457">In the <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType> class, the <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> method.</span></span>

- <span data-ttu-id="f2d3b-458"><xref:System.Web.Caching.CacheDependency> の <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> メソッド。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-458">In the <xref:System.Web.Caching.CacheDependency>, the <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> method.</span></span>

<a name="Strings" />

### <a name="character-categories"></a><span data-ttu-id="f2d3b-459">文字カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f2d3b-459">Character categories</span></span>

<span data-ttu-id="f2d3b-460">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] の文字は [Unicode Standard バージョン 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) に基づいて分類されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-460">Characters in the  [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] are classified based on the [Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="f2d3b-461">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] と [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] では、文字は Unicode 6.3 文字のカテゴリに基づいて分類されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-461">In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], characters were classified based on Unicode 6.3 character categories.</span></span>

<span data-ttu-id="f2d3b-462">Unicode 8.0 のサポートは、<xref:System.Globalization.CharUnicodeInfo> クラスによる文字列の分類およびそれに依存する型とメソッドに限定されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-462">Support for Unicode 8.0 is limited to the classification of characters by the <xref:System.Globalization.CharUnicodeInfo> class and to types and methods that rely on it.</span></span> <span data-ttu-id="f2d3b-463">これらには、<xref:System.Globalization.StringInfo> クラス、オーバーロードされた <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> メソッド、および .NET Framework の正規表現エンジンによって認識される[文字クラス](../../standard/base-types/character-classes-in-regular-expressions.md)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-463">These include the <xref:System.Globalization.StringInfo> class, the overloaded <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> method, and the [character classes](../../standard/base-types/character-classes-in-regular-expressions.md) recognized by the .NET Framework regular expression engine.</span></span>  <span data-ttu-id="f2d3b-464">文字や文字列の比較と並べ替えは、この変更の影響を受けることなく、引き続き基となるオペレーティング システムに依存します (Windows 7 システムの場合は、.NET Framework で提供される文字データに依存)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-464">Character and string comparison and sorting is unaffected by this change and continues to rely on the underlying operating system or, on Windows 7 systems, on character data provided by the .NET Framework.</span></span>

<span data-ttu-id="f2d3b-465">Unicode 6.0 から Unicode 7.0 への文字カテゴリの変更については、Unicode Consortium Web サイトの [Unicode Standard バージョン 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/) に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-465">For changes in character categories from Unicode 6.0 to Unicode 7.0, see [The Unicode Standard, Version 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/) at The Unicode Consortium website.</span></span> <span data-ttu-id="f2d3b-466">Unicode 7.0 から Unicode 8.0 への変更については、Unicode Consortium の Web サイトの [Unicode Standard バージョン 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) に関する記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-466">For changes from Unicode 7.0 to Unicode 8.0, see [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) at The Unicode Consortium website.</span></span>

<a name="Crypto462" />

### <a name="cryptography"></a><span data-ttu-id="f2d3b-467">暗号</span><span class="sxs-lookup"><span data-stu-id="f2d3b-467">Cryptography</span></span>

<span data-ttu-id="f2d3b-468">**FIPS 186-3 DSA を含む X509 証明書のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-468">**Support for X509 certificates containing FIPS 186-3 DSA**</span></span>

<span data-ttu-id="f2d3b-469">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] には、FIPS 186-2 の 1024 ビットという制限を超えるキーを持つ、DSA (Digital Signature Algorithm) X509 証明書のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-469">The [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] adds support for DSA (Digital Signature Algorithm) X509 certificates whose keys exceed the FIPS 186-2 1024-bit limit.</span></span>

<span data-ttu-id="f2d3b-470">より大きな FIPS 186-3 のキー サイズのサポートに加えて、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、SHA-2 ファミリのハッシュ アルゴリズム (SHA256、SHA384、SHA512) によるシグネチャ計算も可能です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-470">In addition to supporting the larger key sizes of FIPS 186-3, the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] allows computing signatures with the SHA-2 family of hash algorithms (SHA256, SHA384, and SHA512).</span></span> <span data-ttu-id="f2d3b-471">FIPS 186-3 のサポートは新しい <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType> クラスで提供されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-471">FIPS 186-3 support is provided by the new <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="f2d3b-472">.NET Framework 4.6 の <xref:System.Security.Cryptography.RSA> クラスと .NET Framework 4.6.1 の <xref:System.Security.Cryptography.ECDsa> クラスの最近の変更に合わせて、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] の <xref:System.Security.Cryptography.DSA> 抽象基本クラスにメソッドが追加されました。呼び出し元はこの機能をキャストせずに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-472">In keeping with recent changes to the <xref:System.Security.Cryptography.RSA> class in the .NET Framework 4.6 and the <xref:System.Security.Cryptography.ECDsa> class in the .NET Framework 4.6.1, the <xref:System.Security.Cryptography.DSA> abstract base class in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] has additional methods to allow callers to use this functionality without casting.</span></span> <span data-ttu-id="f2d3b-473">データに署名する場合は、以下の例のように、<xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> 拡張メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-473">You can call the <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> extension method to sign data, as the following example shows.</span></span>

```csharp
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPrivateKey())
    {
        return dsa.SignData(data, HashAlgorithmName.SHA384);
    }
}
```

```vb
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()
    Using DSA As DSA = cert.GetDSAPrivateKey()
        Return DSA.SignData(data, HashAlgorithmName.SHA384)
    End Using
End Function
```

<span data-ttu-id="f2d3b-474">署名データを検証する場合は、以下の例のように、<xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> 拡張メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-474">And you can call the <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> extension method to verify signed data, as the following example shows.</span></span>

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

<span data-ttu-id="f2d3b-475">**ECDiffieHellman キー派生ルーチンへの入力をよりわかりやすく**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-475">**Increased clarity for inputs to ECDiffieHellman key derivation routines**</span></span>

<span data-ttu-id="f2d3b-476">.NET Framework 3.5 では、3 種類の KDF (キー派生関数) ルーチンによる Elliptic Curve Diffie-Hellman キー承諾のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-476">The .NET Framework 3.5 added support for Elliptic Curve Diffie-Hellman Key Agreement with three different Key Derivation Function (KDF) routines.</span></span> <span data-ttu-id="f2d3b-477">ルーチンへの入力、およびルーチン自体は <xref:System.Security.Cryptography.ECDiffieHellmanCng> オブジェクトのプロパティで構成されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-477">The inputs to the routines, and the routines themselves, were configured via properties on the <xref:System.Security.Cryptography.ECDiffieHellmanCng> object.</span></span> <span data-ttu-id="f2d3b-478">しかし、すべてのルーチンですべての入力プロパティが読み取られるわけではないため、これまで開発者がよく混乱することがありました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-478">But since not every routine read every input property, there was ample room for confusion on the past of the developer.</span></span>

<span data-ttu-id="f2d3b-479">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ではこれに対処するために、次の 3 つのメソッドが <xref:System.Security.Cryptography.ECDiffieHellman> 基本クラスに追加され、これらの KDF ルーチンとその入力がよりわかりやくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-479">To address this in the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the following three methods have been added to the  <xref:System.Security.Cryptography.ECDiffieHellman> base class to more clearly represent these KDF routines and their inputs:</span></span>

|<span data-ttu-id="f2d3b-480">ECDiffieHellman メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-480">ECDiffieHellman method</span></span>|<span data-ttu-id="f2d3b-481">説明</span><span class="sxs-lookup"><span data-stu-id="f2d3b-481">Description</span></span>|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|<span data-ttu-id="f2d3b-482">次の式を使用してキー マテリアルを派生させます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-482">Derives key material using the formula</span></span><br /><br /> <span data-ttu-id="f2d3b-483">HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-483">HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span></span><br /><br /> <span data-ttu-id="f2d3b-484">HASH(secretPrepend OrElse *x* OrElse secretAppend)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-484">HASH(secretPrepend OrElse *x* OrElse secretAppend)</span></span><br /><br /> <span data-ttu-id="f2d3b-485">ここで *x* は、EC Diffie-Hellman アルゴリズムの計算結果を表します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-485">where *x* is the computed result of the EC Diffie-Hellman algorithm.</span></span>|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|<span data-ttu-id="f2d3b-486">次の式を使用してキー マテリアルを派生させます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-486">Derives key material using the formula</span></span><br /><br /> <span data-ttu-id="f2d3b-487">HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-487">HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)</span></span><br /><br /> <span data-ttu-id="f2d3b-488">HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-488">HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)</span></span><br /><br /> <span data-ttu-id="f2d3b-489">ここで *x* は、EC Diffie-Hellman アルゴリズムの計算結果を表します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-489">where *x* is the computed result of the EC Diffie-Hellman algorithm.</span></span>|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|<span data-ttu-id="f2d3b-490">TLS 擬似乱数関数 (PRF) 派生アルゴリズムを使用して、キー マテリアルを派生させます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-490">Derives key material using the TLS pseudo-random function (PRF) derivation algorithm.</span></span>|

<span data-ttu-id="f2d3b-491">**永続化されたキーによる対称暗号化のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-491">**Support for persisted-key symmetric encryption**</span></span>

<span data-ttu-id="f2d3b-492">Windows の暗号化ライブラリ (CNG) では、永続化された対称キーの格納とハードウェアに格納された対称キーの使用のサポートが追加され、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で開発者はこの機能を利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-492">The Windows cryptography library (CNG) added support for storing persisted symmetric keys and using hardware-stored symmetric keys, and the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] made it possible for developers to make use of this feature.</span></span>  <span data-ttu-id="f2d3b-493">キー名とキー プロバイダーの概念が実装に固有であるため、この機能を使用するには、推奨されるファクトリ手法 (`Aes.Create` の呼び出しなど) ではなく、具象実装型のコンストラクターを利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-493">Since the notion of key names and key providers is implementation-specific, using this feature requires utilizing the constructor of the concrete implementation types instead of the preferred factory approach (such as calling `Aes.Create`).</span></span>

<span data-ttu-id="f2d3b-494">永続化されたキーによる対称暗号化は、AES (<xref:System.Security.Cryptography.AesCng>) と 3DES (<xref:System.Security.Cryptography.TripleDESCng>) アルゴリズムでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-494">Persisted-key symmetric encryption support exists for the AES (<xref:System.Security.Cryptography.AesCng>) and 3DES (<xref:System.Security.Cryptography.TripleDESCng>) algorithms.</span></span> <span data-ttu-id="f2d3b-495">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-495">For example:</span></span>

```csharp
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)
{
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))
    {
        aes.IV = iv;

        // Using the zero-argument overload is required to make use of the persisted key
        using (ICryptoTransform encryptor = aes.CreateEncryptor())
        {
            if (!encryptor.CanTransformMultipleBlocks)
            {
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");
            }

            return encryptor.TransformFinalBlock(data, 0, data.Length);
        }
    }
}
```

```vb
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)
        Aes.IV = iv

        ' Using the zero-argument overload Is required to make use of the persisted key
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()
            If Not encryptor.CanTransformMultipleBlocks Then
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")
            End If
            Return encryptor.TransformFinalBlock(data, 0, data.Length)
        End Using
    End Using
End Function
```

<span data-ttu-id="f2d3b-496">**SHA-2 ハッシュの SignedXml サポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-496">**SignedXml support for SHA-2 hashing**</span></span>

<span data-ttu-id="f2d3b-497">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では <xref:System.Security.Cryptography.Xml.SignedXml> クラスに対するサポートが追加され、RSA-SHA256、RSA-SHA384、RSA-SHA512 の各 PKCS#1 署名メソッド、および SHA256、SHA384、SHA512 の各参照ダイジェスト アルゴリズムが使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-497">The [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] adds support to  the <xref:System.Security.Cryptography.Xml.SignedXml> class for RSA-SHA256, RSA-SHA384, and RSA-SHA512 PKCS#1 signature methods, and SHA256, SHA384, and SHA512 reference digest algorithms.</span></span>

<span data-ttu-id="f2d3b-498">以下のように、URI 定数はすべて <xref:System.Security.Cryptography.Xml.SignedXml> で示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-498">The URI constants are all exposed on <xref:System.Security.Cryptography.Xml.SignedXml>:</span></span>

|<span data-ttu-id="f2d3b-499">SignedXml フィールド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-499">SignedXml field</span></span>|<span data-ttu-id="f2d3b-500">定数</span><span class="sxs-lookup"><span data-stu-id="f2d3b-500">Constant</span></span>|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|<span data-ttu-id="f2d3b-501">"http://www.w3.org/2001/04/xmlenc#sha256"</span><span class="sxs-lookup"><span data-stu-id="f2d3b-501">"http://www.w3.org/2001/04/xmlenc#sha256"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|<span data-ttu-id="f2d3b-502">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"</span><span class="sxs-lookup"><span data-stu-id="f2d3b-502">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|<span data-ttu-id="f2d3b-503">"http://www.w3.org/2001/04/xmldsig-more#sha384"</span><span class="sxs-lookup"><span data-stu-id="f2d3b-503">"http://www.w3.org/2001/04/xmldsig-more#sha384"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|<span data-ttu-id="f2d3b-504">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"</span><span class="sxs-lookup"><span data-stu-id="f2d3b-504">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|<span data-ttu-id="f2d3b-505">"http://www.w3.org/2001/04/xmlenc#sha512"</span><span class="sxs-lookup"><span data-stu-id="f2d3b-505">"http://www.w3.org/2001/04/xmlenc#sha512"</span></span>|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|<span data-ttu-id="f2d3b-506">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"</span><span class="sxs-lookup"><span data-stu-id="f2d3b-506">"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"</span></span>|

 <span data-ttu-id="f2d3b-507">これらのアルゴリズムのサポートを追加するためにカスタムの <xref:System.Security.Cryptography.SignatureDescription> ハンドラーを <xref:System.Security.Cryptography.CryptoConfig> に登録していたプログラムはすべて従来どおり引き続き機能しますが、既定でプラットフォームでサポートされるようになったため、<xref:System.Security.Cryptography.CryptoConfig> への登録は不要になりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-507">Any programs that have registered a custom <xref:System.Security.Cryptography.SignatureDescription> handler into <xref:System.Security.Cryptography.CryptoConfig> to add support for these algorithms will continue to function as they did in the past, but since there are now platform defaults, the <xref:System.Security.Cryptography.CryptoConfig> registration is no longer necessary.</span></span>

<a name="SQLClient" />

### <a name="sqlclient"></a><span data-ttu-id="f2d3b-508">SqlClient</span><span class="sxs-lookup"><span data-stu-id="f2d3b-508">SqlClient</span></span>

<span data-ttu-id="f2d3b-509">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、.NET Framework SQL Server 用データ プロバイダー (<xref:System.Data.SqlClient?displayProperty=nameWithType>) に次の新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-509">.NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>) includes the following new features in the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:</span></span>

<span data-ttu-id="f2d3b-510">**Azure SQL Database への接続プールとタイムアウト**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-510">**Connection pooling and timeouts with Azure SQL databases**</span></span>

<span data-ttu-id="f2d3b-511">接続プールが有効な状態で、タイムアウトまたは他のログイン エラーが発生した場合は、例外がキャッシュされ、キャッシュされた例外は次の 5 秒から 1 分の間の後続の接続試行時にすべてスローされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-511">When connection pooling is enabled and a timeout or other login error occurs, an exception is cached, and the cached exception is thrown on any subsequent connection attempt for the next 5 seconds  to 1 minute.</span></span>  <span data-ttu-id="f2d3b-512">詳細については、「[SQL Server の接続プール (ADO.NET)](../data/adonet/sql-server-connection-pooling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-512">For more details, see [SQL Server Connection Pooling (ADO.NET)](../data/adonet/sql-server-connection-pooling.md).</span></span>

<span data-ttu-id="f2d3b-513">通常は迅速に復旧される一時的なエラーで接続試行が失敗する可能性があるため、Azure SQL Database への接続時のこの動作は望ましくありません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-513">This behavior is not desirable when connecting to Azure SQL Databases, since connection attempts can fail with transient errors that are typically recovered quickly.</span></span> <span data-ttu-id="f2d3b-514">接続試行操作をより最適化するため、Azure SQL Database への接続が失敗した場合は、接続プールのブロック期間の動作は削除されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-514">To better optimize the connection retry experience, the connection pool blocking period behavior is removed when connections to Azure SQL Databases fail.</span></span>

<span data-ttu-id="f2d3b-515">新しい `PoolBlockingPeriod` キーワードを追加することで、使用しているアプリに最適なブロック期間を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-515">The addition of the new `PoolBlockingPeriod` keyword lets you to select the blocking period best suited for your app.</span></span> <span data-ttu-id="f2d3b-516">次の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-516">Values include:</span></span>

<xref:System.Data.SqlClient.PoolBlockingPeriod.Auto>

<span data-ttu-id="f2d3b-517">Azure SQL Database に接続しているアプリケーションの接続プールのブロック期間は無効になり、他のすべての SQL Server インスタンスに接続しているアプリケーションの接続プールのブロック期間が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-517">The connection pool blocking period for an application that connects to an Azure SQL Database is disabled, and the connection pool blocking period for an application that connects to any other SQL Server instance is enabled.</span></span> <span data-ttu-id="f2d3b-518">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-518">This is the default value.</span></span> <span data-ttu-id="f2d3b-519">サーバー エンドポイント名の末尾が以下のいずれかである場合は、Azure SQL Database と見なされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-519">If the Server endpoint name ends with any of the following, they are considered Azure SQL Databases:</span></span>

- <span data-ttu-id="f2d3b-520">.database.windows.net</span><span class="sxs-lookup"><span data-stu-id="f2d3b-520">.database.windows.net</span></span>

- <span data-ttu-id="f2d3b-521">.database.chinacloudapi.cn</span><span class="sxs-lookup"><span data-stu-id="f2d3b-521">.database.chinacloudapi.cn</span></span>

- <span data-ttu-id="f2d3b-522">.database.usgovcloudapi.net</span><span class="sxs-lookup"><span data-stu-id="f2d3b-522">.database.usgovcloudapi.net</span></span>

- <span data-ttu-id="f2d3b-523">.database.cloudapi.de</span><span class="sxs-lookup"><span data-stu-id="f2d3b-523">.database.cloudapi.de</span></span>

<xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>

<span data-ttu-id="f2d3b-524">接続プールのブロック期間は常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-524">The connection pool blocking period is always enabled.</span></span>

<xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock>

<span data-ttu-id="f2d3b-525">接続プールのブロック期間は常に無効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-525">The connection pool blocking period is always disabled.</span></span>

<span data-ttu-id="f2d3b-526">**Always Encrypted の強化**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-526">**Enhancements for Always Encrypted**</span></span>

<span data-ttu-id="f2d3b-527">SQLClient では、Always Encrypted の以下の 2 つの機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-527">SQLClient introduces two enhancements for Always Encrypted:</span></span>

- <span data-ttu-id="f2d3b-528">暗号化されたデータベースの列に対するパラメーター クエリのパフォーマンスを向上させるために、クエリ パラメーターの暗号化メタデータがキャッシュされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-528">To improve performance of parameterized queries against encrypted database columns, encryption metadata for query parameters is now cached.</span></span> <span data-ttu-id="f2d3b-529"><xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> プロパティが `true` (既定値) に設定されている状態で、同じクエリが複数回呼び出された場合、クライアントはサーバーからパラメーターのメタデータを 1 回だけ取得します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-529">With the <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> property set to `true` (which is the default value), if the same query is called multiple times, the client retrieves parameter metadata from the server only once.</span></span>

- <span data-ttu-id="f2d3b-530">キー キャッシュ内の列暗号化キー エントリは、<xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType> プロパティを使用して設定された構成可能な時間間隔後に削除されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-530">Column encryption key entries in the key cache are now evicted after a configurable time interval, set using the <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType> property.</span></span>

<a name="WCF" />

### <a name="windows-communication-foundation"></a><span data-ttu-id="f2d3b-531">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f2d3b-531">Windows Communication Foundation</span></span>

<span data-ttu-id="f2d3b-532">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、Windows Communication Foundation の次の領域の機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-532">In the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Communication Foundation has been enhanced in the following areas:</span></span>

<span data-ttu-id="f2d3b-533">**CNG を使用して格納される証明書の WCF トランスポート セキュリティ サポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-533">**WCF transport security support for certificates stored using CNG**</span></span>

<span data-ttu-id="f2d3b-534">WCF トランスポート セキュリティでは、Windows 暗号化ライブラリ (CNG) を使用して格納される証明書がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-534">WCF transport security supports certificates stored using the Windows cryptography library (CNG).</span></span> <span data-ttu-id="f2d3b-535">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、このサポートは、指数の長さが 32 ビット以下の公開キーを持つ証明書を使用する場合に限定されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-535">In the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], this support is limited to using certificates with a public key that has an exponent no more than 32 bits in length.</span></span> <span data-ttu-id="f2d3b-536">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] を対象とするアプリケーションでは、この機能は既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-536">When an application targets the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], this feature is on by default.</span></span>

<span data-ttu-id="f2d3b-537">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 以前を対象とするアプリケーションが [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で実行されている場合、app.config または web.config ファイルの [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) セクションに次の行を追加することで、この機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-537">For applications that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier but are running on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], this feature can be enabled by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app.config or web.config file.</span></span>

```xml
<AppContextSwitchOverrides
    value="Switch.System.ServiceModel.DisableCngCertificates=false"
/>
```

<span data-ttu-id="f2d3b-538">以下のようなコードを使用してプログラムで行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-538">This can also be done programmatically with code like the following:</span></span>

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";
AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

<span data-ttu-id="f2d3b-539">**DataContractJsonSerializer クラスによる複数の夏時間調整規則のサポート強化**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-539">**Better support for multiple daylight saving time adjustment rules by the DataContractJsonSerializer class**</span></span>

<span data-ttu-id="f2d3b-540">お客様はアプリケーションの構成設定を使用して、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> クラスで 1 つのタイム ゾーンに対して複数の調整規則がサポートされているかどうかを判別することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-540">Customers can use an application configuration setting to determine whether the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> class supports multiple adjustment rules for a single time zone.</span></span> <span data-ttu-id="f2d3b-541">これはオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-541">This is an opt-in feature.</span></span> <span data-ttu-id="f2d3b-542">これを有効にするには、app.config ファイルに次の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-542">To enable it, add the following setting to your app.config file:</span></span>

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

<span data-ttu-id="f2d3b-543">この機能が有効な場合、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> オブジェクトは <xref:System.TimeZone> 型ではなく <xref:System.TimeZoneInfo> 型を使用して、日時データを逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-543">When this feature is enabled, a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object uses the <xref:System.TimeZoneInfo> type instead of the <xref:System.TimeZone> type to deserialize date and time data.</span></span> <span data-ttu-id="f2d3b-544"><xref:System.TimeZoneInfo> では、<xref:System.TimeZone> でサポートされない複数の調整規則がサポートされるため、過去のタイム ゾーン データを操作できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-544"><xref:System.TimeZoneInfo> supports multiple adjustment rules, which makes it possible to work with historic time zone data;   <xref:System.TimeZone> does not.</span></span>

<span data-ttu-id="f2d3b-545"><xref:System.TimeZoneInfo> 構造体とタイム ゾーン調整の詳細については、「[タイム ゾーンの概要](../../standard/datetime/time-zone-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-545">For more information on the <xref:System.TimeZoneInfo> structure and time zone adjustments, see [Time Zone Overview](../../standard/datetime/time-zone-overview.md).</span></span>

<span data-ttu-id="f2d3b-546">**NetNamedPipeBinding の最適な一致**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-546">**NetNamedPipeBinding best match**</span></span>

<span data-ttu-id="f2d3b-547">WCF には、クライアント アプリケーションで設定できる新しいアプリ設定があります。これにより、クライアント アプリケーションは常に、要求したものと最も一致する URI でリッスンしているサービスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-547">WCF has a new app setting that can be set on client applications to ensure they always connect to the service listening on the URI that best matches the one that they request.</span></span> <span data-ttu-id="f2d3b-548">このアプリ設定が `false` (既定値) に設定されている場合、クライアントは <xref:System.ServiceModel.NetNamedPipeBinding> を使用して、要求した URI の部分文字列である URI でリッスンしているサービスへの接続を試行できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-548">With this app setting set to `false` (the default), it is possible for clients using <xref:System.ServiceModel.NetNamedPipeBinding> to attempt to connect to a service listening on a URI that is a substring of the requested URI.</span></span>

<span data-ttu-id="f2d3b-549">たとえば、クライアントが `net.pipe://localhost/Service1` でリッスンしているサービスに接続しようとしているときに、管理者特権で実行しているコンピューター上の別のサービスが `net.pipe://localhost` でリッスンしているとします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-549">For example, a client tries to connect to a service listening at `net.pipe://localhost/Service1`, but a different service on that machine running with administrator privilege is listening at `net.pipe://localhost`.</span></span> <span data-ttu-id="f2d3b-550">このアプリ設定が `false` に設定されている場合、クライアントは間違ったサービスに接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-550">With this app setting set to `false`, the client would attempt to connect to the wrong service.</span></span> <span data-ttu-id="f2d3b-551">アプリ設定を `true` に設定すれば、クライアントは常に最も一致するサービスに接続するようになります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-551">After setting the app setting to `true`, the client will always connect to the best matching service.</span></span>

> [!NOTE]
> <span data-ttu-id="f2d3b-552"><xref:System.ServiceModel.NetNamedPipeBinding> を使用するクライアントは、完全なエンドポイント アドレスではなく、サービスのベース アドレス (存在する場合) に基づいてサービスを検索します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-552">Clients using <xref:System.ServiceModel.NetNamedPipeBinding> find services based on the service's base address (if it exists) rather than the full endpoint address.</span></span> <span data-ttu-id="f2d3b-553">この設定が常に機能するようにするには、サービスは一意のベース アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-553">To ensure this setting always works the service should use a unique base address.</span></span>

<span data-ttu-id="f2d3b-554">この変更を有効にするには、以下のアプリ設定をクライアント アプリケーションの App.config ファイルまたは Web.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-554">To enable this change, add the following app setting to your client application's App.config or Web.config file:</span></span>

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="f2d3b-555">**SSL 3.0 が既定のプロトコルではなくなった**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-555">**SSL 3.0 is not a default protocol**</span></span>

<span data-ttu-id="f2d3b-556">トランスポート セキュリティで NetTcp を使用し、証明書の資格情報の種類を使用する場合、SSL 3.0 は、安全な接続のネゴシエーションに使用される既定のプロトコルではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-556">When using NetTcp with transport security and a credential type of certificate, SSL 3.0 is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="f2d3b-557">TLS 1.0 が NetTcp のプロトコル一覧に含まれているため、ほとんどの場合、既存のアプリには影響はないと考えられます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-557">In most cases, there should be no impact to existing apps, because TLS 1.0 is included in the protocol list for NetTcp.</span></span> <span data-ttu-id="f2d3b-558">既存のすべてのクライアントは TLS 1.0 以降を使用して接続をネゴシエートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-558">All existing clients should be able to negotiate a connection using at least TLS 1.0.</span></span> <span data-ttu-id="f2d3b-559">Ssl3 が必要な場合は、以下の構成メカニズムのいずれかを使用して、ネゴシエートされたプロトコルの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-559">If Ssl3 is required, use one of the following configuration mechanisms to add it to the list of negotiated protocols.</span></span>

- <span data-ttu-id="f2d3b-560"><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType> プロパティ</span><span class="sxs-lookup"><span data-stu-id="f2d3b-560">The <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType> property</span></span>

- <span data-ttu-id="f2d3b-561"><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> プロパティ</span><span class="sxs-lookup"><span data-stu-id="f2d3b-561">The <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property</span></span>

- <span data-ttu-id="f2d3b-562">[\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md) セクションの [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) セクション</span><span class="sxs-lookup"><span data-stu-id="f2d3b-562">The [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) section of the [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md) section</span></span>

- <span data-ttu-id="f2d3b-563">[\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) セクションの [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md) セクション</span><span class="sxs-lookup"><span data-stu-id="f2d3b-563">The [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md) section of the [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) section</span></span>

<a name="WPF462" />

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f2d3b-564">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-564">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f2d3b-565">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、Windows Presentation Foundation の次の領域の機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-565">In the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Presentation Foundation has been enhanced in the following areas:</span></span>

<span data-ttu-id="f2d3b-566">**グループの並べ替え**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-566">**Group sorting**</span></span>

<span data-ttu-id="f2d3b-567"><xref:System.Windows.Data.CollectionView> オブジェクトを使用してデータをグループ化するアプリケーションは、グループを並べ替える方法を明示的に宣言できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-567">An application that uses a <xref:System.Windows.Data.CollectionView> object to group data can now explicitly declare how to  sort the groups.</span></span> <span data-ttu-id="f2d3b-568">明示的な並べ替えにより、アプリがグループを動的に追加または削除する場合や、グループ化に関連する項目のプロパティの値を変更する場合に発生する非直感的な順序付けの問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-568">Explicit sorting addresses the problem of non-intuitive ordering that occurs when an app dynamically adds or removes groups, or when it changes the value of item properties involved in grouping.</span></span> <span data-ttu-id="f2d3b-569">また、グループ化プロパティの比較がコレクション全体の並べ替えからグループの並べ替えに変更されるため、グループ作成プロセスのパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-569">It can also improve the performance of the group creation process by moving comparisons of the grouping properties from the sort of the full collection to the sort of the groups.</span></span>

<span data-ttu-id="f2d3b-570">グループの並べ替えをサポートするために、新しい <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> および <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> プロパティで、<xref:System.ComponentModel.GroupDescription> オブジェクトによって生成されるグループのコレクションを並べ替える方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-570">To support group sorting, the new <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> and <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> properties describe how to sort the collection of groups produced by the <xref:System.ComponentModel.GroupDescription> object.</span></span> <span data-ttu-id="f2d3b-571">これは、同じ名前の <xref:System.Windows.Data.ListCollectionView> プロパティでデータ項目を並べ替える方法を示すのと同様です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-571">This is analogous to the way the identically named <xref:System.Windows.Data.ListCollectionView> properties describe how to sort the data items.</span></span>

<span data-ttu-id="f2d3b-572"><xref:System.Windows.Data.PropertyGroupDescription> クラスの新しい 2 つの静的プロパティである <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> と <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A> は、最も一般的なケースで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-572">Two new static properties of the <xref:System.Windows.Data.PropertyGroupDescription> class,  <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> and <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, can be used for the most common cases.</span></span>

<span data-ttu-id="f2d3b-573">たとえば、次の XAML ではデータを年齢でグループ化し、年齢グループを昇順に並べ替え、各年齢グループ内の項目を姓でグループ化します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-573">For example, the following XAML groups data by age, sort the age groups in ascending order, and group the items within each age group by last name.</span></span>

```xaml
<GroupDescriptions>
     <PropertyGroupDescription
         PropertyName="Age"
         CustomSort=
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

<span data-ttu-id="f2d3b-574">**ソフト キーボードのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-574">**Soft keyboard support**</span></span>

<span data-ttu-id="f2d3b-575">ソフト キーボードのサポートにより、WPF アプリケーションでのフォーカス追跡が可能になります。テキスト入力が可能なコントロールによりタッチ入力を受信すると、Windows 10 の新しいソフト キーボードが自動的に起動および終了します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-575">Soft Keyboard support enables focus tracking in a WPF applications by automatically invoking and dismissing the new Soft Keyboard in Windows 10 when the touch input is received by a control that can take textual input.</span></span>

<span data-ttu-id="f2d3b-576">.NET Framework の以前のバージョンでは、WPF アプリケーションは、WPF のペン/タッチ ジェスチャ サポートを無効にしないとフォーカス追跡を選択できません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-576">In previous versions of the .NET Framework, WPF applications cannot opt into the focus tracking without disabling WPF pen/touch gesture support.</span></span>  <span data-ttu-id="f2d3b-577">そのため、WPF アプリケーションは完全な WPF タッチのフル サポートを選ぶか、Windows のマウス プロモーションに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-577">As a result, WPF applications must choose between full WPF touch support or rely on Windows mouse promotion.</span></span>

<span data-ttu-id="f2d3b-578">**モニターごとの DPI**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-578">**Per-monitor DPI**</span></span>

<span data-ttu-id="f2d3b-579">WPF アプリ用の高 DPI とハイブリッド DPI 環境の最近の急激な増加に対応するために、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] の WPF でモニターごとに対応できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-579">To support the recent proliferation of high-DPI and hybrid-DPI environments for WPF apps, WPF in the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] enables per-monitor awareness.</span></span> <span data-ttu-id="f2d3b-580">ご使用の WPF アプリでモニターごとの DPI 対応を有効にする方法の詳細については、GitHub の[サンプルと開発者向けガイド](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-580">See the [samples and developer guide](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) on GitHub for more information about how to enable your WPF app to become per-monitor DPI aware.</span></span>

<span data-ttu-id="f2d3b-581">.NET Framework の以前のバージョンでは、WPF アプリはシステム DPI 対応です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-581">In previous versions of the .NET Framework, WPF apps are system-DPI aware.</span></span> <span data-ttu-id="f2d3b-582">つまり、アプリケーションの UI は、アプリがレンダリングされるモニターの DPI に基づき、必要に応じて OS でスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-582">In other words, the application's UI is scaled by the OS as appropriate, depending on the DPI of the monitor on which the app is rendered.</span></span> <span data-ttu-id="f2d3b-583">,</span><span class="sxs-lookup"><span data-stu-id="f2d3b-583">,</span></span>

<span data-ttu-id="f2d3b-584">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で実行されるアプリの場合、次のように、アプリケーションの構成ファイルの [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) セクションに構成ステートメントを追加して、WPF アプリでモニターごとの DPI 変更を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-584">For apps running under the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], you can disable per-monitor DPI changes in WPF apps by adding a configuration statement to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file, as follows:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462" />

### <a name="windows-workflow-foundation-wf"></a><span data-ttu-id="f2d3b-585">Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-585">Windows Workflow Foundation (WF)</span></span>

<span data-ttu-id="f2d3b-586">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、Windows Workflow Foundation の次領域の機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-586">In the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Workflow Foundation has been enhanced in the following area:</span></span>

<span data-ttu-id="f2d3b-587">**再ホストされた WF デザイナーにおける C# 式と IntelliSense のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-587">**Support for C# expressions and IntelliSense in the Re-hosted WF Designer**</span></span>

<span data-ttu-id="f2d3b-588">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 以降では、WF によって、Visual Studio デザイナーとコード ワークフローの両方で C# 式がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-588">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], WF supports C# expressions in both the Visual Studio Designer and in code workflows.</span></span> <span data-ttu-id="f2d3b-589">再ホストされたワークフロー デザイナーは WF の主な機能です。これにより、ワークフロー デザイナーを Visual Studio の外部のアプリケーション (WPF など) で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-589">The Re-hosted Workflow Designer is a key feature of WF that allows for the Workflow Designer to be in an application outside Visual Studio (for example, in WPF).</span></span>  <span data-ttu-id="f2d3b-590">Windows Workflow Foundation は、再ホストされたワークフロー デザイナーで C# 式と IntelliSense をサポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-590">Windows Workflow Foundation provides the ability to support C# expressions and IntelliSense in the Re-hosted Workflow Designer.</span></span> <span data-ttu-id="f2d3b-591">詳細については、[Windows Workflow Foundation のブログ](https://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-591">For more information, see the [Windows Workflow Foundation blog](https://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).</span></span>

<span data-ttu-id="f2d3b-592">`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] より前のバージョンの .NET Framework で、お客様が Visual Studio からワークフロー プロジェクトを再ビルドした場合、WF Designer IntelliSense は破損してしまいます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-592">`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` In versions of the .NET Framework prior to the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], WF Designer IntelliSense is broken when a customer rebuilds a workflow project from Visual Studio.</span></span> <span data-ttu-id="f2d3b-593">プロジェクトのビルドに成功しても、デザイナーでワークフローの種類が見つからず、**[エラー一覧]** ウィンドウにワークフローの種類が欠落していることを示す IntelliSense からの警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-593">While the project build is successful, the workflow types are not found on the designer, and warnings from IntelliSense for the missing workflow types appear in the **Error List** window.</span></span> <span data-ttu-id="f2d3b-594">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] はこの問題に対処し、IntelliSense を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-594">The [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] addresses this issue and makes IntelliSense available.</span></span>

<span data-ttu-id="f2d3b-595">**ワークフロー追跡を有効にしたワークフロー V1 アプリケーションを FIPS モードで実行**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-595">**Workflow V1 applications with Workflow Tracking on now run under FIPS-mode**</span></span>

<span data-ttu-id="f2d3b-596">FIPS コンプライアンス モードが有効なコンピューターで、ワークフロー追跡が有効なワークフロー バージョン 1 スタイルのアプリケーションを正常に実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-596">Machines with FIPS Compliance Mode enabled can now successfully run a workflow Version 1-style application with Workflow tracking on.</span></span> <span data-ttu-id="f2d3b-597">このシナリオを有効にするには、app.config ファイルを以下のように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-597">To enable this scenario, you must make the following change to your app.config file:</span></span>

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

<span data-ttu-id="f2d3b-598">このシナリオが有効でない場合、アプリケーションを実行すると、引き続き例外が生成され、"この実装は Windows プラットフォーム FIPS 検証暗号化アルゴリズムの一部ではありません" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-598">If this scenario is not enabled, running the application continues to generate an exception with the message, "This implementation is not part of the Windows Platform FIPS validated cryptographic algorithms."</span></span>

<span data-ttu-id="f2d3b-599">**Visual Studio ワークフロー デザイナーで動的更新を使用する場合のワークフローの改善**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-599">**Workflow Improvements when using Dynamic Update with Visual Studio Workflow Designer**</span></span>

<span data-ttu-id="f2d3b-600">ワークフロー デザイナー、フローチャート アクティビティ デザイナー、およびその他のワークフロー アクティビティ デザイナーで、<xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> メソッドを呼び出した後に保存されたワークフローが正常に読み込まれ、表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-600">The Workflow Designer, FlowChart Activity Designer, and other Workflow Activity Designers now successfully load and display workflows that have been saved after calling  the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f2d3b-601">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] より前のバージョンの .NET Framework では、<xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> を呼び出した後に保存されたワークフローの XAML ファイルを Visual Studio で読み込むと、以下の問題が発生する場合がありました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-601">In versions of the .NET Framework before the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], loading a XAML file in Visual Studio for a workflow that has been saved after calling <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> can result in the following issues:</span></span>

- <span data-ttu-id="f2d3b-602">ワークフロー デザイナーで XAML ファイルが正しく読み込めない (行の末尾に <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> がある場合)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-602">The Workflow Designer can't load the XAML file correctly (when the <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> is at the end of the line).</span></span>

- <span data-ttu-id="f2d3b-603">フローチャート アクティビティ デザイナーまたは他のワークフロー アクティビティ デザイナーで、アタッチされるプロパティの値ではなく既定の場所にすべてのオブジェクトが表示される場合がある。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-603">Flowchart Activity Designer or other Workflow Activity Designers may display all objects in their default locations as opposed to attached property values.</span></span>

<a name="clickonce-1" />

### <a name="clickonce"></a><span data-ttu-id="f2d3b-604">ClickOnce</span><span class="sxs-lookup"><span data-stu-id="f2d3b-604">ClickOnce</span></span>

<span data-ttu-id="f2d3b-605">ClickOnce が更新され、既にサポートされている 1.0 プロトコルに加え、TLS 1.1 と TLS 1.2 がサポートがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-605">ClickOnce has been updated to support TLS 1.1 and TLS 1.2 in addition to the 1.0 protocol, which it already supports.</span></span> <span data-ttu-id="f2d3b-606">ClickOnce が必要なプロトコルを自動的に検出するため、TLS 1.1 と 1.2 のサポートを有効にするために、ClickOnce アプリケーション内での追加の手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-606">ClickOnce automatically detects which protocol is required; no extra steps within the ClickOnce application are required to enable TLS 1.1 and 1.2 support.</span></span>

<a name="UWPConvert" />

### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a><span data-ttu-id="f2d3b-607">Windows フォームおよび WPF アプリの UWP アプリへの変換</span><span class="sxs-lookup"><span data-stu-id="f2d3b-607">Converting Windows Forms and WPF apps to  UWP apps</span></span>

<span data-ttu-id="f2d3b-608">Windows では、WPF および Windows フォーム アプリを含む、既存の Windows デスクトップ アプリを UWP (ユニバーサル Windows プラットフォーム) で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-608">Windows now offers capabilities to bring existing Windows desktop apps, including WPF and Windows Forms apps, to the Universal Windows Platform (UWP).</span></span> <span data-ttu-id="f2d3b-609">このテクノロジはブリッジとして機能し、既存のコード ベースを段階的に UWP に移行し、アプリをすべての Windows 10 デバイスで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-609">This technology acts as a bridge by enabling you to gradually migrate your existing code base to UWP, thereby bringing your app to all Windows 10 devices.</span></span>

<span data-ttu-id="f2d3b-610">変換後のデスクトップ アプリは UWP アプリのアプリ ID のようなアプリ ID を取得し、UWP API をアクセス可能にして、ライブ タイルや通知などの機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-610">Converted desktop apps gain an app identity similar to the app identity of UWP apps, which makes UWP APIs accessible to enable features such as Live Tiles and notifications.</span></span> <span data-ttu-id="f2d3b-611">アプリは引き続き従来どおり動作し、完全信頼アプリとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-611">The app continues to behave as before and runs as a full trust app.</span></span> <span data-ttu-id="f2d3b-612">アプリが変換されたら、アプリ コンテナー プロセスを既存の完全信頼プロセスに追加し、適応ユーザー インターフェイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-612">Once the app is converted, an app container process can be added to the existing full trust process to add an adaptive user interface.</span></span> <span data-ttu-id="f2d3b-613">すべての機能がアプリ コンテナー プロセスに移行されたら、完全信頼プロセスを削除し、新しい UWP アプリをすべての Windows 10 デバイスで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-613">When all functionality is moved to the app container process, the full trust process can be removed and the new UWP app can be made available to all Windows 10 devices.</span></span>

<a name="Debug462" />

### <a name="debugging-improvements"></a><span data-ttu-id="f2d3b-614">デバッグの機能強化</span><span class="sxs-lookup"><span data-stu-id="f2d3b-614">Debugging improvements</span></span>

<span data-ttu-id="f2d3b-615">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で *アンマネージ デバッグ API* が強化され、<xref:System.NullReferenceException> がスローされたときに、ソース コードの単一行でどの変数が `null` になっているかを判別できるように、さらに分析されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-615">The *unmanaged debugging API* has been enhanced in the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] to perform additional analysis when a <xref:System.NullReferenceException> is thrown so that it is possible to determine which variable in a single line of source code is `null`.</span></span>   <span data-ttu-id="f2d3b-616">このシナリオをサポートするために、次の API がアンマネージ デバッグ API に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-616">To support this scenario, the following APIs have been added to the unmanaged debugging API.</span></span>

- <span data-ttu-id="f2d3b-617">[ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md)、[ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md)、および [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) インターフェイス。これらは管理対象変数の元のホームを公開します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-617">The [ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md), and [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interfaces, which expose the native homes of managed variables.</span></span> <span data-ttu-id="f2d3b-618">これにより、デバッガーは、<xref:System.NullReferenceException> の発生時になんらかのコード フロー分析を行い、さかのぼって、`null` だった元の場所に対応する管理対象変数を判別できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-618">This enables debuggers to do some code flow analysis when a  <xref:System.NullReferenceException> occurs and to work backwards to determine the managed variable that corresponds to the native location that was `null`.</span></span>

- <span data-ttu-id="f2d3b-619">[ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) メソッドでは ICorDebugType を [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) にマッピングできます。これにより、デバッガーは、ICorDebugType のインスタンスがなくても [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-619">The [ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method provides a mapping for ICorDebugType to [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md), which allows the debugger to obtain a [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) without an instance of the ICorDebugType.</span></span> <span data-ttu-id="f2d3b-620">その後、[COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) で既存の API を使用して、型のクラス レイアウトを判別できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-620">Existing APIs on [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) can then be used to determine the class layout of the type.</span></span>

<a name="v461" />

## <a name="whats-new-in-the-net-framework-461"></a><span data-ttu-id="f2d3b-621">.NET Framework 4.6.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-621">What's new in the .NET Framework 4.6.1</span></span>

<span data-ttu-id="f2d3b-622">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] には、次の領域における新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-622">The [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] includes new features in the following areas:</span></span>

- [<span data-ttu-id="f2d3b-623">暗号</span><span class="sxs-lookup"><span data-stu-id="f2d3b-623">Cryptography</span></span>](#Crypto)

- [<span data-ttu-id="f2d3b-624">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-624">ADO.NET</span></span>](#ADO.NET461)

- [<span data-ttu-id="f2d3b-625">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-625">Windows Presentation Foundation (WPF)</span></span>](#WPF461)

- [<span data-ttu-id="f2d3b-626">Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="f2d3b-626">Windows Workflow Foundation</span></span>](#WWF461)

- [<span data-ttu-id="f2d3b-627">プロファイル</span><span class="sxs-lookup"><span data-stu-id="f2d3b-627">Profiling</span></span>](#Profile461)

- [<span data-ttu-id="f2d3b-628">NGen</span><span class="sxs-lookup"><span data-stu-id="f2d3b-628">NGen</span></span>](#NGEN461)

<span data-ttu-id="f2d3b-629">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-629">For more information on the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], see the following topics:</span></span>

- <span data-ttu-id="f2d3b-630">[.NET Framework 4.6.1 の変更の一覧](https://go.microsoft.com/fwlink/?LinkId=622964)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-630">The [.NET Framework 4.6.1 list of changes](https://go.microsoft.com/fwlink/?LinkId=622964)</span></span>

- [<span data-ttu-id="f2d3b-631">4.6.1 でのアプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="f2d3b-631">Application Compatibility in 4.6.1</span></span>](../migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

- <span data-ttu-id="f2d3b-632">[.NET Framework API の diff (差分)](https://go.microsoft.com/fwlink/?LinkId=622989) (GitHub 上)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-632">[The .NET Framework API diff](https://go.microsoft.com/fwlink/?LinkId=622989) (on GitHub)</span></span>

<a name="Crypto" />

### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a><span data-ttu-id="f2d3b-633">暗号: ECDSA を含む X509 証明書のサポート</span><span class="sxs-lookup"><span data-stu-id="f2d3b-633">Cryptography: Support for X509 certificates containing ECDSA</span></span>

<span data-ttu-id="f2d3b-634">.NET Framework 4.6 では、X509 証明書の RSACng サポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-634">The .NET Framework 4.6 added RSACng support for X509 certificates.</span></span> <span data-ttu-id="f2d3b-635">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] では、ECDSA (Elliptic Curve Digital Signature Algorithm: 楕円曲線デジタル署名アルゴリズム) X509 証明書のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-635">The [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] adds support for ECDSA (Elliptic Curve Digital Signature Algorithm) X509 certificates.</span></span>

<span data-ttu-id="f2d3b-636">ECDSA は、RSA よりも安全な暗号化アルゴリズムで、パフォーマンスも向上するため、トランスポート層セキュリティ (TLS) のパフォーマンスとスケーラビリティが問題になる場合に最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-636">ECDSA offers better performance and is a more secure cryptography algorithm than RSA, providing an excellent choice where Transport Layer Security (TLS) performance and scalability is a concern.</span></span> <span data-ttu-id="f2d3b-637">.NET Framework の実装では、既存の Windows 機能の呼び出しがラップされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-637">The .NET Framework implementation wraps calls into existing Windows functionality.</span></span>

<span data-ttu-id="f2d3b-638">次のサンプル コードでは、[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] での新しい ECDSA X509 証明書のサポートを使用してバイト ストリームの署名が簡単に生成できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-638">The following example code shows how easy it is to generate a signature for a byte stream by using the new  support for ECDSA  X509 certificates included in the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>

[!code-csharp[whatsnew.461.crypto#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
[!code-vb[whatsnew.461.crypto#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

<span data-ttu-id="f2d3b-639">このコードは、.NET Framework 4.6 での署名の生成に必要な次のコードとは大きく異なっています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-639">This offers a marked contrast to the code needed to generate a signature in the .NET Framework 4.6.</span></span>

[!code-csharp[whatsnew.461.crypto#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
[!code-vb[whatsnew.461.crypto#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461" />

### <a name="adonet"></a><span data-ttu-id="f2d3b-640">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-640">ADO.NET</span></span>

<span data-ttu-id="f2d3b-641">次のものが ADO.NET に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-641">The following have been added to ADO.NET:</span></span>

<span data-ttu-id="f2d3b-642">**ハードウェア保護キーに対する Always Encrypted のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-642">**Always Encrypted support for hardware protected keys**</span></span>

<span data-ttu-id="f2d3b-643">ADO.NET では、Always Encrypted 列 (常に暗号化される列) のマスター キーをハードウェア セキュリティ モジュール (HSM) に格納することが、ネイティブでサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-643">ADO.NET now supports storing Always Encrypted column master keys natively in Hardware Security Modules (HSMs).</span></span> <span data-ttu-id="f2d3b-644">このサポートによって、ユーザーは、HSM に格納された非対称キーを利用できます。カスタムの列マスター キー ストア プロバイダーを作成してからアプリケーションに登録する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-644">With this support, customers can leverage asymmetric keys stored in HSMs without having to write custom column master key store providers and registering them in applications.</span></span>

<span data-ttu-id="f2d3b-645">HSM に格納された列マスター キーで保護された Always Encrypted データにアクセスするには、HSM ベンダー提供の CSP プロバイダーまたは CNG キー ストア プロバイダーをアプリ サーバーまたはクライアント コンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-645">Customers need to install the HSM vendor-provided CSP provider or CNG key store providers on the app servers or client computers in order to access Always Encrypted data protected with column master keys stored in a HSM.</span></span>

<span data-ttu-id="f2d3b-646">**AlwaysOn に対する <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> の接続動作の向上**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-646">**Improved <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> connection behavior for AlwaysOn**</span></span>

<span data-ttu-id="f2d3b-647">SqlClient で、AlwaysOn 可用性グループ (AG) へのより高速な接続が自動的に提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-647">SqlClient now automatically provides faster connections to an AlwaysOn Availability Group (AG).</span></span> <span data-ttu-id="f2d3b-648">SqlClient では、アプリケーションが別のサブネット上の AlwaysOn 可用性グループ (AG) に接続しているかどうかを自動的に検出し、現在のアクティブなサーバーを迅速に探索し、そのサーバーへの接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-648">It transparently detects whether your application is connecting to an AlwaysOn availability group (AG) on a different subnet and quickly discovers the current active server and provides a connection to the server.</span></span> <span data-ttu-id="f2d3b-649">このリリースよりも前は、アプリケーションで接続文字列を設定し、`"MultisubnetFailover=true"` を含め、AlwaysOn 可用性グループに接続されていることを示す必要がありました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-649">Prior to this release, an application had to set the connection string to include `"MultisubnetFailover=true"` to indicate that it was connecting to an AlwaysOn Availability Group.</span></span> <span data-ttu-id="f2d3b-650">`true` への接続キーワードを設定しないと、アプリケーションで AlwaysOn 可用性グループに接続中にタイムアウトが発生する可能性がありました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-650">Without setting the connection keyword to `true`, an application might experience a timeout while connecting to an AlwaysOn Availability Group.</span></span> <span data-ttu-id="f2d3b-651">このリリースを使用すれば、アプリケーションで <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> を `true` に設定する必要が*なくなり*ます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-651">With this release, an application does *not* need to set <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> to `true` anymore.</span></span> <span data-ttu-id="f2d3b-652">Always On 可用性グループの SqlClient サポートの詳細については、「[高可用性障害復旧のための SqlClient サポート](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-652">For more information about SqlClient support for Always On Availability Groups, see [SqlClient Support for High Availability, Disaster Recovery](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).</span></span>

<a name="WPF461" />

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f2d3b-653">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-653">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f2d3b-654">Windows Presentation Foundation には、さまざまな改善と変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-654">Windows Presentation Foundation includes a number of improvements and changes.</span></span>

<span data-ttu-id="f2d3b-655">**パフォーマンスの向上**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-655">**Improved performance**</span></span>

<span data-ttu-id="f2d3b-656">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] で、タッチ イベントの開始の遅延が修正されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-656">The delay in firing touch events has been fixed in the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span> <span data-ttu-id="f2d3b-657">また、<xref:System.Windows.Controls.RichTextBox> コントロールの入力が高速入力時のレンダーのスレッドを停止させなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-657">In addition, typing in a <xref:System.Windows.Controls.RichTextBox> control no longer ties up the render thread during fast input.</span></span>

<span data-ttu-id="f2d3b-658">**スペル チェック機能の改善**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-658">**Spell checking improvements**</span></span>

<span data-ttu-id="f2d3b-659">WPF のスペル チェック機能が、追加の言語のスペル チェックのためにオペレーティング システムのサポートを利用するように、Windows 8.1 以降のバージョンで更新されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-659">The spell checker in WPF has been updated on Windows 8.1 and later versions to leverage operating system support for spell-checking additional languages.</span></span>  <span data-ttu-id="f2d3b-660">Windows 8.1 よりも前の Windows バージョンの機能の変更はありません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-660">There is no change in functionality on Windows versions prior to Windows 8.1.</span></span>

<span data-ttu-id="f2d3b-661">以前のバージョンの .NET Framework と同様に、<xref:System.Windows.Controls.TextBox> コントロールまたは <xref:System.Windows.Controls.RichTextBox> ブロック用の言語が、次の順序で情報を探すことによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-661">As in previous versions of the .NET Framework, the language for a <xref:System.Windows.Controls.TextBox> control ora <xref:System.Windows.Controls.RichTextBox> block is detected by looking for information in the following order:</span></span>

- <span data-ttu-id="f2d3b-662">`xml:lang` (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-662">`xml:lang`, if it is present.</span></span>

- <span data-ttu-id="f2d3b-663">現在の入力言語。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-663">Current input language.</span></span>

- <span data-ttu-id="f2d3b-664">現在のスレッド カルチャ。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-664">Current thread culture.</span></span>

<span data-ttu-id="f2d3b-665">WPF での言語サポートの詳細については、[.NET Framework 4.6.1 機能に関する WPF ブログの記事](https://go.microsoft.com/fwlink/?LinkID=691819)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-665">For additional information on language support in WPF, see the [WPF blog post on .NET Framework 4.6.1 features](https://go.microsoft.com/fwlink/?LinkID=691819).</span></span>

<span data-ttu-id="f2d3b-666">**ユーザーごとのユーザー辞書の追加サポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-666">**Additional support for per-user custom dictionaries**</span></span>

<span data-ttu-id="f2d3b-667">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] では、WPF で、グローバルに登録されているユーザー辞書が認識されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-667">In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], WPF recognizes custom dictionaries that are registered globally.</span></span> <span data-ttu-id="f2d3b-668">この機能は、ユーザー辞書をコントロールごとに登録する機能に加えて使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-668">This capability is available in addition to the ability to register them per-control.</span></span>

<span data-ttu-id="f2d3b-669">以前のバージョンの WPF では、ユーザー辞書で除外された単語とオートコレクト リストが認識されませんでした。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-669">In previous versions of WPF, custom dictionaries did not recognize Excluded Words and AutoCorrect lists.</span></span> <span data-ttu-id="f2d3b-670">`%AppData%\Microsoft\Spelling\<language tag>` ディレクトリに配置できるファイルの使用によって、これらが Windows 8.1 と Windows 10 でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-670">They are supported on Windows 8.1 and Windows 10 through the use of files that can be placed under the `%AppData%\Microsoft\Spelling\<language tag>` directory.</span></span>  <span data-ttu-id="f2d3b-671">これらのファイルには、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-671">The following rules apply to these files:</span></span>

- <span data-ttu-id="f2d3b-672">これらのファイルには、拡張子の .dic (追加された単語の場合)、.exc (除外された単語の場合)、または .acl (オートコレクトの場合) が付いている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-672">The files should have extensions of .dic (for added words), .exc (for excluded words), or .acl (for AutoCorrect).</span></span>

- <span data-ttu-id="f2d3b-673">これらのファイルは、バイト オーダー マーク (BOM) で始まる UTF-16 LE プレーン テキストである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-673">The files should be UTF-16 LE plaintext that starts with the Byte Order Mark (BOM).</span></span>

- <span data-ttu-id="f2d3b-674">それぞれの行は、1 つの単語 (追加および除外された単語の一覧内)、または単語が縦棒 ("&#124;") で区切られたオートコレクトのペア (オートコレクトの単語の一覧内) で構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-674">Each line should consist of a word (in the added and excluded word lists), or an autocorrect pair with the words separated by a vertical bar ("&#124;") (in the AutoCorrect word list).</span></span>

- <span data-ttu-id="f2d3b-675">これらのファイルは読み取り専用と見なされ、システムによって変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-675">These files are considered read-only and are not modified by the system.</span></span>

> [!NOTE]
> <span data-ttu-id="f2d3b-676">これらの新しいファイル形式は、WPF スペル チェック API で直接サポートされるわけではありません。また、アプリケーションで WPF に提供されるユーザー辞書では以前と同様に .lex ファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-676">These new file-formats are not directly supported by the WPF spell checking APIs, and the custom dictionaries supplied to WPF in applications should continue to use .lex files.</span></span>

<span data-ttu-id="f2d3b-677">**サンプル**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-677">**Samples**</span></span>

<span data-ttu-id="f2d3b-678">WPF のサンプルは、[Microsoft/WPF サンプル](https://github.com/Microsoft/WPF-Samples) GitHub リポジトリにいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-678">There are a number of WPF samples on the [Microsoft/WPF-Samples](https://github.com/Microsoft/WPF-Samples) GitHub repository.</span></span> <span data-ttu-id="f2d3b-679">プル要求を送信するか、または[GitHub issue (GitHub の問題)](https://github.com/Microsoft/WPF-Samples/issues) を開いて、これらのサンプルの改善にご協力ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-679">Help us improve our samples by sending us a pull-request or opening a [GitHub issue](https://github.com/Microsoft/WPF-Samples/issues).</span></span>

<span data-ttu-id="f2d3b-680">**DirectX の拡張機能**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-680">**DirectX extensions**</span></span>

<span data-ttu-id="f2d3b-681">WPF には、DX10 および Dx11 のコンテンツとの相互運用を容易にする、<xref:System.Windows.Interop.D3DImage> の新しい実装を提供する [NuGet パッケージ](https://go.microsoft.com/fwlink/?LinkID=691342)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-681">WPF includes a [NuGet package](https://go.microsoft.com/fwlink/?LinkID=691342) that provides new implementations of <xref:System.Windows.Interop.D3DImage> that make it easy for you to interoperate with DX10 and Dx11 content.</span></span> <span data-ttu-id="f2d3b-682">このパッケージのコードはオープン ソース化されており、[GitHub で](https://github.com/Microsoft/WPFDXInterop)入手できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-682">The code for this package has been open sourced and is available [on GitHub](https://github.com/Microsoft/WPFDXInterop).</span></span>

<a name="WWF461" />

### <a name="windows-workflow-foundation-transactions"></a><span data-ttu-id="f2d3b-683">Windows Workflow Foundation: トランザクション</span><span class="sxs-lookup"><span data-stu-id="f2d3b-683">Windows Workflow Foundation: Transactions</span></span>

<span data-ttu-id="f2d3b-684"><xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> メソッドで、MSDTC 以外の分散トランザクション マネージャーを使用して、トランザクションをプロモート (昇格) できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-684">The <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> method can now use a distributed transaction manager other than MSDTC to promote the transaction.</span></span> <span data-ttu-id="f2d3b-685">このプロモートは、新しい <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> オーバーロードに GUID のトランザクション プロモーター識別子を指定することによって行います。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-685">You do this by specifying a GUID transaction promoter identifier to the  new <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> overload .</span></span> <span data-ttu-id="f2d3b-686">この操作が成功すると、そのトランザクションの機能に制限が加えられます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-686">If this operation is successful, there are limitations placed on the capabilities of the transaction.</span></span> <span data-ttu-id="f2d3b-687">MSDTC 以外のトランザクション プロモーターが登録される (参加する) と、次の各メソッドで MSDTC へのプロモートが必要になるため、これらのメソッドで <xref:System.Transactions.TransactionPromotionException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-687">Once a non-MSDTC transaction promoter is enlisted, the following methods throw a <xref:System.Transactions.TransactionPromotionException> because these methods require promotion to MSDTC:</span></span>

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

<span data-ttu-id="f2d3b-688">MSDTC 以外のトランザクション プロモーターが登録されると、そのプロモーターで定義するプロトコルを使用することで、そのプロモーターをその後の永続参加リストに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-688">Once a non-MSDTC transaction promoter is enlisted, it must be used for future durable enlistments by using protocols that it defines.</span></span> <span data-ttu-id="f2d3b-689">トランザクション プロモーターの <xref:System.Guid> は、<xref:System.Transactions.Transaction.PromoterType%2A> プロパティを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-689">The <xref:System.Guid> of the transaction promoter can be obtained by using the <xref:System.Transactions.Transaction.PromoterType%2A> property.</span></span> <span data-ttu-id="f2d3b-690">トランザクションがプロモートする際、トランザクション プロモーターによって、プロモート済みトークンを表す <xref:System.Byte> 配列が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-690">When the transaction promotes, the transaction promoter provides a <xref:System.Byte> array that represents the promoted token.</span></span> <span data-ttu-id="f2d3b-691">アプリケーションで、MSDTC 以外のプロモート済みトランザクションのプロモート済みトークンを <xref:System.Transactions.Transaction.GetPromotedToken%2A> メソッドを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-691">An application can obtain the promoted token for a non-MSDTC promoted transaction with the <xref:System.Transactions.Transaction.GetPromotedToken%2A> method.</span></span>

<span data-ttu-id="f2d3b-692">新しい <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> オーバーロードのユーザーは、プロモーション操作が正常に完了するように、特定の呼び出しシーケンスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-692">Users of the new <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> overload must follow a specific call sequence in order for the promotion operation to complete successfully.</span></span> <span data-ttu-id="f2d3b-693">これらの規則は、メソッドのドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-693">These rules are documented in the method's documentation.</span></span>

<a name="Profile461" />

### <a name="profiling"></a><span data-ttu-id="f2d3b-694">プロファイル</span><span class="sxs-lookup"><span data-stu-id="f2d3b-694">Profiling</span></span>

<span data-ttu-id="f2d3b-695">アンマネージド プロファイリング API が、次のように拡張されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-695">The unmanaged profiling API has been enhanced as follows:</span></span>

- <span data-ttu-id="f2d3b-696">[ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) インターフェイス内の PDB へのアクセスのサポートが向上。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-696">Better support for accessing PDBs in the [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) interface.</span></span>

   <span data-ttu-id="f2d3b-697">ASP.NET Core では、アセンブリがメモリ内で Roslyn によってコンパイルされることがよりいっそう一般的になっています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-697">In ASP.NET Core, it is becoming much more common for assemblies to be compiled in-memory by Roslyn.</span></span> <span data-ttu-id="f2d3b-698">プロファイル ツールを作成する開発者にとって、これは従来ディスクにシリアル化されていた PDB が存在しなくなる可能性があることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-698">For developers making profiling tools, this means that PDBs that historically were serialized on disk may no longer be present.</span></span> <span data-ttu-id="f2d3b-699">プロファイル ツールでは、多くの場合 PDB を使用して、コード カバレッジや 1 行単位のパフォーマンス分析などのタスクのソース行に、コードをマップし戻します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-699">Profiler tools often use PDBs to map code back to source lines for tasks such as code coverage or line-by-line performance analysis.</span></span> <span data-ttu-id="f2d3b-700">[ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) インターフェイスは、メモリ内の PDB データにアクセスして、これらのプロファイル ツールを提供する 2 つの新しいメソッド、[ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) と [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md) を含むようになりました。これらの新しい API を使用すれば、プロファイラーでメモリ内の PDB の内容をバイト配列として取得してから、それを処理したり、ディスクにシリアル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-700">The [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) interface now includes two new methods, [ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) and [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), to provide these profiler tools with access to the in-memory PDB data, By using the new APIs, a profiler can obtain the contents of an in-memory PDB as a byte array and then process it or serialize it to disk.</span></span>

- <span data-ttu-id="f2d3b-701">ICorProfiler インターフェイスを使用したインストルメンテーションの改善。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-701">Better instrumentation with the ICorProfiler interface.</span></span>

   <span data-ttu-id="f2d3b-702">動的インストルメンテーションに `ICorProfiler` API ReJit 機能を使用しているプロファイラーで、いくつかのメタデータを変更できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-702">Profilers that are using the `ICorProfiler` APIs ReJit functionality for dynamic instrumentation can now modify some metadata.</span></span> <span data-ttu-id="f2d3b-703">従来、このようなツールでは、いつでも IL をインストルメント化できましたが、メタデータを変更できるのはモジュールを読み込む時だけでした。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-703">Previously such tools could instrument IL at any time, but metadata could only be modified at module load time.</span></span> <span data-ttu-id="f2d3b-704">IL はメタデータを参照するため、実行できるインストルメンテーションの種類が限られています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-704">Because IL refers to metadata, this limited the kinds of instrumentation that could be done.</span></span> <span data-ttu-id="f2d3b-705">モジュールの読み込み後のメタデータの編集のサブセットをサポートするために、[ICorProfilerInfo7::ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) メソッドを追加することで (特に新しい `AssemblyRef`、`TypeRef`、`TypeSpec`、`MemberRef`、`MemberSpec`、および `UserString` の各レコードを追加することで)、これらの制限の一部を解消しました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-705">We have lifted some of those limits by adding the [ICorProfilerInfo7::ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) method to support a subset of metadata edits after the module loads, in particular by adding new `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec`, and `UserString` records.</span></span> <span data-ttu-id="f2d3b-706">この変更により、はるかに広範な実行時インストルメンテーションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-706">This change makes a much broader range of on-the-fly instrumentation possible.</span></span>

<a name="NGEN461" />

### <a name="native-image-generator-ngen-pdbs"></a><span data-ttu-id="f2d3b-707">ネイティブ イメージ ジェネレーター (NGEN) PDB</span><span class="sxs-lookup"><span data-stu-id="f2d3b-707">Native Image Generator (NGEN) PDBs</span></span>

<span data-ttu-id="f2d3b-708">マシン間のイベント トレースを使用すれば、ユーザーはマシン A 上でプログラムのプロファイリングを行い、マシン B 上でソース行のマッピングを使用して、プロファイリング データを確認できます。以前のバージョンの.NET Framework を使用する場合、ソースからネイティブへのマッピングを作成するには、ユーザーは、プロファイルされたコンピューターにあるすべてのモジュールとネイティブ イメージを、IL PDB が含まれた分析用コンピューターにコピーする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-708">Cross-machine event tracing allows customers to profile a program on Machine A and look at the profiling data with source line mapping on Machine B. Using previous versions of the .NET Framework, the user would copy all the modules and native images from the profiled machine to the analysis machine that contains the IL PDB to create the source-to-native mapping.</span></span> <span data-ttu-id="f2d3b-709">この処理は、Phone アプリケーションなどファイル サイズが比較的小さい場合には高速に実行されますが、これらのファイルのサイズがデスクトップ システム上で非常に大きくなる可能性があり、その場合コピーにかなりの時間を要する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-709">While this process may work well when the files are relatively small, such as for phone applications, the files can be very large on desktop systems and require significant time to copy.</span></span>

<span data-ttu-id="f2d3b-710">NGen PDB を使用すれば、IL PDB に依存することなく、NGen で IL からネイティブへのマッピングが含まれた PDB を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-710">With Ngen PDBs, NGen can create a PDB that contains the IL-to-native mapping without a dependency on the IL PDB.</span></span> <span data-ttu-id="f2d3b-711">このマシン間のイベント トレース シナリオで必要なことは、コンピューター A で生成されたネイティブ イメージの PDB をコンピューター B にコピーすることと、[Debug Interface Access API](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) を使用して IL PDB のソースから IL へのマッピングとネイティブ イメージの PDB の IL からネイティブへのマッピングを読み取ることだけです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-711">In our cross-machine event tracing scenario, all that is needed is to copy the native image PDB that is generated by Machine A to Machine B and to use [Debug Interface Access APIs](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) to read the IL PDB's source-to-IL mapping and the native image PDB's IL-to-native mapping.</span></span> <span data-ttu-id="f2d3b-712">両方のマッピングを組み合わせることで、ソースからネイティブへのマッピングが実現します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-712">Combining both mappings provides a source-to-native mapping.</span></span> <span data-ttu-id="f2d3b-713">ネイティブ イメージの PDB は、どのモジュールとネイティブ イメージよりもはるかにサイズが小さいため、コンピューター A からコンピューター B へのコピーの処理は非常に高速になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-713">Since the native image PDB is much smaller than all the modules and native images, the process of copying from Machine A to Machine B is much faster.</span></span>

<a name="v46" />

## <a name="whats-new-in-net-2015"></a><span data-ttu-id="f2d3b-714">.NET 2015 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-714">What's new in .NET 2015</span></span>

<span data-ttu-id="f2d3b-715">.NET 2015 では、[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] と .NET Core が導入されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-715">.NET 2015 introduces the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and .NET Core.</span></span> <span data-ttu-id="f2d3b-716">一部の新機能はその両方に適用され、その他の機能は [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] または [!INCLUDE[net_core](../../../includes/net-core-md.md)] に固有です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-716">Some new features apply to both, and other features are specific to [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] or [!INCLUDE[net_core](../../../includes/net-core-md.md)].</span></span>

- <span data-ttu-id="f2d3b-717">**ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-717">**ASP.NET Core**</span></span>

     <span data-ttu-id="f2d3b-718">.NET 2015 には、ASP.NET Core が含まれています。これは、最新のクラウド ベースのアプリを構築するのに効率的な .NET 実装です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-718">.NET 2015 includes ASP.NET Core, which is a lean .NET implementation for building modern cloud-based apps.</span></span> <span data-ttu-id="f2d3b-719">ASP.NET Core はモジュール形式であるため、ご利用のアプリケーションで必要な機能のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-719">ASP.NET Core is modular so you can include only those features that are needed in your application.</span></span> <span data-ttu-id="f2d3b-720">IIS でホストすることも、カスタムのプロセスでセルフホストすることもできます。さらに同じサーバー上のさまざまなバージョンの .NET Framework でアプリを実行することも可能です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-720">It can be hosted on IIS or self-hosted in a custom process, and you can run apps with different versions of the .NET Framework on the same server.</span></span> <span data-ttu-id="f2d3b-721">クラウド展開用に設計されている新たな環境構成システムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-721">It includes a new environment configuration system that is designed for cloud deployment.</span></span>

     <span data-ttu-id="f2d3b-722">MVC、Web API、および Web ページは、MVC 6 と呼ばれる 1 つのフレームワークに統合されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-722">MVC, Web API, and Web Pages are unified into a single framework called MVC 6.</span></span> <span data-ttu-id="f2d3b-723">Visual Studio 2015 以降のツールで ASP.NET Core アプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-723">You build ASP.NET Core apps through tools in Visual Studio 2015 or later.</span></span> <span data-ttu-id="f2d3b-724">既存のアプリケーションは、この新しい .NET Framework で動作しますが、MVC 6 または SignalR 3 を使用するアプリをビルドするには Visual Studio 2015 以降のプロジェクト システムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-724">Your existing applications will work on the new .NET Framework; however to build an app that uses MVC 6 or SignalR 3, you must use the project system in Visual Studio 2015 or later.</span></span>

     <span data-ttu-id="f2d3b-725">詳細については、[ASP.NET Core](/aspnet/core/) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-725">For information, see [ASP.NET Core](/aspnet/core/).</span></span>

- <span data-ttu-id="f2d3b-726">**ASP.NET の更新プログラム**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-726">**ASP.NET Updates**</span></span>

    - <span data-ttu-id="f2d3b-727">**非同期応答フラッシュ用のタスク ベース API**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-727">**Task-based API for Asynchronous Response Flushing**</span></span>

         <span data-ttu-id="f2d3b-728">ASP.NET で、非同期応答フラッシュ用の単純なタスク ベース API である <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType> が提供されるようになりました。これにより、言語の `async/await` サポートを使用して非同期的に応答をフラッシュできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-728">ASP.NET now provides a simple task-based API for asynchronous response flushing, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType>, that allows responses to be flushed asynchronously by using your language's `async/await` support.</span></span>

    - <span data-ttu-id="f2d3b-729">**モデル バインドによるタスクを返すメソッドのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-729">**Model binding supports task-returning methods**</span></span>

         <span data-ttu-id="f2d3b-730">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、Web フォーム ページやユーザー コントロールでの CRUD ベースのデータ操作に対して拡張可能なコード中心のアプローチを可能にするモデル バインド機能が ASP.NET に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-730">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], ASP.NET added the Model Binding feature that enabled an extensible, code-focused approach to CRUD-based data operations in Web Forms pages and user controls.</span></span> <span data-ttu-id="f2d3b-731">このモデル バインド システムで、<xref:System.Threading.Tasks.Task> を返すモデル バインド メソッドがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-731">The Model Binding system now supports <xref:System.Threading.Tasks.Task>-returning model binding methods.</span></span> <span data-ttu-id="f2d3b-732">この機能により、Web フォーム開発者は Entity Framework などの ORM の新しいバージョンを使用するときに、データ バインド システムのように簡単に非同期のスケーラビリティ上のメリットを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-732">This feature allows Web Forms developers to get the scalability benefits of async with the ease of the data-binding system when using newer versions of ORMs, including the Entity Framework.</span></span>

         <span data-ttu-id="f2d3b-733">非同期モデル バインドは、`aspnet:EnableAsyncModelBinding` 構成設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-733">Async model binding is controlled by the `aspnet:EnableAsyncModelBinding` configuration setting.</span></span>

        ```xml
        <appSettings>
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
        </appSettings>
        ```

         <span data-ttu-id="f2d3b-734">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] を対象とするアプリでは、既定で `true` になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-734">On apps the target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], it defaults to `true`.</span></span> <span data-ttu-id="f2d3b-735">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] で実行され、.NET Framework の以前のバージョンを対象とするアプリでは、既定で `false` になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-735">On apps running on the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] that target an earlier version of the .NET Framework, it is `false` by default.</span></span> <span data-ttu-id="f2d3b-736">有効にするには、この構成設定を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-736">It can be enabled by setting the configuration setting to `true`.</span></span>

    - <span data-ttu-id="f2d3b-737">**HTTP/2 のサポート (Windows 10)**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-737">**HTTP/2 Support (Windows 10)**</span></span>

         <span data-ttu-id="f2d3b-738">[HTTP/2](https://www.wikipedia.org/wiki/HTTP/2) は HTTP プロトコルの新しいバージョンで、接続の使用状況が (クライアントとサーバー間のラウンド トリップ数の減少により) 大幅に改善されて、ユーザーが Web ページを読み込むときの遅延が軽減されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-738">[HTTP/2](https://www.wikipedia.org/wiki/HTTP/2) is a new version of the HTTP protocol that provides much better connection utilization (fewer round-trips between client and server), resulting in lower latency web page loading for users.</span></span>  <span data-ttu-id="f2d3b-739">このプロトコルは単一のエクスペリエンスの一部として要求さる複数の成果物のために最適化されているので、HTTP/2 が最も役立つのは (サービスではなく) web ページです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-739">Web pages (as opposed to services) benefit the most from HTTP/2, since the protocol optimizes for multiple artifacts being requested as part of a single experience.</span></span> <span data-ttu-id="f2d3b-740">.NET Framework 4.6 では、HTTP/2 のサポートが ASP.NET に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-740">HTTP/2 support has been added to ASP.NET in the .NET Framework 4.6.</span></span> <span data-ttu-id="f2d3b-741">ネットワーク機能は複数のレイヤーで存在するので、HTTP/2 を有効にするために、Windows、IIS、および ASP.NET で新機能が必要とされていました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-741">Because networking functionality exists at multiple layers, new features were required in Windows, in IIS, and in ASP.NET to enable HTTP/2.</span></span> <span data-ttu-id="f2d3b-742">ASP.NET で HTTP/2 を使用するには、Windows 10 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-742">You must be running on Windows 10 to use HTTP/2 with ASP.NET.</span></span>

         <span data-ttu-id="f2d3b-743">HTTP/2 は、<xref:System.Net.Http.HttpClient?displayProperty=nameWithType> API を使用する Windows 10 ユニバーサル Windows プラットフォーム (UWP) アプリでもサポートされ、既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-743">HTTP/2 is also supported and on by default for Windows 10 Universal Windows Platform (UWP) apps that use the <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> API.</span></span>

         <span data-ttu-id="f2d3b-744">ASP.NET アプリケーションで [PUSH_PROMISE](https://http2.github.io/http2-spec/#PUSH_PROMISE) 機能を使用する手段を提供するために、<xref:System.Web.HttpResponse.PushPromise%28System.String%29> と <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29> の 2 つのオーバーロードを持つ新しいメソッドが <xref:System.Web.HttpResponse> クラスに追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-744">In order to provide a way to use the [PUSH_PROMISE](https://http2.github.io/http2-spec/#PUSH_PROMISE) feature in ASP.NET applications, a new method with two overloads, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> and <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, has been added to the <xref:System.Web.HttpResponse> class.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f2d3b-745">ASP.NET Core では HTTP/2 がサポートされますが、PUSH PROMISE 機能のサポートはまだ追加されていません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-745">While ASP.NET Core supports HTTP/2, support for the PUSH PROMISE feature has not yet been added.</span></span>

         <span data-ttu-id="f2d3b-746">ブラウザーと web サーバー (Windows 上の IIS) がすべての処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-746">The browser and the web server (IIS on Windows) do all the work.</span></span> <span data-ttu-id="f2d3b-747">ユーザーの側で複雑な操作を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-747">You don't have to do any heavy-lifting for your users.</span></span>

         <span data-ttu-id="f2d3b-748">[主要なブラウザーのほとんどは HTTP/2 をサポートしている](https://www.wikipedia.org/wiki/HTTP/2)ため、多くの場合、サーバーが HTTP/2 をサポートしていれば、ユーザーもそのメリットを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-748">Most of the [major browsers support HTTP/2](https://www.wikipedia.org/wiki/HTTP/2), so it's likely that your users will benefit from HTTP/2 support if your server supports it.</span></span>

    - <span data-ttu-id="f2d3b-749">**トークン バインディング プロトコルのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-749">**Support for the Token Binding Protocol**</span></span>

         <span data-ttu-id="f2d3b-750">Microsoft と Google は、[トークン バインディング プロトコル](https://github.com/TokenBinding/Internet-Drafts)と呼ばれる、認証のための新しいアプローチに共同で取り組んできました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-750">Microsoft and Google have been collaborating on a new approach to authentication, called the [Token Binding Protocol](https://github.com/TokenBinding/Internet-Drafts).</span></span> <span data-ttu-id="f2d3b-751">この前提となっているのは、犯罪者が (ブラウザー キャッシュ内の) 認証トークンを盗用することで、本来ならパスワードや他の特別な情報でセキュリティ保護されているリソース (銀行口座など) にアクセスできる可能性がある、ということです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-751">The premise is that authentication tokens (in your browser cache) can be stolen and used by criminals to access otherwise secure resources (e.g. your bank account) without requiring your password or any other privileged knowledge.</span></span> <span data-ttu-id="f2d3b-752">新しいプロトコルは、この問題を軽減することを目指しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-752">The new protocol aims to mitigate this problem.</span></span>

         <span data-ttu-id="f2d3b-753">トークン バインディング プロトコルは、Windows 10 でブラウザーの機能として実装されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-753">The Token Binding Protocol will be implemented in Windows 10 as a browser feature.</span></span> <span data-ttu-id="f2d3b-754">ASP.NET アプリは、認証トークンの正当性が検証されるように、このプロトコルに参加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-754">ASP.NET apps will participate in the protocol, so that authentication tokens are validated to be legitimate.</span></span> <span data-ttu-id="f2d3b-755">クライアントとサーバーの実装は、プロトコルによって指定されるエンド ツー エンドの保護を確立します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-755">The client and the server implementations establish the end-to-end protection specified by the protocol.</span></span>

    - <span data-ttu-id="f2d3b-756">**ランダムな文字列のハッシュ アルゴリズム**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-756">**Randomized string hash algorithms**</span></span>

         <span data-ttu-id="f2d3b-757">.NET Framework 4.5 で、[ランダム化された文字列のハッシュ アルゴリズム](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)が導入されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-757">The .NET Framework 4.5 introduced a [randomized string hash algorithm](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).</span></span> <span data-ttu-id="f2d3b-758">しかし、ASP.NET の一部の機能は安定したハッシュ コードに依存していたため、この機能は ASP.NET ではサポートされませんでした。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-758">However, it was not supported by ASP.NET because of some ASP.NET features depended on a stable hash code.</span></span> <span data-ttu-id="f2d3b-759">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] では、ランダムな文字列のハッシュ アルゴリズムがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-759">In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], randomized string hash algorithms are now supported.</span></span> <span data-ttu-id="f2d3b-760">この機能を有効にするには、`aspnet:UseRandomizedStringHashAlgorithm` 構成設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-760">To enable this feature, use the `aspnet:UseRandomizedStringHashAlgorithm` config setting.</span></span>

        ```xml
        <appSettings>
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
        </appSettings>
        ```

- <span data-ttu-id="f2d3b-761">**ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-761">**ADO.NET**</span></span>

     <span data-ttu-id="f2d3b-762">ADO .NET では、SQL Server 2016 Community Technology Preview 2 (CTP2) で使用できる Always Encrypted 機能がサポートされました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-762">ADO .NET now supports the Always Encrypted feature available in SQL Server 2016 Community Technology Preview 2 (CTP2).</span></span> <span data-ttu-id="f2d3b-763">SQL Server は、Always Encrypted 機能を使用して、暗号化されたデータに対して操作を実行できます。特に、サーバー上ではなく、ユーザーが信頼している環境内にアプリケーションと共に暗号化キーを保存できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-763">With Always Encrypted, SQL Server can perform operations on encrypted data, and best of all the encryption key resides with the application inside the customer’s trusted environment and not on the server.</span></span> <span data-ttu-id="f2d3b-764">Always Encrypted でユーザー データが保護されるので、DBA はプレーン テキスト データにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-764">Always Encrypted secures customer data so DBAs do not have access to plain text data.</span></span> <span data-ttu-id="f2d3b-765">データの暗号化と復号化は、ドライバー レベルで透過的に行われるので、既存のアプリケーションに対する変更が最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-765">Encryption and decryption of data happens transparently at the driver level, minimizing changes that have to be made to existing applications.</span></span> <span data-ttu-id="f2d3b-766">詳細については、「[Always Encrypted (データベース エンジン)](/sql/relational-databases/security/encryption/always-encrypted-database-engine)」および「[Always Encrypted (クライアント開発)](/sql/relational-databases/security/encryption/always-encrypted-client-development)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-766">For details, see [Always Encrypted (Database Engine)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) and [Always Encrypted (client development)](/sql/relational-databases/security/encryption/always-encrypted-client-development).</span></span>

- <span data-ttu-id="f2d3b-767">**マネージド コードの JIT コンパイラ (64 ビット)**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-767">**64-bit JIT Compiler for managed code**</span></span>

     <span data-ttu-id="f2d3b-768">.NET Framework 4.6 の特徴の 1 つとして、新しいバージョンの 64 ビット JIT コンパイラ (RyuJIT というコードネームで呼ばれていたもの) があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-768">The .NET Framework 4.6 features a new version of the 64-bit JIT compiler (originally code-named RyuJIT).</span></span> <span data-ttu-id="f2d3b-769">この新しい 64 ビット コンパイラは、これまでの 64 ビット JIT コンパイラよりもパフォーマンスが大幅に向上しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-769">The new 64-bit compiler provides significant performance improvements over the older 64-bit JIT compiler.</span></span> <span data-ttu-id="f2d3b-770">新しい 64 ビット コンパイラは、.NET Framework 4.6 上で実行される 64 ビット プロセスで有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-770">The new 64-bit compiler is enabled for 64-bit processes running on top of the .NET Framework 4.6.</span></span> <span data-ttu-id="f2d3b-771">64 ビットまたは AnyCPU としてコンパイルされ、64 ビット オペレーティング システム上で実行されるアプリは、64 ビットで動作します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-771">Your app will run in a 64-bit process if it is compiled as 64-bit or AnyCPU and is running on a 64-bit operating system.</span></span> <span data-ttu-id="f2d3b-772">新しいコンパイラへの移行をできる限り透過的に行うように注意を払いましたが、動作の変更が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-772">While care has been taken to make the transition to the new compiler as transparent as possible, changes in behavior are possible.</span></span> <span data-ttu-id="f2d3b-773">新しい JIT コンパイラの使用中に発生した問題については、直接お聞かせいただければと思います。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-773">We would like to hear directly about any issues encountered when using the new JIT compiler.</span></span> <span data-ttu-id="f2d3b-774">新しい 64 ビット JIT コンパイラに関連する可能性のある問題が発生した場合は、[Microsoft Connect](https://connect.microsoft.com/) にご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-774">Please contact us through [Microsoft Connect](https://connect.microsoft.com/) if you encounter an issue that may be related to the new 64-bit JIT compiler.</span></span>

     <span data-ttu-id="f2d3b-775">新しい 64 ビット JIT コンパイラには、ハードウェア SIMD アクセラレータ機能も含まれています。これを <xref:System.Numerics> 名前空間の SIMD 対応の型と組み合わせると、パフォーマンスが大幅に向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-775">The new 64-bit JIT compiler also includes hardware SIMD acceleration features when coupled with SIMD-enabled types in the <xref:System.Numerics> namespace, which can yield good performance improvements.</span></span>

- <span data-ttu-id="f2d3b-776">**アセンブリ ローダーの改善**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-776">**Assembly loader improvements**</span></span>

     <span data-ttu-id="f2d3b-777">アセンブリ ローダーで、対応する NGEN イメージの読み込み後に IL アセンブリをアンロードすることにより、メモリがより効率的に使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-777">The assembly loader now uses memory more efficiently by unloading IL assemblies after a corresponding NGEN image is loaded.</span></span> <span data-ttu-id="f2d3b-778">この変更は、仮想メモリが減少するため、特に大規模な 32 ビット アプリ (Visual Studio など) で有益であり、物理メモリの節約にもなります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-778">This change decreases virtual memory, which is particularly beneficial for large 32-bit apps (such as Visual Studio), and also saves physical memory.</span></span>

- <span data-ttu-id="f2d3b-779">**基本クラス ライブラリの変更点**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-779">**Base class library changes**</span></span>

     <span data-ttu-id="f2d3b-780">主なシナリオを利用できるようにするため、多くの新しい API が [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] に関連して追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-780">Many new APIs have been added around to [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] to enable key scenarios.</span></span> <span data-ttu-id="f2d3b-781">変更点と追加点を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-781">These include the following changes and additions:</span></span>

    - <span data-ttu-id="f2d3b-782">**IReadOnlyCollection\<T> implementations**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-782">**IReadOnlyCollection\<T> implementations**</span></span>

         <span data-ttu-id="f2d3b-783">追加のコレクション <xref:System.Collections.Generic.IReadOnlyCollection%601> (<xref:System.Collections.Generic.Queue%601>、<xref:System.Collections.Generic.Stack%601> など) が実装されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-783">Additional collections implement <xref:System.Collections.Generic.IReadOnlyCollection%601> such as <xref:System.Collections.Generic.Queue%601> and <xref:System.Collections.Generic.Stack%601>.</span></span>

    - <span data-ttu-id="f2d3b-784">**CultureInfo.CurrentCulture と CultureInfo.CurrentUICulture**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-784">**CultureInfo.CurrentCulture and CultureInfo.CurrentUICulture**</span></span>

         <span data-ttu-id="f2d3b-785"><xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> プロパティと <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> プロパティが読み取り専用ではなく、読み取り/書き込み可能になりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-785">The <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> properties are now read-write rather than read-only.</span></span> <span data-ttu-id="f2d3b-786">新しい <xref:System.Globalization.CultureInfo> オブジェクトをこれらのプロパティに割り当てると、`Thread.CurrentThread.CurrentCulture` プロパティで現在定義されているスレッド カルチャと、`Thread.CurrentThread.CurrentUICulture` プロパティで現在定義されている UI スレッド カルチャも変更されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-786">If you assign a new <xref:System.Globalization.CultureInfo> object to these properties, the current thread culture defined by the `Thread.CurrentThread.CurrentCulture` property and the current UI thread culture defined by the `Thread.CurrentThread.CurrentUICulture` properties also change.</span></span>

    - <span data-ttu-id="f2d3b-787">**ガベージ コレクション (GC) の機能強化**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-787">**Enhancements to garbage collection (GC)**</span></span>

         <span data-ttu-id="f2d3b-788"><xref:System.GC> クラスに <xref:System.GC.TryStartNoGCRegion%2A> メソッドと <xref:System.GC.EndNoGCRegion%2A> メソッドが含まれるようになりました。これらのメソッドを使用するとクリティカル パスの実行中にガベージ コレクションを不許可にできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-788">The <xref:System.GC> class now includes <xref:System.GC.TryStartNoGCRegion%2A> and <xref:System.GC.EndNoGCRegion%2A> methods that allow you to disallow garbage collection during the execution of a critical path.</span></span>

         <span data-ttu-id="f2d3b-789"><xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> メソッドの新しいオーバーロードを使用して、小さなオブジェクト ヒープと大きなオブジェクト ヒープの両方に関して、スイープして圧縮するのか、スイープのみを行うのかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-789">A new overload of the <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> method allows you to control whether both the small object heap and the large object heap are swept and compacted or swept only.</span></span>

    - <span data-ttu-id="f2d3b-790">**SIMD が有効な型**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-790">**SIMD-enabled types**</span></span>

         <span data-ttu-id="f2d3b-791"><xref:System.Numerics> 名前空間には、<xref:System.Numerics.Matrix3x2>、<xref:System.Numerics.Matrix4x4>、<xref:System.Numerics.Plane>、<xref:System.Numerics.Quaternion>、<xref:System.Numerics.Vector2>、<xref:System.Numerics.Vector3>、<xref:System.Numerics.Vector4> など、いくつかの SIMD 対応の型が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-791">The <xref:System.Numerics> namespace now includes a number of SIMD-enabled types, such as <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, and <xref:System.Numerics.Vector4>.</span></span>

         <span data-ttu-id="f2d3b-792">新しい 64 ビット JIT コンパイラにはハードウェア SIMD アクセラレータ機能も含まれているため、新しい 64 ビット JIT コンパイラで SIMD 対応の型を使用すると、パフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-792">Because the new 64-bit JIT compiler also includes hardware SIMD acceleration features, there are especially significant performance improvements when using the SIMD-enabled types with the new 64-bit JIT compiler.</span></span>

    - <span data-ttu-id="f2d3b-793">**暗号の更新**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-793">**Cryptography updates**</span></span>

         <span data-ttu-id="f2d3b-794"><xref:System.Security.Cryptography?displayProperty=nameWithType> API は、[Windows CNG 暗号化 API](/windows/desktop/SecCNG/cng-reference) をサポートするために更新中です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-794">The <xref:System.Security.Cryptography?displayProperty=nameWithType> API is being updated to support the [Windows CNG cryptography APIs](/windows/desktop/SecCNG/cng-reference).</span></span> <span data-ttu-id="f2d3b-795">以前のバージョンの .NET Framework は、<xref:System.Security.Cryptography?displayProperty=nameWithType> の実装の基礎として、[それより前のバージョンの Windows 暗号化 API](/windows/desktop/SecCrypto/cryptography-portal) に完全に依存していました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-795">Previous versions of the .NET Framework have relied entirely on an [earlier version of the Windows Cryptography APIs](/windows/desktop/SecCrypto/cryptography-portal) as the basis for the <xref:System.Security.Cryptography?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="f2d3b-796">CNG API は特定のカテゴリのアプリにとって重要な[最新の暗号アルゴリズム](/windows/desktop/SecCNG/cng-features#suite-b-support)をサポートするものであるため、CNG API をサポートしてほしいというリクエストが寄せられていました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-796">We have had requests to support the CNG API, since it supports [modern cryptography algorithms](/windows/desktop/SecCNG/cng-features#suite-b-support), which are important for certain categories of apps.</span></span>

         <span data-ttu-id="f2d3b-797">.NET Framework 4.6 には、Windows CNG 暗号化 API をサポートするために、次の新しい機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-797">The .NET Framework 4.6 includes the following new enhancements to support the Windows CNG cryptography APIs:</span></span>

        - <span data-ttu-id="f2d3b-798">可能な場合に CAPI ベースの実装ではなく CNG ベースの実装を返す X509 証明書用の一連の拡張メソッド `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` および `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` </span><span class="sxs-lookup"><span data-stu-id="f2d3b-798">A set of extension methods for X509 Certificates, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` and `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, that return a CNG-based implementation rather than a CAPI-based implementation when possible.</span></span> <span data-ttu-id="f2d3b-799">(一部のスマート カードなどでは現在も CAPI が必要であり、API がフォールバックを処理します)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-799">(Some smartcards, etc., still require CAPI, and the APIs handle the fallback).</span></span>

        - <span data-ttu-id="f2d3b-800">RSA アルゴリズムの CNG 実装を提供する <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> クラス。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-800">The <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> class, which provides a CNG implementation of the RSA algorithm.</span></span>

        - <span data-ttu-id="f2d3b-801">一般的な操作でキャストを不要にする RSA API の機能強化。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-801">Enhancements to the RSA API so that common actions no longer require casting.</span></span> <span data-ttu-id="f2d3b-802">たとえば、以前のバージョンの .NET Framework で <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> オブジェクトを使用してデータを暗号化するには、次のようなコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-802">For example, encrypting data using an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> object requires code like the following in previous versions of the .NET Framework.</span></span>

             [!code-csharp[WhatsNew.Casting#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
             [!code-vb[WhatsNew.Casting#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

             <span data-ttu-id="f2d3b-803">.NET Framework 4.6 で新しい暗号化を使用するコードは、次のように書き換えてキャストを回避することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-803">Code that uses the new cryptography APIs in the .NET Framework 4.6 can be rewritten as follows to avoid the cast.</span></span>

             [!code-csharp[WhatsNew.Casting#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
             [!code-vb[WhatsNew.Casting#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

    - <span data-ttu-id="f2d3b-804">**日付および時間と UNIX 時間の変換のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-804">**Support for converting dates and times to or from Unix time**</span></span>

         <span data-ttu-id="f2d3b-805">日付値および時間値と UNIX 時間の変換をサポートするため、次の新しいメソッドが <xref:System.DateTimeOffset> 構造体に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-805">The following new methods have been added to the <xref:System.DateTimeOffset> structure to support converting date and time values to or from Unix time:</span></span>

        - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - <span data-ttu-id="f2d3b-806">**互換性スイッチ**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-806">**Compatibility switches**</span></span>

         <span data-ttu-id="f2d3b-807">新しい <xref:System.AppContext> クラスは、ライブラリの作成者が統一された新機能のオプトアウト メカニズムをユーザーに提供できるようにする、新しい互換性機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-807">The new <xref:System.AppContext> class adds a new compatibility feature that enables library writers to provide a uniform opt-out mechanism for new functionality for their users.</span></span> <span data-ttu-id="f2d3b-808">これは、オプトアウト要求を伝達するために、コンポーネント間に疎結合のコントラクトを確立します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-808">It establishes a loosely-coupled contract between components in order to communicate an opt-out request.</span></span> <span data-ttu-id="f2d3b-809">通常、この機能は既存の機能が変更されるときに重要となります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-809">This capability is typically important when a change is made to existing functionality.</span></span> <span data-ttu-id="f2d3b-810">それに対して、新しい機能には暗黙のオプトインが既に存在しています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-810">Conversely, there is already an implicit opt-in for new functionality.</span></span>

         <span data-ttu-id="f2d3b-811"><xref:System.AppContext> によって、ライブラリは互換性スイッチを定義して公開します。また、それらに依存するコードは、それらのスイッチを設定してライブラリの動作に影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-811">With <xref:System.AppContext>, libraries define and expose compatibility switches, while code that depends on them can set those switches to affect the library behavior.</span></span> <span data-ttu-id="f2d3b-812">ライブラリは、既定では新しい機能を提供し、スイッチが設定されている場合のみそれを変更する (つまり以前の機能を提供する) ことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-812">By default, libraries provide the new functionality, and they only alter it (that is, they provide the previous functionality) if the switch is set.</span></span>

         <span data-ttu-id="f2d3b-813">アプリケーション (またはライブラリ) は、依存するライブラリが定義したスイッチの値 (常に <xref:System.Boolean> 値) を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-813">An application (or a library) can declare the value of a switch (which is always a <xref:System.Boolean> value) that a dependent library defines.</span></span> <span data-ttu-id="f2d3b-814">スイッチは常に暗黙的に `false` です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-814">The switch is always implicitly `false`.</span></span> <span data-ttu-id="f2d3b-815">スイッチを `true` に設定すると、それが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-815">Setting the switch to `true` enables it.</span></span> <span data-ttu-id="f2d3b-816">スイッチを明示的に `false` に設定すると、新しい動作が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-816">Explicitly setting the switch to `false` provides the new behavior.</span></span>

        ```csharp
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
        ```

         <span data-ttu-id="f2d3b-817">ライブラリは、コンシューマーがスイッチの値を宣言したことを確認してから、それを適切に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-817">The library must check if a consumer has declared the value of the switch and then appropriately act on it.</span></span>

        ```csharp
        if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))
        {
           // This is the case where the switch value was not set by the application.
           // The library can choose to get the value of shouldThrow by other means.
           // If no overrides nor default values are specified, the value should be 'false'.
           // A false value implies the latest behavior.
        }

           // The library can use the value of shouldThrow to throw exceptions or not.
           if (shouldThrow)
           {
              // old code
           }
           else {
              // new code
           }
        }
        ```

         <span data-ttu-id="f2d3b-818">スイッチは、ライブラリによって公開される正式なコントラクトであるため、一貫性のある形式を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-818">It's beneficial to use a consistent format for switches, since they are a formal contract exposed by a library.</span></span> <span data-ttu-id="f2d3b-819">2 つの明確な形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-819">The following are two obvious formats.</span></span>

        - <span data-ttu-id="f2d3b-820">*Switch*.*namespace*.*switchname*</span><span class="sxs-lookup"><span data-stu-id="f2d3b-820">*Switch*.*namespace*.*switchname*</span></span>

        - <span data-ttu-id="f2d3b-821">*Switch*.*library*.*switchname*</span><span class="sxs-lookup"><span data-stu-id="f2d3b-821">*Switch*.*library*.*switchname*</span></span>

    - <span data-ttu-id="f2d3b-822">**タスク ベースの非同期パターン (TAP) の変更点**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-822">**Changes to the task-based asynchronous pattern (TAP)**</span></span>

         <span data-ttu-id="f2d3b-823">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] をターゲットとするアプリの場合、<xref:System.Threading.Tasks.Task> オブジェクトと <xref:System.Threading.Tasks.Task%601> オブジェクトは、呼び出し元のスレッドのカルチャと UI カルチャを継承します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-823">For apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects inherit the culture and UI culture of the calling thread.</span></span> <span data-ttu-id="f2d3b-824">以前のバージョンの .NET Framework をターゲットするとアプリまたは特定のバージョンの .NET Framework をターゲットとしないアプリの動作には影響を及ぼしません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-824">The behavior of apps that target previous versions of the .NET Framework, or that do not target a specific version of the .NET Framework, is unaffected.</span></span> <span data-ttu-id="f2d3b-825">詳細については、<xref:System.Globalization.CultureInfo> クラスのトピックの「カルチャとタスク ベースの非同期の操作」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-825">For more information, see the "Culture and task-based asynchronous operations" section of the <xref:System.Globalization.CultureInfo> class topic.</span></span>

         <span data-ttu-id="f2d3b-826"><xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> クラスを使用すると、`async` メソッドなど、特定の非同期制御フローに対してローカルなアンビエント データを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-826">The <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> class allows you to represent ambient data that is local to a given asynchronous control flow, such as an `async` method.</span></span> <span data-ttu-id="f2d3b-827">これは、スレッド間でデータを保持するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-827">It can be used to persist data across threads.</span></span> <span data-ttu-id="f2d3b-828"><xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> プロパティの明示的な変更やスレッドでのコンテキスト変換の発生などによってアンビエント データが変更されるたびに通知されるコールバック メソッドを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-828">You can also define a callback method that is notified whenever the ambient data changes either because the <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> property was explicitly changed, or because the thread encountered a context transition.</span></span>

         <span data-ttu-id="f2d3b-829">タスク ベースの非同期パターン (TAP) に、特定の状態で完了したタスクを返す 3 つの便利なメソッド <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>、<xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType>、および <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType> が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-829">Three convenience methods, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType>, have been added to the task-based asynchronous pattern (TAP) to return completed tasks in a particular state.</span></span>

         <span data-ttu-id="f2d3b-830"><xref:System.IO.Pipes.NamedPipeClientStream> クラスで、新しい <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A> メソッドによる非同期通信がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-830">The <xref:System.IO.Pipes.NamedPipeClientStream> class now supports asynchronous communication with its new <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>.</span></span> <span data-ttu-id="f2d3b-831">メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-831">method.</span></span>

    - <span data-ttu-id="f2d3b-832">**EventSource がイベント ログへの書き込みをサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-832">**EventSource now supports writing to the Event log**</span></span>

         <span data-ttu-id="f2d3b-833">コンピューター上で作成された既存の ETW セッションに加えて、<xref:System.Diagnostics.Tracing.EventSource> クラスを使用して管理または操作メッセージをイベント ログに記録できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-833">You now can use the <xref:System.Diagnostics.Tracing.EventSource> class to log administrative or operational messages to the event log, in addition to any existing ETW sessions created on the machine.</span></span> <span data-ttu-id="f2d3b-834">以前は、この機能のために Microsoft.Diagnostics.Tracing.EventSource NuGet パッケージを使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-834">In the past, you had to use the Microsoft.Diagnostics.Tracing.EventSource NuGet package for this functionality.</span></span> <span data-ttu-id="f2d3b-835">この機能は .NET Framework 4.6 に組み込まれました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-835">This functionality is now built-into the .NET Framework 4.6.</span></span>

         <span data-ttu-id="f2d3b-836">NuGet パッケージと .NET Framework 4.6 は、どちらも次の機能によって更新されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-836">Both the NuGet package and the .NET Framework 4.6 have been updated with the following features:</span></span>

        - <span data-ttu-id="f2d3b-837">**ダイナミック イベント**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-837">**Dynamic events**</span></span>

             <span data-ttu-id="f2d3b-838">イベント メソッドを作成せずに、実行時にイベントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-838">Allows events defined "on the fly" without creating event methods.</span></span>

        - <span data-ttu-id="f2d3b-839">**リッチ ペイロード**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-839">**Rich payloads**</span></span>

             <span data-ttu-id="f2d3b-840">特別な属性が指定されたクラスや配列に加えて、プリミティブ型もペイロードとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-840">Allows specially attributed classes and arrays as well as primitive types to be passed as a payload</span></span>

        - <span data-ttu-id="f2d3b-841">**アクティビティの追跡**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-841">**Activity tracking**</span></span>

             <span data-ttu-id="f2d3b-842">Start イベントと Stop イベントの間のイベントに、現在アクティブなすべてのアクティビティを表す ID が付けられます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-842">Causes Start and Stop events to tag events between them with an ID that represents all currently active activities.</span></span>

         <span data-ttu-id="f2d3b-843">これらの機能をサポートするため、<xref:System.Diagnostics.Tracing.EventSource> クラスにオーバーロードされた <xref:System.Diagnostics.Tracing.EventSource.Write%2A> メソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-843">To support these features, the overloaded <xref:System.Diagnostics.Tracing.EventSource.Write%2A> method has been added to the <xref:System.Diagnostics.Tracing.EventSource> class.</span></span>

- <span data-ttu-id="f2d3b-844">**Windows Presentation Foundation (WPF)**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-844">**Windows Presentation Foundation (WPF)**</span></span>

    - <span data-ttu-id="f2d3b-845">**HDPI の強化**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-845">**HDPI improvements**</span></span>

         <span data-ttu-id="f2d3b-846">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] では、WPF での HDPI サポートが強化されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-846">HDPI support in WPF is now better in the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</span></span> <span data-ttu-id="f2d3b-847">境界があるコントロールでのクリッピングの発生を減らすため、レイアウトの丸め処理が変更されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-847">Changes have been made to layout rounding to reduce instances of clipping in controls with borders.</span></span> <span data-ttu-id="f2d3b-848">既定では、<xref:System.Runtime.Versioning.TargetFrameworkAttribute> が .NET 4.6 に設定されている場合にのみ、この機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-848">By default, this feature is enabled only if your <xref:System.Runtime.Versioning.TargetFrameworkAttribute> is set to .NET 4.6.</span></span>  <span data-ttu-id="f2d3b-849">以前のバージョンの Framework を対象とするアプリケーションが [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] で実行される場合は、app.config ファイルの [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) セクションに次の行を追加することで、新しい動作を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-849">Applications that target earlier versions of the framework but are running on the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt in to the new behavior by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app.config file:</span></span>

        ```xml
        <AppContextSwitchOverrides
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
        />
        ```

         <span data-ttu-id="f2d3b-850">異なる DPI 設定を持つ (マルチ DPI セットアップの) 複数のモニターにまたがる WPF ウィンドウは、ブラック アウト領域なしで完全にレンダリングされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-850">WPF windows straddling multiple monitors with different DPI settings (Multi-DPI setup) are now completely rendered without blacked-out regions.</span></span> <span data-ttu-id="f2d3b-851">この動作の選択を解除するには、app.config ファイルの `<appSettings>` セクションに次の行を追加して、この新しい動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-851">You can opt out of this behavior by adding the following line to the `<appSettings>` section of the app.config file to disable this new behavior:</span></span>

        ```xml
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>
        ```

         <span data-ttu-id="f2d3b-852">DPI 設定に基づいて自動的に正しいカーソルを読み込む機能のサポートが <xref:System.Windows.Input.Cursor?displayProperty=nameWithType> に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-852">Support for automatically loading the right cursor based on DPI setting has been added to  <xref:System.Windows.Input.Cursor?displayProperty=nameWithType>.</span></span>

    - <span data-ttu-id="f2d3b-853">**タッチの改善**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-853">**Touch is better**</span></span>

         <span data-ttu-id="f2d3b-854">タッチで予期しない動作が発生するという、お客様から報告された [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) の問題が [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] で対処されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-854">Customer reports on [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) that touch produces unpredictable behavior have been addressed in the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</span></span> <span data-ttu-id="f2d3b-855">Windows 8.1 以降では、Windows ストア アプリケーションと WPF アプリケーションのダブルタップのしきい値が同じになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-855">The double tap threshold for Windows Store applications and WPF applications is now the same in Windows 8.1 and above.</span></span>

    - <span data-ttu-id="f2d3b-856">**透過的な子ウィンドウのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-856">**Transparent child window support**</span></span>

         <span data-ttu-id="f2d3b-857">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] の WPF では、Windows 8.1 以降の透過的な子ウィンドウがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-857">WPF in the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] supports transparent child windows in Windows 8.1 and above.</span></span> <span data-ttu-id="f2d3b-858">これにより、最上位レベルのウィンドウ内に四角形でない透過的な子ウィンドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-858">This allows you to create non-rectangular and transparent child windows in your top-level windows.</span></span> <span data-ttu-id="f2d3b-859">この機能を有効にするには、<xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-859">You can enable this feature by setting the <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> property to `true`.</span></span>

- <span data-ttu-id="f2d3b-860">**Windows Communication Foundation (WCF)**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-860">**Windows Communication Foundation (WCF)**</span></span>

    - <span data-ttu-id="f2d3b-861">**SSL のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-861">**SSL support**</span></span>

         <span data-ttu-id="f2d3b-862">WCF で、NetTcp をトランスポート セキュリティおよびクライアント認証と共に使用する場合に、SSL のバージョンとして SSL 3.0 および TLS 1.0 に加えて TLS 1.1 および TLS 1.2 がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-862">WCF now supports SSL version TLS 1.1 and TLS 1.2, in addition to SSL 3.0 and TLS 1.0, when using NetTcp with transport security and client authentication.</span></span> <span data-ttu-id="f2d3b-863">使用するプロトコルを選択することも、安全性の低い古いプロトコルを無効化することもできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-863">It is now possible to select which protocol to use, or to disable old lesser secure protocols.</span></span> <span data-ttu-id="f2d3b-864">これを行うには、<xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> プロパティを設定するか、または構成ファイルに以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-864">This can be done either by setting the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> property or by adding the following to a configuration file.</span></span>

        ```xml
        <netTcpBinding>
           <binding>
              <security mode= "None|Transport|Message|TransportWithMessageCredential" >
                 <transport clientCredentialType="None|Windows|Certificate"
                            protectionLevel="None|Sign|EncryptAndSign"
                            sslProtocols="Ssl3|Tls1|Tls11|Tls12">
                    </transport>
              </security>
           </binding>
        </netTcpBinding>
        ```

    - <span data-ttu-id="f2d3b-865">**異なる HTTP 接続によるメッセージの送信**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-865">**Sending messages using different HTTP connections**</span></span>

         <span data-ttu-id="f2d3b-866">WCF で、ユーザーが別の基になる HTTP 接続を使用して特定のメッセージを送信できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-866">WCF now allows users to ensure certain messages are sent using different underlying HTTP connections.</span></span> <span data-ttu-id="f2d3b-867">これには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-867">There are two ways to do this:</span></span>

        - <span data-ttu-id="f2d3b-868">**接続グループ名プレフィックスの使用**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-868">**Using a connection group name prefix**</span></span>

             <span data-ttu-id="f2d3b-869">ユーザーは、WCF で接続グループ名のプレフィックスとして使用される文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-869">Users can specify a string that WCF will use as a prefix for the connection group name.</span></span> <span data-ttu-id="f2d3b-870">異なるプレフィックスを持つ 2 つのメッセージは、別の基になる HTTP 接続を使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-870">Two messages with different prefixes are sent using different underlying HTTP connections.</span></span> <span data-ttu-id="f2d3b-871">プレフィックスを設定するには、メッセージの <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> プロパティにキー/値のペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-871">You set the prefix by adding a key/value pair to the message's <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f2d3b-872">キーは "HttpTransportConnectionGroupNamePrefix" で、値は使用するプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-872">The key is "HttpTransportConnectionGroupNamePrefix"; the value is the desired prefix.</span></span>

        - <span data-ttu-id="f2d3b-873">**異なるチャネル ファクトリの使用**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-873">**Using different channel factories**</span></span>

             <span data-ttu-id="f2d3b-874">ユーザーは、異なるチャネル ファクトリによって作成されたチャネルを使用して送信されるメッセージで別の基になる HTTP 接続を使用する機能を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-874">Users can also enable a feature that ensures that messages sent using channels created by different channel factories will use different underlying HTTP connections.</span></span> <span data-ttu-id="f2d3b-875">この機能を有効にするには、ユーザーが次の `appSetting` を `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-875">To enable this feature, users must set the following `appSetting` to `true`:</span></span>

            ```xml
            <appSettings>
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
            </appSettings>
            ```

- <span data-ttu-id="f2d3b-876">**Windows Workflow Foundation (WWF)**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-876">**Windows Workflow Foundation (WWF)**</span></span>

     <span data-ttu-id="f2d3b-877">順序不定の操作要求がタイムアウトする前に未処理の "非プロトコル" ブックマークが存在する場合に、ワークフロー サービスが要求を保持する秒数を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-877">You can now specify the number of seconds a workflow service will hold on to an out-of-order operation request when there is an outstanding "non-protocol" bookmark before timing out the request.</span></span> <span data-ttu-id="f2d3b-878">"非プロトコル" ブックマークとは、未処理の Receive アクティビティに関連付けられていないブックマークです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-878">A "non-protocol" bookmark is a bookmark that is not related to outstanding Receive activities.</span></span> <span data-ttu-id="f2d3b-879">一部のアクティビティはその実装内で非プロトコル ブックマークを作成するため、必ずしも非プロトコル ブックマークの存在が明らかにわかるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-879">Some activities create non-protocol bookmarks within their implementation, so it may not be obvious that a non-protocol bookmark exists.</span></span> <span data-ttu-id="f2d3b-880">例として State や Pick などがあります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-880">These include State and Pick.</span></span> <span data-ttu-id="f2d3b-881">ステート マシンを使用して実装されたワークフロー サービスや、Pick アクティビティを含むワークフロー サービスがある場合は、非プロトコル ブックマークが存在する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-881">So if you have a workflow service implemented with a state machine or containing a Pick activity, you will most likely have non-protocol bookmarks.</span></span> <span data-ttu-id="f2d3b-882">この間隔を指定するには、app.config ファイルの `appSettings` セクションに次のような行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-882">You specify the interval by adding a line like the following to the `appSettings` section of your app.config file:</span></span>

    ```xml
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
    ```

     <span data-ttu-id="f2d3b-883">既定値は 60 秒です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-883">The default value is 60 seconds.</span></span> <span data-ttu-id="f2d3b-884">`value` を 0 に設定すると、順序不定の要求はただちに拒否され、次のようなテキストを含むエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-884">If `value` is set to 0, out-of-order requests are immediately rejected with a fault with text that looks like this:</span></span>

    ```
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.
    ```

     <span data-ttu-id="f2d3b-885">これは、順序不定の操作メッセージを受信し、非プロトコル ブックマークが存在しない場合に受信するメッセージと同じです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-885">This is the same message that you receive if an out-of-order operation message is received and there are no non-protocol bookmarks.</span></span>

     <span data-ttu-id="f2d3b-886">`FilterResumeTimeoutInSeconds` 要素の値がゼロ以外で、非プロトコル ブックマークが存在し、タイムアウト間隔が終了した場合、その操作は失敗し、タイムアウト メッセージが発生します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-886">If the value of the `FilterResumeTimeoutInSeconds` element is non-zero, there are non-protocol bookmarks, and the timeout interval expires, the operation fails with a timeout message.</span></span>

- <span data-ttu-id="f2d3b-887">**トランザクション**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-887">**Transactions**</span></span>

     <span data-ttu-id="f2d3b-888"><xref:System.Transactions.TransactionException> から派生した例外がスローされる原因となったトランザクションに、分散トランザクション識別子を含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-888">You can now include the distributed transaction identifier for the transaction that has caused an exception derived from <xref:System.Transactions.TransactionException> to be thrown.</span></span> <span data-ttu-id="f2d3b-889">これを行うには、次のキーを app.config ファイルの `appSettings` セクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-889">You do this by adding the following key to the `appSettings` section of your app.config file:</span></span>

    ```xml
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>
    ```

     <span data-ttu-id="f2d3b-890">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-890">The default value is `false`.</span></span>

- <span data-ttu-id="f2d3b-891">**ネットワーク**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-891">**Networking**</span></span>

    - <span data-ttu-id="f2d3b-892">**ソケットの再利用**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-892">**Socket reuse**</span></span>

         <span data-ttu-id="f2d3b-893">Windows 10 には、送信 TCP 接続のローカル ポートを再利用してコンピューターのリソースを効率的に使用する新しいスケーラビリティの高いネットワーク アルゴリズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-893">Windows 10 includes a new high-scalability networking algorithm that makes better use of machine resources by reusing local ports for outbound TCP connections.</span></span> <span data-ttu-id="f2d3b-894">.NET Framework 4.6 では、この新しいアルゴリズムがサポートされ、.NET アプリで新しい動作を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-894">The .NET Framework 4.6 supports the new algorithm, enabling .NET apps to take advantage of the new behavior.</span></span> <span data-ttu-id="f2d3b-895">以前のバージョンの Windows では、人工的なコンカレント接続の制限 (通常は動的なポート範囲の既定のサイズである 16,384) があったため、負荷がかかったときにポートが使い尽くされ、サービスのスケーラビリティが制限されることがありました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-895">In previous versions of Windows, there was an artificial concurrent connection limit (typically 16,384, the default size of the dynamic port range), which could limit the scalability of a service by causing port exhaustion when under load.</span></span>

         <span data-ttu-id="f2d3b-896">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] では、ポートの再利用を有効にする次の 2 つの新しい API が追加され、コンカレント接続に対する 64K の制限が実質的になくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-896">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], two new APIs have been added to enable port reuse, which effectively removes the 64K limit on concurrent connections:</span></span>

        - <span data-ttu-id="f2d3b-897"><xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> 列挙型値。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-897">The <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> enumeration value.</span></span>

        - <span data-ttu-id="f2d3b-898"><xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-898">The <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> property.</span></span>

         <span data-ttu-id="f2d3b-899">既定では、`HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` レジストリ キーの `HWRPortReuseOnSocketBind` の値が 0x1 に設定されないかぎり、<xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> プロパティは `false` になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-899">By default, the <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> property is `false` unless the `HWRPortReuseOnSocketBind` value of the `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` registry key is set to 0x1.</span></span> <span data-ttu-id="f2d3b-900">HTTP 接続でのローカル ポートの再利用を有効にするには、<xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-900">To enable local port reuse on HTTP connections, set the <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="f2d3b-901">これにより、<xref:System.Net.Http.HttpClient> および <xref:System.Net.HttpWebRequest> からの外向きのすべての TCP ソケット接続で Windows 10 の新しいソケット オプション [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options) が使用されるようになるため、ローカル ポートの再利用が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-901">This causes all outgoing TCP socket connections from <xref:System.Net.Http.HttpClient> and <xref:System.Net.HttpWebRequest> to use a new Windows 10 socket option, [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options), that enables local port reuse.</span></span>

         <span data-ttu-id="f2d3b-902">ソケット専用のアプリケーションを作成する開発者は、<xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> などのメソッドを呼び出すときに <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> オプションを指定することにより、送信ソケットでバインド中にローカル ポートを再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-902">Developers writing a sockets-only application can specify the <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> option when calling a method such as <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> so that outbound sockets reuse local ports during binding.</span></span>

    - <span data-ttu-id="f2d3b-903">**国際ドメイン名と PunyCode のサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-903">**Support for international domain names and PunyCode**</span></span>

         <span data-ttu-id="f2d3b-904"><xref:System.Uri> クラスに新しいプロパティ <xref:System.Uri.IdnHost%2A> が追加され、国際ドメイン名と PunyCode のサポートが強化されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-904">A new property, <xref:System.Uri.IdnHost%2A>, has been added to the <xref:System.Uri> class to better support international domain names and PunyCode.</span></span>

- <span data-ttu-id="f2d3b-905">**Windows フォーム コントロールでのサイズ変更**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-905">**Resizing in Windows Forms controls.**</span></span>

     <span data-ttu-id="f2d3b-906">この機能が [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] にも拡張されました。<xref:System.Windows.Forms.DomainUpDown>、<xref:System.Windows.Forms.NumericUpDown>、<xref:System.Windows.Forms.DataGridViewComboBoxColumn>、<xref:System.Windows.Forms.DataGridViewColumn>、<xref:System.Windows.Forms.ToolStripSplitButton> 型、および <xref:System.Drawing.Design.UITypeEditor> を描画するときに使用する <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> プロパティで指定される四角形も含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-906">This feature has been expanded in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] to include the <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.ToolStripSplitButton> types and the rectangle specified by the <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> property used when drawing a <xref:System.Drawing.Design.UITypeEditor>.</span></span>

     <span data-ttu-id="f2d3b-907">これはオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-907">This is an opt-in feature.</span></span> <span data-ttu-id="f2d3b-908">この機能を有効にするには、アプリケーション構成 (app.config) ファイルで `EnableWindowsFormsHighDpiAutoResizing` 要素を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-908">To enable it, set the `EnableWindowsFormsHighDpiAutoResizing` element to `true` in the application configuration (app.config) file:</span></span>

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- <span data-ttu-id="f2d3b-909">**コード ページのエンコーディングのサポート**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-909">**Support for code page encodings**</span></span>

     [!INCLUDE[net_core](../../../includes/net-core-md.md)] <span data-ttu-id="f2d3b-910">は、本来 Unicode エンコードをサポートし、既定ではコード ページ エンコーディングに関するサポートは限定的です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-910">primarily supports the Unicode encodings and by default provides limited support for code page encodings.</span></span> <span data-ttu-id="f2d3b-911"><xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType> メソッドを使用してコード ページ エンコーディングを登録することで、.NET Framework では利用できるものの [!INCLUDE[net_core](../../../includes/net-core-md.md)] ではサポートされていないコード ページ エンコーディングのサポートを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-911">You can add support for code page encodings available in the .NET Framework but unsupported in [!INCLUDE[net_core](../../../includes/net-core-md.md)] by registering code page encodings with the <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f2d3b-912">詳細については、「<xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-912">For more information, see <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="f2d3b-913">**.NET ネイティブ**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-913">**.NET Native**</span></span>

     <span data-ttu-id="f2d3b-914">[!INCLUDE[net_core](../../../includes/net-core-md.md)] をターゲットとし、C# または Visual Basic で作成されている Windows 10 用の Windows アプリは、IL ではなくネイティブ コードにアプリをコンパイルする新しい技術を活用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-914">Windows apps for Windows 10 that target [!INCLUDE[net_core](../../../includes/net-core-md.md)] and are written in C# or Visual Basic can take advantage of a new technology that compiles apps to native code rather than IL.</span></span> <span data-ttu-id="f2d3b-915">これで、起動時間と実行時間がより速いアプリを生成できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-915">They produce apps characterized by faster startup and execution times.</span></span> <span data-ttu-id="f2d3b-916">詳しくは、「[.NET ネイティブによるアプリのコンパイル](../net-native/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-916">For more information, see [Compiling Apps with .NET Native](../net-native/index.md).</span></span> <span data-ttu-id="f2d3b-917">JIT コンパイルと NGEN による結果の違い、およびコードにおけるその影響の概要については、「[.NET ネイティブとコンパイル](../net-native/net-native-and-compilation.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-917">For an overview of .NET Native that examines how it differs from both JIT compilation and NGEN and what that means for your code, see [.NET Native and Compilation](../net-native/net-native-and-compilation.md).</span></span>

     <span data-ttu-id="f2d3b-918">ご利用のアプリは、Visual Studio 2015 以降でコンパイルするときに、既定でネイティブ コードにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-918">Your apps are compiled to native code by default when you compile them with Visual Studio 2015 or later.</span></span> <span data-ttu-id="f2d3b-919">詳しくは、「[.NET ネイティブの概要](../net-native/getting-started-with-net-native.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-919">For more information, see [Getting Started with .NET Native](../net-native/getting-started-with-net-native.md).</span></span>

     <span data-ttu-id="f2d3b-920">.NET ネイティブ アプリのデバッグをサポートするため、アンマネージ デバッグ APIに対して数多くの新しいインターフェイスと列挙型が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-920">To support debugging .NET Native apps, a number of new interfaces and enumerations have been added to the unmanaged debugging API.</span></span> <span data-ttu-id="f2d3b-921">詳しくは、「[デバッグ (アンマネージ API リファレンス)](../unmanaged-api/debugging/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-921">For more information, see the [Debugging (Unmanaged API Reference)](../unmanaged-api/debugging/index.md) topic.</span></span>

- <span data-ttu-id="f2d3b-922">**オープン ソースの .NET Framework パッケージ**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-922">**Open-source .NET Framework packages**</span></span>

     <span data-ttu-id="f2d3b-923">.NET Core のパッケージ (変更できないコレクションなど)、[SIMD API](https://go.microsoft.com/fwlink/?LinkID=518639)、およびネットワーク API (<xref:System.Net.Http> 名前空間に含まれるものなど) は、[GitHub](https://github.com/) でオープン ソース パッケージとして入手できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-923">.NET Core packages such as the immutable collections, [SIMD APIs](https://go.microsoft.com/fwlink/?LinkID=518639), and networking APIs such as those found in the <xref:System.Net.Http> namespace are now available as open source packages on [GitHub](https://github.com/).</span></span> <span data-ttu-id="f2d3b-924">このコードにアクセスするには、[GitHub で CoreFx](https://github.com/dotnet/corefx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-924">To access the code, see [CoreFx on GitHub](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="f2d3b-925">これらのパッケージの詳細、および投稿方法については、「[.NET Core とオープン ソース](../get-started/net-core-and-open-source.md)」および [GitHub の .NET ホーム ページ](https://github.com/dotnet/home)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-925">For more information and how to contribute to these packages, see [.NET Core and Open-Source](../get-started/net-core-and-open-source.md), [.NET Home Page on GitHub](https://github.com/dotnet/home).</span></span>

<a name="v452" />

## <a name="whats-new-in-the-net-framework-452"></a><span data-ttu-id="f2d3b-926">.NET Framework 4.5.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-926">What's new in the .NET Framework 4.5.2</span></span>

- <span data-ttu-id="f2d3b-927">**ASP.NET アプリ用の新しい API。**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-927">**New APIs for ASP.NET apps.**</span></span> <span data-ttu-id="f2d3b-928">新しい <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> メソッドと <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> メソッドにより、応答がクライアント アプリにフラッシュされる際の、応答ヘッダーと状態コードを確認および変更できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-928">The new <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> and <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> methods let you inspect and modify response headers and status code as the response is being flushed to the client app.</span></span> <span data-ttu-id="f2d3b-929"><xref:System.Web.HttpApplication.PreSendRequestHeaders> イベントや <xref:System.Web.HttpApplication.PreSendRequestContent> イベントの代わりに、より効率的で信頼性の高いこれらのメソッドの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-929">Consider using these methods instead of the <xref:System.Web.HttpApplication.PreSendRequestHeaders> and <xref:System.Web.HttpApplication.PreSendRequestContent> events; they are more efficient and reliable.</span></span>

     <span data-ttu-id="f2d3b-930"><xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> メソッドにより、小さなバックグラウンド作業項目をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-930">The <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> method lets you schedule small background work items.</span></span> <span data-ttu-id="f2d3b-931">ASP.NET はこれらの項目を追跡し、すべてのバックグラウンド作業項目が完了するまで IIS が突然ワーカー プロセスを終了しないようにします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-931">ASP.NET tracks these items and prevents IIS from abruptly terminating the worker process until all background work items have completed.</span></span> <span data-ttu-id="f2d3b-932">このメソッドは、ASP.NET マネージド アプリ ドメインの外部で呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-932">This method can't be called outside an ASP.NET managed app domain.</span></span>

     <span data-ttu-id="f2d3b-933">新しい <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> プロパティと <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> プロパティは、応答ヘッダーが書き込まれたかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-933">The new <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> and <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> properties return Boolean values that indicate whether the response headers have been written.</span></span> <span data-ttu-id="f2d3b-934">これらのプロパティを使用して、<xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (ヘッダーが書き込まれた場合に例外をスローする) などの API への呼び出しが成功することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-934">You can use these properties to make sure that calls to APIs such as <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (which throw exceptions if the headers have been written) will succeed.</span></span>

- <span data-ttu-id="f2d3b-935">**Windows フォーム コントロールでのサイズ変更**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-935">**Resizing in Windows Forms controls.**</span></span> <span data-ttu-id="f2d3b-936">この機能が拡張されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-936">This feature has been expanded.</span></span> <span data-ttu-id="f2d3b-937">これにより、システム DPI 設定を使用して、次の追加コントロールのコンポーネント (例: コンボ ボックスのドロップダウン矢印) をサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-937">You can now use the system DPI setting to resize components of the following additional controls (for example, the drop-down arrow in combo boxes):</span></span>

    - <xref:System.Windows.Forms.ComboBox>
    - <xref:System.Windows.Forms.ToolStripComboBox>
    - <xref:System.Windows.Forms.ToolStripMenuItem>
    - <xref:System.Windows.Forms.Cursor>
    - <xref:System.Windows.Forms.DataGridView>
    - <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

     <span data-ttu-id="f2d3b-938">これはオプトイン機能です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-938">This is an opt-in feature.</span></span> <span data-ttu-id="f2d3b-939">この機能を有効にするには、アプリケーション構成 (app.config) ファイルで `EnableWindowsFormsHighDpiAutoResizing` 要素を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-939">To enable it, set the `EnableWindowsFormsHighDpiAutoResizing` element to `true` in the application configuration (app.config) file:</span></span>

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- <span data-ttu-id="f2d3b-940">**新しいワークフロー機能。**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-940">**New workflow feature.**</span></span> <span data-ttu-id="f2d3b-941"><xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> メソッドを使用している (および、結果として <xref:System.Transactions.IPromotableSinglePhaseNotification> インターフェイスを実装している) リソース マネージャーは、新しい <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> メソッドを使用して、次の事柄を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-941">A resource manager that's using the <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> method (and therefore implementing the <xref:System.Transactions.IPromotableSinglePhaseNotification> interface) can use the new <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> method to request the following:</span></span>

    - <span data-ttu-id="f2d3b-942">トランザクションを Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションに昇格する。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-942">Promote the transaction to a Microsoft Distributed Transaction Coordinator (MSDTC) transaction.</span></span>

    - <span data-ttu-id="f2d3b-943"><xref:System.Transactions.IPromotableSinglePhaseNotification> を <xref:System.Transactions.ISinglePhaseNotification> (単一フェーズのコミットをサポートする永続的登録リスト) に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-943">Replace <xref:System.Transactions.IPromotableSinglePhaseNotification> with an <xref:System.Transactions.ISinglePhaseNotification>, which is a durable enlistment that supports single phase commits.</span></span>

     <span data-ttu-id="f2d3b-944">これは同じアプリ ドメイン内で実行でき、MSDTC とやり取りして昇格を実行するためにアンマネージ コードを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-944">This can be done within the same app domain, and doesn't require any extra unmanaged code to interact with MSDTC to perform the promotion.</span></span> <span data-ttu-id="f2d3b-945"><xref:System.Transactions?displayProperty=nameWithType> から昇格可能な登録リストにより実装された <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote` メソッドへの未処理の呼び出しがある場合のみ、この新しいメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-945">The new method can be called only when there's an outstanding call from <xref:System.Transactions?displayProperty=nameWithType> to the <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote` method that's implemented by the promotable enlistment.</span></span>

- <span data-ttu-id="f2d3b-946">**プロファイリングの機能強化。**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-946">**Profiling improvements.**</span></span> <span data-ttu-id="f2d3b-947">次の新しいアンマネージ プロファイリング API により、さらに信頼性の高いプロファイリングを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-947">The following new unmanaged profiling APIs provide more robust profiling:</span></span>

    - [<span data-ttu-id="f2d3b-948">COR_PRF_ASSEMBLY_REFERENCE_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="f2d3b-948">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
    - [<span data-ttu-id="f2d3b-949">COR_PRF_HIGH_MONITOR 列挙型</span><span class="sxs-lookup"><span data-stu-id="f2d3b-949">COR_PRF_HIGH_MONITOR Enumeration</span></span>](../unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)
    - [<span data-ttu-id="f2d3b-950">GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-950">GetAssemblyReferences Method</span></span>](../unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
    - [<span data-ttu-id="f2d3b-951">GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-951">GetEventMask2 Method</span></span>](../unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
    - [<span data-ttu-id="f2d3b-952">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-952">SetEventMask2 Method</span></span>](../unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
    - [<span data-ttu-id="f2d3b-953">AddAssemblyReference メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-953">AddAssemblyReference Method</span></span>](../unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

     <span data-ttu-id="f2d3b-954">以前の `ICorProfiler` の実装は、依存アセンブリの遅延読み込みをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-954">Previous `ICorProfiler` implementations supported lazy loading of dependent assemblies.</span></span> <span data-ttu-id="f2d3b-955">新しいプロファイリング API では、プロファイラーにより挿入される依存アセンブリを、アプリの完全な初期化後に読み込むのではなく、すぐに読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-955">The new profiling APIs require dependent assemblies that are injected by the profiler to be loadable immediately, instead of being loaded after the app is fully initialized.</span></span> <span data-ttu-id="f2d3b-956">この変更は、既存の `ICorProfiler` API のユーザーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-956">This change doesn't affect users of the existing `ICorProfiler` APIs.</span></span>

- <span data-ttu-id="f2d3b-957">**デバッグの機能強化。**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-957">**Debugging improvements.**</span></span> <span data-ttu-id="f2d3b-958">次の新しいアンマネージド デバッグ API により、プロファイラーとの統合性が向上しました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-958">The following new unmanaged debugging APIs provide better integration with a profiler.</span></span> <span data-ttu-id="f2d3b-959">これにより、ダンプのデバッグ時にコンパイラ ReJIT 要求により作成されたローカル変数やコードだけでなく、プロファイラーにより挿入されたメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-959">You can now access metadata inserted by the profiler as well as local variables and code produced by compiler ReJIT requests when dump debugging.</span></span>

    - [<span data-ttu-id="f2d3b-960">SetWriteableMetadataUpdateMode メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-960">SetWriteableMetadataUpdateMode Method</span></span>](../unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
    - [<span data-ttu-id="f2d3b-961">EnumerateLocalVariablesEx メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-961">EnumerateLocalVariablesEx Method</span></span>](../unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)
    - [<span data-ttu-id="f2d3b-962">GetLocalVariableEx メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-962">GetLocalVariableEx Method</span></span>](../unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)
    - [<span data-ttu-id="f2d3b-963">GetCodeEx メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-963">GetCodeEx Method</span></span>](../unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)
    - [<span data-ttu-id="f2d3b-964">GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-964">GetActiveReJitRequestILCode Method</span></span>](../unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)
    - [<span data-ttu-id="f2d3b-965">GetInstrumentedILMap メソッド</span><span class="sxs-lookup"><span data-stu-id="f2d3b-965">GetInstrumentedILMap Method</span></span>](../unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- <span data-ttu-id="f2d3b-966">**イベント トレーシングの変更。**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-966">**Event tracing changes.**</span></span> <span data-ttu-id="f2d3b-967">.NET Framework 4.5.2 では、より大きなサーフェイス領域において、アウトプロセスの Windows イベント トレーシング (ETW) に基づくアクティビティ トレーシングができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-967">The .NET Framework 4.5.2 enables out-of-process, Event Tracing for Windows (ETW)-based activity tracing for a larger surface area.</span></span> <span data-ttu-id="f2d3b-968">これにより、アドバンスト パワー マネージメント (APM) ベンダーは、スレッドを越えた個々の要求とアクティビティのコストを正確に追跡する軽量ツールを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-968">This enables Advanced Power Management (APM) vendors to provide lightweight tools that accurately track the costs of individual requests and activities that cross threads.</span></span>  <span data-ttu-id="f2d3b-969">これらのイベントは、ETW コントローラーで有効にされた場合にのみ発生します。したがって、変更は以前に記述された ETW コードや ETW が無効な状態で実行されるコードには影響しません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-969">These events are raised only when ETW controllers enable them; therefore, the changes don't affect previously written ETW code or code that runs with ETW disabled.</span></span>

- <span data-ttu-id="f2d3b-970">**トランザクションの昇格と永続参加リストへの変換**</span><span class="sxs-lookup"><span data-stu-id="f2d3b-970">**Promoting a transaction and converting it to a durable enlistment**</span></span>

     <span data-ttu-id="f2d3b-971"><xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> は、.NET Framework 4.5.2 および 4.6 に追加された新しい API です。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-971"><xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> is a new API added to the .NET Framework 4.5.2 and 4.6:</span></span>

    ```csharp
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                              IPromotableSinglePhaseNotification promotableNotification,
                                              ISinglePhaseNotification enlistmentNotification,
                                              EnlistmentOptions enlistmentOptions)
    ```

     <span data-ttu-id="f2d3b-972">このメソッドは、以前に <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> メソッドへの応答として <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> によって作成された参加リストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-972">The method may be used by an enlistment that was previously created by <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> in response to the <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f2d3b-973">これは、`System.Transactions` に対して、トランザクションを MSDTC トランザクションに昇格させ、昇格可能参加リストを永続参加リストに "変換" するように要求します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-973">It asks `System.Transactions` to promote the transaction to an MSDTC transaction and to "convert" the promotable enlistment to a durable enlistment.</span></span> <span data-ttu-id="f2d3b-974">このメソッドが正常に完了すると、<xref:System.Transactions.IPromotableSinglePhaseNotification> インターフェイスが `System.Transactions` から参照されなくなり、その後の通知は指定された <xref:System.Transactions.ISinglePhaseNotification> インターフェイスに到着します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-974">After this method completes successfully, the <xref:System.Transactions.IPromotableSinglePhaseNotification> interface will no longer be referenced by `System.Transactions`, and any future notifications will arrive on the provided <xref:System.Transactions.ISinglePhaseNotification> interface.</span></span> <span data-ttu-id="f2d3b-975">問題の参加リストは、永続参加リストとして機能し、トランザクションのログ記録と復旧をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-975">The enlistment in question must act as a durable enlistment, supporting transaction logging and recovery.</span></span> <span data-ttu-id="f2d3b-976">詳細については、<xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-976">Refer to <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> for details.</span></span> <span data-ttu-id="f2d3b-977">さらに、この参加リストは <xref:System.Transactions.ISinglePhaseNotification> もサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-977">In addition, the enlistment must support <xref:System.Transactions.ISinglePhaseNotification>.</span></span>  <span data-ttu-id="f2d3b-978">このメソッドは、<xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> の呼び出しの処理中に*のみ*呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-978">This method can *only* be called while processing an <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> call.</span></span> <span data-ttu-id="f2d3b-979">そうでない場合は、<xref:System.Transactions.TransactionException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-979">If that is not the case, a <xref:System.Transactions.TransactionException> exception is thrown.</span></span>

<a name="v451" />

## <a name="whats-new-in-the-net-framework-451"></a><span data-ttu-id="f2d3b-980">.NET Framework 4.5.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-980">What's new in the .NET Framework 4.5.1</span></span>

<span data-ttu-id="f2d3b-981">**2014 年 4 月の更新**:</span><span class="sxs-lookup"><span data-stu-id="f2d3b-981">**April 2014 updates**:</span></span>

- <span data-ttu-id="f2d3b-982">[Visual Studio 2013 更新プログラム 2](https://go.microsoft.com/fwlink/p/?LinkId=393658) には、次のシナリオをサポートするポータブル クラス ライブラリ テンプレートの更新が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-982">[Visual Studio 2013 Update 2](https://go.microsoft.com/fwlink/p/?LinkId=393658) includes updates to the Portable Class Library templates to support these scenarios:</span></span>

    - <span data-ttu-id="f2d3b-983">Windows 8.1、Windows Phone 8.1、および Windows Phone Silverlight 8.1 を対象とするポータブル ライブラリで Windows ランタイム API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-983">You can use Windows Runtime APIs in portable libraries that target Windows 8.1, Windows Phone 8.1, and Windows Phone Silverlight 8.1.</span></span>

    - <span data-ttu-id="f2d3b-984">Windows 8.1 または Windows Phone 8.1 を対象とする場合、ポータブル ライブラリに XAML (Windows.UI.XAML 型) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-984">You can include XAML (Windows.UI.XAML types) in portable libraries when you target Windows 8.1 or Windows Phone 8.1.</span></span> <span data-ttu-id="f2d3b-985">次の XAML テンプレートがサポートされています: 空白のページ、リソース ディクショナリ、テンプレート コントロール、およびユーザー コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-985">The following XAML templates are supported:  Blank Page, Resource Dictionary, Templated Control, and User Control.</span></span>

    - <span data-ttu-id="f2d3b-986">Windows 8.1 および Windows Phone 8.1 を対象とするストア アプリで使用するためにポータブル Windows ラインタイム コンポーネント (.winmd ファイル) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-986">You can create a portable Windows Runtime component (.winmd file) for use in Store apps that target Windows 8.1 and Windows Phone 8.1.</span></span>

    - <span data-ttu-id="f2d3b-987">ポータブル クラス ライブラリのような Windows ストアまたは Windows Phone ストア クラス ライブラリを再ターゲットできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-987">You can retarget a Windows Store or Windows Phone Store class library like a Portable Class Library.</span></span>

     <span data-ttu-id="f2d3b-988">これらの変更の詳細については、[ポータブル クラス ライブラリ](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-988">For more information about these changes, see [Portable Class Library](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).</span></span>

- <span data-ttu-id="f2d3b-989">.NET Framework のコンテンツ セットには、Windows アプリをビルドして配置するためのプリコンパイル テクノロジである [!INCLUDE[net_native](../../../includes/net-native-md.md)] のドキュメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-989">The .NET Framework content set now includes documentation for [!INCLUDE[net_native](../../../includes/net-native-md.md)], which is a precompilation technology for building and deploying Windows apps.</span></span> [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="f2d3b-990">は、中間言語 (IL) ではなくネイティブ コードへアプリを直接コンパイルすることにより、パフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-990">compiles your apps directly to native code, rather than to intermediate language (IL), for better performance.</span></span> <span data-ttu-id="f2d3b-991">詳しくは、「[.NET ネイティブによるアプリのコンパイル](../net-native/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-991">For details, see [Compiling Apps with .NET Native](../net-native/index.md).</span></span>

- <span data-ttu-id="f2d3b-992">[.NET Framework Reference Source](https://referencesource.microsoft.com/) で、新しい参照エクスペリエンスと強化された機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-992">The [.NET Framework Reference Source](https://referencesource.microsoft.com/) provides a new browsing experience and enhanced functionality.</span></span> <span data-ttu-id="f2d3b-993">これにより、.NET Frameworkのソース コードをオンラインで参照したり、[リファレンスをダウンロード](https://referencesource.microsoft.com/download.html)してオフラインで表示したりできます。さらに、デバッグ中にソース (パッチや更新を含む) をステップ実行できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-993">You can now browse through the .NET Framework source code online, [download the reference](https://referencesource.microsoft.com/download.html) for offline viewing, and step through the sources (including patches and updates) during debugging.</span></span> <span data-ttu-id="f2d3b-994">詳細については、ブログ記事「[A new look for .NET Reference Source (.NET Reference Source の新しい外観)](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-994">For more information, see the blog entry [A new look for .NET Reference Source](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/).</span></span>

<span data-ttu-id="f2d3b-995">.NET Framework 4.5.1 のコア機能の新機能と機能強化には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-995">Core new features and enhancements in the .NET Framework 4.5.1 include:</span></span>

- <span data-ttu-id="f2d3b-996">アセンブリの自動バインディング リダイレクト。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-996">Automatic binding redirection for assemblies.</span></span> <span data-ttu-id="f2d3b-997">Visual Studio 2013 以降では、アプリまたはそのコンポーネントが同じアセンブリの複数バージョンを参照している場合、[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] を対象とするアプリのコンパイル時に、バインディング リダイレクトをアプリ構成ファイルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-997">Starting with Visual Studio 2013, when you compile an app that targets the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be added to the app configuration file if your app or its components reference multiple versions of the same assembly.</span></span> <span data-ttu-id="f2d3b-998">また、.NET Framework の以前のバージョンを対象とするプロジェクトで、この機能を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-998">You can also enable this feature for projects that target older versions of the .NET Framework.</span></span> <span data-ttu-id="f2d3b-999">詳細については、「[方法 :自動バインディング リダイレクトを有効/無効にする](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-999">For more information, see [How to: Enable and Disable Automatic Binding Redirection](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).</span></span>

- <span data-ttu-id="f2d3b-1000">開発者がサーバーおよびクラウド アプリケーションのパフォーマンスを向上するために役立つ診断情報を収集する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1000">Ability to collect diagnostics information to help developers improve the performance of server and cloud applications.</span></span> <span data-ttu-id="f2d3b-1001">詳細については、<xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> クラスの <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> メソッドと <xref:System.Diagnostics.Tracing.EventSource> メソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1001">For more information, see the <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> and <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> methods in the <xref:System.Diagnostics.Tracing.EventSource> class.</span></span>

- <span data-ttu-id="f2d3b-1002">ガベージ コレクション中に大きなオブジェクト ヒープ (LOH) を圧縮する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1002">Ability to explicitly compact the large object heap (LOH) during garbage collection.</span></span> <span data-ttu-id="f2d3b-1003">詳細については、<xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1003">For more information, see the <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="f2d3b-1004">その他のパフォーマンス向上 (ASP.NET アプリの中断、マルチコア JIT の改良、.NET Framework 更新後のアプリ起動時間の短縮など)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1004">Additional performance improvements such as ASP.NET app suspension, multi-core JIT improvements, and faster app startup after a .NET Framework update.</span></span> <span data-ttu-id="f2d3b-1005">詳細については、ブログ記事「[.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/)」(.NET Framework 4.5.1 についてのお知らせ) および「[ASP.NET app suspend](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/)」 (ASP.NET アプリケーションの中断) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1005">For details, see the [.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/) and the [ASP.NET app suspend](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/) blog post.</span></span>

<span data-ttu-id="f2d3b-1006">Windows フォームの機能強化には次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1006">Improvements to Windows Forms include:</span></span>

- <span data-ttu-id="f2d3b-1007">Windows フォーム コントロールでのサイズ変更。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1007">Resizing in Windows Forms controls.</span></span> <span data-ttu-id="f2d3b-1008">アプリのアプリケーション構成ファイル (app.config) 内のエントリで有効にすることにより、システム DIP 設定を使用してコントロールのコンポーネント (例: プロパティ グリッドに表示されるアイコン) をサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1008">You can use the system DPI setting to resize components of controls (for example, the icons that appear in a property grid) by opting in with an entry in the application configuration file (app.config) for your app.</span></span> <span data-ttu-id="f2d3b-1009">現在、この機能は次の Windows フォーム コントロールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1009">This feature is currently supported in the following Windows Forms controls:</span></span>

    - <xref:System.Windows.Forms.PropertyGrid>
    - <xref:System.Windows.Forms.TreeView>
    - <span data-ttu-id="f2d3b-1010"><xref:System.Windows.Forms.DataGridView> の一部 (サポートされている追加コントロールについては、「[4.5.2 の新機能](#v452)」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1010">Some aspects of the <xref:System.Windows.Forms.DataGridView> (see [new features in 4.5.2](#v452) for additional controls supported)</span></span>

     <span data-ttu-id="f2d3b-1011">この機能を有効にするには、構成ファイル (app.config) に新しい \<appSettings> 要素を追加し、`EnableWindowsFormsHighDpiAutoResizing` 要素を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1011">To enable this feature, add a new \<appSettings> element to the configuration file (app.config) and set the `EnableWindowsFormsHighDpiAutoResizing` element to `true`:</span></span>

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

<span data-ttu-id="f2d3b-1012">Visual Studio 2013 で .NET Framework アプリをデバッグするときの改善点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1012">Improvements when debugging your .NET Framework apps in Visual Studio 2013 include:</span></span>

- <span data-ttu-id="f2d3b-1013">Visual Studio デバッガーの戻り値。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1013">Return values in the Visual Studio debugger.</span></span> <span data-ttu-id="f2d3b-1014">Visual Studio 2013 でマネージド アプリをデバッグする場合、メソッドの戻り値の型と値が [自動変数] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1014">When you debug a managed app in Visual Studio 2013, the Autos window displays return types and values for methods.</span></span> <span data-ttu-id="f2d3b-1015">デスクトップ アプリ、Windows ストア アプリ、Windows Phone アプリについて、この情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1015">This information is available for desktop, Windows Store, and Windows Phone apps.</span></span> <span data-ttu-id="f2d3b-1016">詳細については、「[メソッド呼び出しの戻り値の調査](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1016">For more information, see [Examine return values of method calls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120)).</span></span>

- <span data-ttu-id="f2d3b-1017">64 ビット アプリのエディット コンティニュ。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1017">Edit and Continue for 64-bit apps.</span></span> <span data-ttu-id="f2d3b-1018">Visual Studio 2013 では、デスクトップ、Windows ストア、Windows Phone 用の 64 ビット マネージド アプリについて、エディット コンティニュ機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1018">Visual Studio 2013 supports the Edit and Continue feature for 64-bit managed apps for desktop, Windows Store, and Windows Phone.</span></span> <span data-ttu-id="f2d3b-1019">既存の制限は、32 ビット アプリと 64 ビット アプリの両方でまだ有効です (「[Supported Code Changes (C#)](/visualstudio/debugger/supported-code-changes-csharp)」(サポートされているコードの変更 (C#)) の記事の最後のセクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1019">The existing limitations remain in effect for both 32-bit and 64-bit apps (see the last section of the [Supported Code Changes (C#)](/visualstudio/debugger/supported-code-changes-csharp) article).</span></span>

- <span data-ttu-id="f2d3b-1020">非同期対応のデバッグ。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1020">Async-aware debugging.</span></span> <span data-ttu-id="f2d3b-1021">Visual Studio 2013 で非同期アプリを簡単にデバッグするために、呼び出し履歴には、非同期プログラミングをサポートするためにコンパイラに用意されているインフラストラクチャ コード、および論理上の親フレーム内のチェーンが表示されません。これにより、論理的なプログラムの実行をよりわかりやすく行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1021">To make it easier to debug asynchronous apps in Visual Studio 2013, the call stack hides the infrastructure code provided by compilers to support asynchronous programming, and also chains in logical parent frames so you can follow logical program execution more clearly.</span></span> <span data-ttu-id="f2d3b-1022">[タスク] ウィンドウが [並列タスク] ウィンドウに代わって使用され、特定のブレークポイントに関連するタスクが表示されます。また、現在アクティブなタスクやアプリでスケジュールされているタスクなども表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1022">A Tasks window replaces the Parallel Tasks window and displays tasks that relate to a particular breakpoint, and also displays any other tasks that are currently active or scheduled in the app.</span></span> <span data-ttu-id="f2d3b-1023">この機能については、「[.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/)」(.NET Framework 4.5.1 についてのお知らせ) の「Async-aware debugging」(非同期対応のデバッグ) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1023">You can read about this feature in the "Async-aware debugging" section of the [.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).</span></span>

- <span data-ttu-id="f2d3b-1024">Windows ランタイム コンポーネント向けのより適切な例外処理のサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1024">Better exception support for Windows Runtime components.</span></span> <span data-ttu-id="f2d3b-1025">[!INCLUDE[win81](../../../includes/win81-md.md)] では、言語の種類に関係なく、Windows ストア アプリから発生する例外には、例外を発生させたエラーに関する情報が保持されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1025">In [!INCLUDE[win81](../../../includes/win81-md.md)], exceptions that arise from Windows Store apps preserve information about the error that caused the exception, even across language boundaries.</span></span> <span data-ttu-id="f2d3b-1026">この機能については、「[.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/)」(.NET Framework 4.5.1 についてのお知らせ) の「Windows Store app development」(Windows ストア アプリ開発) のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1026">You can read about this feature in the "Windows Store app development" section of the [.NET Framework 4.5.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).</span></span>

<span data-ttu-id="f2d3b-1027">Visual Studio 2013 以降では、[Mpgo.exe (マネージド プロファイル ガイド付き最適化ツール)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) を使って、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリとデスクトップ アプリを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1027">Starting with Visual Studio 2013, you can use the [Managed Profile Guided Optimization Tool (Mpgo.exe)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) to optimize [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps as well as desktop apps.</span></span>

<span data-ttu-id="f2d3b-1028">ASP.NET 4.5.1 の新機能については、「[ASP.NET and Web Tools for Visual Studio 2013 のリリース ノート](/aspnet/visual-studio/overview/2013/release-notes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1028">For new features in ASP.NET 4.5.1, see [ASP.NET and Web Tools for Visual Studio 2013 Release Notes](/aspnet/visual-studio/overview/2013/release-notes).</span></span>

<a name="v45" />

## <a name="whats-new-in-the-net-framework-45"></a><span data-ttu-id="f2d3b-1029">.NET Framework 4.5 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1029">What's new in the .NET Framework 4.5</span></span>

### <a name="core-new-features-and-improvements"></a><span data-ttu-id="f2d3b-1030">コア機能の新機能と機能強化</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1030">Core new features and improvements</span></span>

- <span data-ttu-id="f2d3b-1031">配置時に .NET Framework 4 アプリケーションを検出して終了することにより、システムの再起動を減らす機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1031">Ability to reduce system restarts by detecting and closing .NET Framework 4 applications during deployment.</span></span> <span data-ttu-id="f2d3b-1032">「[.NET Framework 4.5 のインストール中のシステム再起動の削減](../deployment/reducing-system-restarts.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1032">See [Reducing System Restarts During .NET Framework 4.5 Installations](../deployment/reducing-system-restarts.md).</span></span>

- <span data-ttu-id="f2d3b-1033">64 ビット プラットフォームでの 2 ギガバイト (GB) を超える配列のサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1033">Support for arrays that are larger than 2 gigabytes (GB) on 64-bit platforms.</span></span> <span data-ttu-id="f2d3b-1034">この機能は、アプリケーション構成ファイルで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1034">This feature can be enabled in the application configuration file.</span></span> <span data-ttu-id="f2d3b-1035">「[\<gcAllowVeryLargeObjects> 要素](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)」も参照してください。オブジェクト サイズと配列サイズに関する他の制限も記載されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1035">See the [\<gcAllowVeryLargeObjects> element](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), which also lists other restrictions on object size and array size.</span></span>

- <span data-ttu-id="f2d3b-1036">サーバーのガベージ コレクションをバックグラウンドで行うことにより、パフォーマンスを改善します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1036">Better performance through background garbage collection for servers.</span></span> <span data-ttu-id="f2d3b-1037">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] でサーバーのガベージ コレクションを使用すると、バックグラウンド ガベージ コレクションが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1037">When you use server garbage collection in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], background garbage collection is automatically enabled.</span></span> <span data-ttu-id="f2d3b-1038">「[Fundamentals of Garbage Collection](../../standard/garbage-collection/fundamentals.md)」(ガベージ コレクションの基礎) トピックの「バックグラウンド サーバー ガベージ コレクション」というセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1038">See the Background Server Garbage Collection section of the [Fundamentals of Garbage Collection](../../standard/garbage-collection/fundamentals.md) topic.</span></span>

- <span data-ttu-id="f2d3b-1039">マルチコア プロセッサでオプションで使用できるバックグラウンドの Just-in-time (JIT) コンパイルを使用すると、アプリケーションのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1039">Background just-in-time (JIT) compilation, which is optionally available on multi-core processors to improve application performance.</span></span> <span data-ttu-id="f2d3b-1040">「<xref:System.Runtime.ProfileOptimization>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1040">See <xref:System.Runtime.ProfileOptimization>.</span></span>

- <span data-ttu-id="f2d3b-1041">正規表現エンジンがタイムアウトする前に、正規表現の解決を試みる時間に制限を設ける機能。<xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType> プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1041">Ability to limit how long the regular expression engine will attempt to resolve a regular expression before it times out. See the <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType> property.</span></span>

- <span data-ttu-id="f2d3b-1042">アプリケーション ドメインの既定のカルチャを定義する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1042">Ability to define the default culture for an application domain.</span></span> <span data-ttu-id="f2d3b-1043">詳細については、<xref:System.Globalization.CultureInfo> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1043">See the <xref:System.Globalization.CultureInfo> class.</span></span>

- <span data-ttu-id="f2d3b-1044">Unicode UTF-16 エンコードのコンソール サポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1044">Console support for Unicode (UTF-16) encoding.</span></span> <span data-ttu-id="f2d3b-1045">詳細については、<xref:System.Console> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1045">See the <xref:System.Console> class.</span></span>

- <span data-ttu-id="f2d3b-1046">カルチャに従った文字列の順序のバージョン指定と比較データのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1046">Support for versioning of cultural string ordering and comparison data.</span></span> <span data-ttu-id="f2d3b-1047">詳細については、<xref:System.Globalization.SortVersion> クラスのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1047">See the <xref:System.Globalization.SortVersion> class.</span></span>

- <span data-ttu-id="f2d3b-1048">リソースを取得するときのパフォーマンスを改善します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1048">Better performance when retrieving resources.</span></span> <span data-ttu-id="f2d3b-1049">「[リソースのパッケージ化と配置](../resources/packaging-and-deploying-resources-in-desktop-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1049">See [Packaging and Deploying Resources](../resources/packaging-and-deploying-resources-in-desktop-apps.md).</span></span>

- <span data-ttu-id="f2d3b-1050">Zip 圧縮の機能強化により、圧縮ファイルのサイズが小さくなりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1050">Zip compression improvements to reduce the size of a compressed file.</span></span> <span data-ttu-id="f2d3b-1051"><xref:System.IO.Compression?displayProperty=nameWithType> 名前空間を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1051">See the <xref:System.IO.Compression?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="f2d3b-1052"><xref:System.Reflection.Context.CustomReflectionContext> クラスを使用して、既定のリフレクションの動作をオーバーライドするリフレクション コンテキストをカスタマイズできる機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1052">Ability to customize a reflection context to override default reflection behavior through the <xref:System.Reflection.Context.CustomReflectionContext> class.</span></span>

- <span data-ttu-id="f2d3b-1053"><xref:System.Globalization.IdnMapping?displayProperty=nameWithType> クラスを [!INCLUDE[win8](../../../includes/win8-md.md)] で使用した場合の IDNA (Internationalized Domain Names in Applications) 規格の 2008 バージョンのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1053">Support for the 2008 version of the Internationalized Domain Names in Applications (IDNA) standard when the <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> class is used  on [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span>

- <span data-ttu-id="f2d3b-1054">オペレーティング システムへの文字列比較の処理代行。 .NET Framework を [!INCLUDE[win8](../../../includes/win8-md.md)] で使用したときに、Unicode 6.0 が実装されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1054">Delegation of string comparison to the operating system, which implements Unicode 6.0, when the .NET Framework is used on [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span> <span data-ttu-id="f2d3b-1055">他のプラットフォームで実行されている場合、.NET Framework には、Unicode 5.x. を実装する独自の文字列比較データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1055">When running on other platforms, the .NET Framework includes its own string comparison data, which implements Unicode 5.x.</span></span> <span data-ttu-id="f2d3b-1056"><xref:System.String> クラスおよび <xref:System.Globalization.SortVersion> クラスの「コメント」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1056">See the <xref:System.String> class and the Remarks section of the <xref:System.Globalization.SortVersion> class.</span></span>

- <span data-ttu-id="f2d3b-1057">アプリケーション ドメインごとに文字列のハッシュ コードを計算する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1057">Ability to compute the hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="f2d3b-1058">「[\<UseRandomizedStringHashAlgorithm> 要素](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1058">See [\<UseRandomizedStringHashAlgorithm> Element](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).</span></span>

- <span data-ttu-id="f2d3b-1059"><xref:System.Type> クラスと <xref:System.Reflection.TypeInfo> クラスで、タイプ リフレクションのサポートが分割されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1059">Type reflection support split between <xref:System.Type> and <xref:System.Reflection.TypeInfo> classes.</span></span> <span data-ttu-id="f2d3b-1060">「[Reflection in the .NET Framework for Windows Store Apps](../reflection-and-codedom/reflection-for-windows-store-apps.md)」(Windows ストア アプリのための .NET Framework のリフレクション) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1060">See [Reflection in the .NET Framework for Windows Store Apps](../reflection-and-codedom/reflection-for-windows-store-apps.md).</span></span>

### <a name="managed-extensibility-framework-mef"></a><span data-ttu-id="f2d3b-1061">MEF (Managed Extensibility Framework)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1061">Managed Extensibility Framework (MEF)</span></span>

<span data-ttu-id="f2d3b-1062">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、MEF (Managed Extensibility Framework) に次の新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1062">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the Managed Extensibility Framework (MEF) provides the following new features:</span></span>

- <span data-ttu-id="f2d3b-1063">ジェネリック型のサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1063">Support for generic types.</span></span>

- <span data-ttu-id="f2d3b-1064">属性ではなく命名規則に基づいてパーツを作成できるようにする、規則ベースのプログラミング モデル。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1064">Convention-based programming model that enables you to create parts based on naming conventions rather than attributes.</span></span>

- <span data-ttu-id="f2d3b-1065">複数のスコープ。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1065">Multiple scopes.</span></span>

- <span data-ttu-id="f2d3b-1066">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリを作成するときに使用できる MEF のサブセット。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1066">A subset of MEF that you can use when you create [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="f2d3b-1067">このサブセットは、[ダウンロード可能パッケージ](https://go.microsoft.com/fwlink/?LinkId=256238)として NuGet ギャラリーから入手できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1067">This subset is available as a [downloadable package](https://go.microsoft.com/fwlink/?LinkId=256238) from the NuGet Gallery.</span></span> <span data-ttu-id="f2d3b-1068">パッケージをインストールするには、Visual Studio でプロジェクトを開き、**[プロジェクト]** メニューの **[NuGet パッケージの管理]** をクリックし、`Microsoft.Composition` パッケージをオンラインで検索します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1068">To install the package, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the `Microsoft.Composition` package.</span></span>

<span data-ttu-id="f2d3b-1069">詳しくは、「[Managed Extensibility Framework (MEF)](../mef/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1069">For more information, see [Managed Extensibility Framework (MEF)](../mef/index.md).</span></span>

### <a name="asynchronous-file-operations"></a><span data-ttu-id="f2d3b-1070">非同期のファイル操作</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1070">Asynchronous file operations</span></span>

<span data-ttu-id="f2d3b-1071">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]では、新しい非同期機能が C# および Visual Basic 言語に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1071">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], new asynchronous features were added to the C# and Visual Basic languages.</span></span> <span data-ttu-id="f2d3b-1072">これらの機能は、非同期操作を実行するためのタスク ベースのモデルを追加します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1072">These features add a task-based model for performing asynchronous operations.</span></span> <span data-ttu-id="f2d3b-1073">この新しいモデルを使用するには、I/O クラスで非同期メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1073">To use this new model, use the asynchronous methods in the I/O classes.</span></span> <span data-ttu-id="f2d3b-1074">「[非同期ファイル I/O](../../standard/io/asynchronous-file-i-o.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1074">See [Asynchronous File I/O](../../standard/io/asynchronous-file-i-o.md).</span></span>

<a name="tools" />

### <a name="tools"></a><span data-ttu-id="f2d3b-1075">ツール</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1075">Tools</span></span>

<span data-ttu-id="f2d3b-1076">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、リソース ファイル ジェネレーター (Resgen.exe) を使用すると、.NET Framework アセンブリに埋め込まれた .resources ファイルから [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリ用の .resw ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1076">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Resource File Generator (Resgen.exe) enables you to create a .resw file for use in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps from a .resources file embedded in a .NET Framework assembly.</span></span> <span data-ttu-id="f2d3b-1077">詳しくは、「[Resgen.exe (リソース ファイル ジェネレーター)](../tools/resgen-exe-resource-file-generator.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1077">For more information, see [Resgen.exe (Resource File Generator)](../tools/resgen-exe-resource-file-generator.md).</span></span>

<span data-ttu-id="f2d3b-1078">マネージド プロファイル ガイド付き最適化ツール (Mpgo.exe) を使用すると、ネイティブ イメージ アセンブリを最適化することによって、アプリケーションの起動時間、メモリの使用率 (ワーキング セットのサイズ)、およびスループットを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1078">Managed Profile Guided Optimization (Mpgo.exe) enables you to improve application startup time, memory utilization (working set size), and throughput by optimizing native image assemblies.</span></span> <span data-ttu-id="f2d3b-1079">このコマンド ライン ツールは、ネイティブ イメージ アプリケーション アセンブリ用のプロファイル データを生成します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1079">The command-line tool generates profile data for native image application assemblies.</span></span> <span data-ttu-id="f2d3b-1080">「[Mpgo.exe (マネージド プロファイル ガイド付き最適化ツール)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1080">See [Mpgo.exe (Managed Profile Guided Optimization Tool)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md).</span></span> <span data-ttu-id="f2d3b-1081">Visual Studio 2013 以降では、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリおよびデスクトップ アプリを最適化するために、Mpgo.exe を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1081">Starting with Visual Studio 2013, you can use Mpgo.exe to optimize [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps as well as desktop apps.</span></span>

<a name="parallel" />

### <a name="parallel-computing"></a><span data-ttu-id="f2d3b-1082">並列コンピューティング</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1082">Parallel computing</span></span>

<span data-ttu-id="f2d3b-1083">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、並列計算用にいくつかの新機能と機能強化が提供されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1083">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] provides several new features and improvements for parallel computing.</span></span> <span data-ttu-id="f2d3b-1084">パフォーマンスの向上、コントロールの強化、非同期プログラミングのサポートの改善、新しいデータフロー ライブラリ、並列デバッグとパフォーマンス分析のためのサポートの強化などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1084">These include improved performance, increased control, improved support for asynchronous programming, a new dataflow library, and improved support for parallel debugging and performance analysis.</span></span> <span data-ttu-id="f2d3b-1085">ブログ「Parallel Programming with .NET」(.NET での並列プログラミング) の記事「[What’s New for Parallelism in .NET 4.5](https://go.microsoft.com/fwlink/?LinkId=235061)」(.NET 4.5 での並列処理の新機能) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1085">See the entry [What’s New for Parallelism in .NET 4.5](https://go.microsoft.com/fwlink/?LinkId=235061) in the Parallel Programming with .NET blog.</span></span>

<a name="web" />

### <a name="web"></a><span data-ttu-id="f2d3b-1086">Web</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1086">Web</span></span>

<span data-ttu-id="f2d3b-1087">ASP.NET 4.5 および 4.5.1 では、Web フォーム モデルのバインディング、WebSocket のサポート、非同期ハンドラー、パフォーマンスの向上などの多くの機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1087">ASP.NET 4.5 and 4.5.1 add model binding for Web Forms, WebSocket support, asynchronous handlers, performance enhancements, and many other features.</span></span> <span data-ttu-id="f2d3b-1088">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1088">For more information, see the following resources:</span></span>

- <span data-ttu-id="f2d3b-1089">[ASP.NET 4.5 と Visual Studio 2012](https://docs.microsoft.com/previous-versions/aspnet/hh420390(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1089">[ASP.NET 4.5 and Visual Studio 2012](https://docs.microsoft.com/previous-versions/aspnet/hh420390(v=vs.110))</span></span>

- [<span data-ttu-id="f2d3b-1090">Visual Studio 2013 の ASP.NET と Web ツールのリリース ノート</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1090">ASP.NET and Web Tools for Visual Studio 2013 Release Notes</span></span>](/aspnet/visual-studio/overview/2013/release-notes)

### <a name="networking-a-namenetworking-"></a><span data-ttu-id="f2d3b-1091">ネットワーク <a name="networking" /></span><span class="sxs-lookup"><span data-stu-id="f2d3b-1091">Networking <a name="networking" /></span></span>

<span data-ttu-id="f2d3b-1092">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] は、HTTP アプリケーションに新しいプログラミング インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1092">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] provides a new programming interface for HTTP applications.</span></span> <span data-ttu-id="f2d3b-1093">詳細については、新しい <xref:System.Net.Http?displayProperty=nameWithType> 名前空間と <xref:System.Net.Http.Headers?displayProperty=nameWithType> 名前空間を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1093">For more information, see the new <xref:System.Net.Http?displayProperty=nameWithType> and <xref:System.Net.Http.Headers?displayProperty=nameWithType> namespaces.</span></span>

<span data-ttu-id="f2d3b-1094">既存の <xref:System.Net.HttpListener> と関連クラスを使用して WebSocket 接続を受け入れ、やり取りするための新しいプログラミング インターフェイスのサポートも含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1094">Support is also included for a new programming interface for accepting and interacting with a WebSocket connection by using the existing <xref:System.Net.HttpListener> and related classes.</span></span> <span data-ttu-id="f2d3b-1095">詳細については、新しい <xref:System.Net.WebSockets> 名前空間と <xref:System.Net.HttpListener> クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1095">For more information, see the new <xref:System.Net.WebSockets> namespace and the <xref:System.Net.HttpListener> class.</span></span>

<span data-ttu-id="f2d3b-1096">また [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] には、次のネットワークの機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1096">In addition, the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] includes the following networking improvements:</span></span>

- <span data-ttu-id="f2d3b-1097">RFC 準拠の URI サポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1097">RFC-compliant URI support.</span></span> <span data-ttu-id="f2d3b-1098">詳細については、<xref:System.Uri> および関連クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1098">For more information, see <xref:System.Uri> and related classes.</span></span>

- <span data-ttu-id="f2d3b-1099">国際化ドメイン名 (IDN: Internationalized Domain Name) による解析のサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1099">Support for Internationalized Domain Name (IDN) parsing.</span></span> <span data-ttu-id="f2d3b-1100">詳細については、<xref:System.Uri> および関連クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1100">For more information, see <xref:System.Uri> and related classes.</span></span>

- <span data-ttu-id="f2d3b-1101">電子メール アドレスの国際化 (EAI) のサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1101">Support for Email Address Internationalization (EAI).</span></span> <span data-ttu-id="f2d3b-1102">詳細については、「<xref:System.Net.Mail>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1102">For more information, see the <xref:System.Net.Mail> namespace.</span></span>

- <span data-ttu-id="f2d3b-1103">強化された IPv6 サポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1103">Improved IPv6 support.</span></span> <span data-ttu-id="f2d3b-1104">詳細については、「<xref:System.Net.NetworkInformation>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1104">For more information, see the <xref:System.Net.NetworkInformation> namespace.</span></span>

- <span data-ttu-id="f2d3b-1105">デュアル モードのソケットのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1105">Dual-mode socket support.</span></span> <span data-ttu-id="f2d3b-1106">詳細については、<xref:System.Net.Sockets.Socket> クラスおよび <xref:System.Net.Sockets.TcpListener> クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1106">For more information, see the <xref:System.Net.Sockets.Socket> and <xref:System.Net.Sockets.TcpListener> classes.</span></span>

<a name="client" />

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f2d3b-1107">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1107">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f2d3b-1108">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、WPF (Windows Presentation Foundation) の次の領域の機能が変更および強化されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1108">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Windows Presentation Foundation (WPF) contains changes and improvements in the following areas:</span></span>

- <span data-ttu-id="f2d3b-1109">クイック アクセス ツール バー、アプリケーション メニューおよびタブをホストするリボン ユーザー インターフェイスを実装できる新しい <xref:System.Windows.Controls.Ribbon.Ribbon> コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1109">The new <xref:System.Windows.Controls.Ribbon.Ribbon> control, which enables you to implement a ribbon user interface that hosts a Quick Access Toolbar, Application Menu, and tabs.</span></span>

- <span data-ttu-id="f2d3b-1110">同期および非同期のデータ検証をサポートする新しい <xref:System.ComponentModel.INotifyDataErrorInfo> インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1110">The new <xref:System.ComponentModel.INotifyDataErrorInfo> interface, which supports synchronous and asynchronous data validation.</span></span>

- <span data-ttu-id="f2d3b-1111"><xref:System.Windows.Controls.VirtualizingPanel> および <xref:System.Windows.Threading.Dispatcher> クラスの新しい機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1111">New features for the <xref:System.Windows.Controls.VirtualizingPanel> and <xref:System.Windows.Threading.Dispatcher> classes.</span></span>

- <span data-ttu-id="f2d3b-1112">グループ化された大量のデータを表示するときに、非 UI スレッドのコレクションにアクセスすることによってパフォーマンスを向上。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1112">Improved performance when displaying large sets of grouped data, and by accessing collections on non-UI threads.</span></span>

- <span data-ttu-id="f2d3b-1113">静的プロパティへのデータ バインディング、<xref:System.Reflection.ICustomTypeProvider> インターフェイスを実装するカスタム型へのデータ バインディング、およびバインディング式からのデータ バインディング情報の取得。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1113">Data binding to static properties, data binding to custom types that implement the <xref:System.Reflection.ICustomTypeProvider> interface, and retrieval of data binding information from a binding expression.</span></span>

- <span data-ttu-id="f2d3b-1114">値の変更に伴うデータの再配置 (ライブ形成)。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1114">Repositioning of data as the values change (live shaping).</span></span>

- <span data-ttu-id="f2d3b-1115">項目コンテナーのデータ コンテキストを切断するかどうかをチェックする機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1115">Ability to check whether the data context for an item container is disconnected.</span></span>

- <span data-ttu-id="f2d3b-1116">プロパティの変更とデータ ソースの更新までの経過時間を設定する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1116">Ability to set the amount of time that should elapse between property changes and data source updates.</span></span>

- <span data-ttu-id="f2d3b-1117">弱いイベント パターン実装時のサポートの強化。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1117">Improved support for implementing weak event patterns.</span></span> <span data-ttu-id="f2d3b-1118">また、イベントでマークアップ拡張機能を使用することもできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1118">Also, events can now accept markup extensions.</span></span>

<a name="windows_communication_foundation" />

### <a name="windows-communication-foundation-wcf"></a><span data-ttu-id="f2d3b-1119">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1119">Windows Communication Foundation (WCF)</span></span>

<span data-ttu-id="f2d3b-1120">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]では、Windows Communication Foundation (WCF) アプリケーションの記述と保守を簡単にするため、次の機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1120">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the following features have been added to make it simpler to write and maintain Windows Communication Foundation (WCF) applications:</span></span>

- <span data-ttu-id="f2d3b-1121">生成された構成ファイルの簡略化。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1121">Simplification of generated configuration files.</span></span>

- <span data-ttu-id="f2d3b-1122">コントラクト優先開発のサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1122">Support for contract-first development.</span></span>

- <span data-ttu-id="f2d3b-1123">ASP.NET 互換モードをより簡単に構成できる機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1123">Ability to configure ASP.NET compatibility mode more easily.</span></span>

- <span data-ttu-id="f2d3b-1124">既定のトランスポート プロパティ値に変更を加え、設定しなければならない可能性を低減しました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1124">Changes in default transport property values to reduce the likelihood that you will have to set them.</span></span>

- <span data-ttu-id="f2d3b-1125"><xref:System.Xml.XmlDictionaryReaderQuotas> クラスを更新して、XML ディクショナリ リーダーのクォータを手動で構成する手間を省けるようにしました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1125">Updates to the <xref:System.Xml.XmlDictionaryReaderQuotas> class to reduce the likelihood that you will have to manually configure quotas for XML dictionary readers.</span></span>

- <span data-ttu-id="f2d3b-1126">ビルド処理の一部として Visual Studio による WCF 構成ファイルを検証することで、アプリケーションを実行する前に構成エラーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1126">Validation of WCF configuration files by Visual Studio as part of the build process, so you can detect configuration errors before you run your application.</span></span>

- <span data-ttu-id="f2d3b-1127">新しい非同期ストリーミングのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1127">New asynchronous streaming support.</span></span>

- <span data-ttu-id="f2d3b-1128">Internet Information Services (IIS) での HTTPS 上のエンドポイントを公開しやすくする新しい HTTPS プロトコル マッピング。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1128">New HTTPS protocol mapping to make it easier to expose an endpoint over HTTPS with Internet Information Services (IIS).</span></span>

- <span data-ttu-id="f2d3b-1129">`?singleWSDL` をサービス URL に追加して 1 つの WSDL ドキュメントのメタデータを生成する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1129">Ability to generate metadata in a single WSDL document by appending `?singleWSDL` to the service URL.</span></span>

- <span data-ttu-id="f2d3b-1130">TCP トランスポートと同様のパフォーマンス特性を持つポート 80 と 443 で真の双方向通信を可能にする Websockets のサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1130">Websockets support to enable true bidirectional communication over ports 80 and 443 with performance characteristics similar to the TCP transport.</span></span>

- <span data-ttu-id="f2d3b-1131">コード内の構成サービスのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1131">Support for configuring services in code.</span></span>

- <span data-ttu-id="f2d3b-1132">XML エディターのツール ヒント。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1132">XML Editor tooltips.</span></span>

- <span data-ttu-id="f2d3b-1133"><xref:System.ServiceModel.ChannelFactory> キャッシュのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1133"><xref:System.ServiceModel.ChannelFactory> caching support.</span></span>

- <span data-ttu-id="f2d3b-1134">バイナリ エンコーダーの圧縮サポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1134">Binary encoder compression support.</span></span>

- <span data-ttu-id="f2d3b-1135">開発者が「ファイア アンド フォーゲット (撃ち放し)」メッセージングを使用するサービスを作成できるようにする UDP トランスポートのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1135">Support for a UDP transport that enables developers to write services that use "fire and forget" messaging.</span></span> <span data-ttu-id="f2d3b-1136">クライアントは、サービスにメッセージを送信しますが、サービスからの応答を期待しません。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1136">A client sends a message to a service and expects no response from the service.</span></span>

- <span data-ttu-id="f2d3b-1137">HTTP トランスポートとトランスポート セキュリティを使用したときに、単一の WCF エンドポイントで複数の認証モードをサポートする機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1137">Ability to support multiple authentication modes on a single WCF endpoint when using the HTTP transport and transport security.</span></span>

- <span data-ttu-id="f2d3b-1138">国際化ドメイン名 (IDN: Internationalized Domain Name) を使用する WCF サービスのサポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1138">Support for WCF services that use internationalized domain names (IDNs).</span></span>

<span data-ttu-id="f2d3b-1139">詳細については、「[Windows Communication Foundation 4.5 の新機能](https://go.microsoft.com/fwlink/?LinkId=228173)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1139">For more information, see [What's New in Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=228173).</span></span>

<a name="windows_workflow_foundation" />

### <a name="windows-workflow-foundation-wf"></a><span data-ttu-id="f2d3b-1140">Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1140">Windows Workflow Foundation (WF)</span></span>

<span data-ttu-id="f2d3b-1141">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、次に示すようないくつかの新しい機能が Windows Workflow Foundation (WF) に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1141">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], several new features were added to Windows Workflow Foundation (WF), including:</span></span>

- <span data-ttu-id="f2d3b-1142">最初に .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](https://go.microsoft.com/fwlink/?LinkID=215092)) の一部として導入された、ステート マシンのワークフロー。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1142">State machine workflows, which were first introduced as part of the .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](https://go.microsoft.com/fwlink/?LinkID=215092)).</span></span> <span data-ttu-id="f2d3b-1143">この更新プログラムには、開発者がステート マシン ワークフローを作成できるようにする新しいクラスとアクティビティが複数含まれていました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1143">This update included several new classes and activities that enabled developers to create state machine workflows.</span></span> <span data-ttu-id="f2d3b-1144">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、これらのクラスとアクティビティが、次を含むように更新されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1144">These classes and activities were updated for the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] to include:</span></span>

    - <span data-ttu-id="f2d3b-1145">状態でブレークポイントを設定する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1145">The ability to set breakpoints on states.</span></span>

    - <span data-ttu-id="f2d3b-1146">ワークフロー デザイナーで遷移をコピーして貼り付ける機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1146">The ability to copy and paste transitions in the workflow designer.</span></span>

    - <span data-ttu-id="f2d3b-1147">共有されるトリガーの遷移作成のデザイナー サポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1147">Designer support for shared trigger transition creation.</span></span>

    - <span data-ttu-id="f2d3b-1148"><xref:System.Activities.Statements.StateMachine>、 <xref:System.Activities.Statements.State>、および <xref:System.Activities.Statements.Transition> などのようにステート マシン ワークフローを作成する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1148">Activities for creating state machine workflows, including: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State>, and <xref:System.Activities.Statements.Transition>.</span></span>

- <span data-ttu-id="f2d3b-1149">次のようなワークフロー デザイナーの機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1149">Enhanced Workflow Designer features such as the following:</span></span>

    - <span data-ttu-id="f2d3b-1150">**[クイック検索]** や **[フォルダーを指定して検索]** など、Visual Studio で強化されたワークフロー検索機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1150">Enhanced workflow search capabilities in Visual Studio, including **Quick Find** and **Find in Files**.</span></span>

    - <span data-ttu-id="f2d3b-1151">2 番目の子アクティビティがコンテナー アクティビティに追加されたときに、自動的にシーケンス アクティビティを作成し、両方のアクティビティをシーケンス アクティビティに含める機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1151">Ability to automatically create a Sequence activity when a second child activity is added to a container activity, and to include both activities in the Sequence activity.</span></span>

    - <span data-ttu-id="f2d3b-1152">スクロール バーを使用せずに変更されるワークフローの表示部分を変更できるようにするパン サポート。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1152">Panning support, which enables the visible portion of a workflow to be changed without using the scroll bars.</span></span>

    - <span data-ttu-id="f2d3b-1153">ツリー スタイルのアウトライン ビューでワークフローのコンポーネントを表示し、**[ドキュメント アウトライン]** ビューでコンポーネントを選択できるようにする新しい **[ドキュメント アウトライン]** ビュー。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1153">A new **Document Outline** view that shows the components of a workflow in a tree-style outline view and lets you select a component in the **Document Outline** view.</span></span>

    - <span data-ttu-id="f2d3b-1154">アクティビティに注釈を追加できる機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1154">Ability to add annotations to activities.</span></span>

    - <span data-ttu-id="f2d3b-1155">ワークフロー デザイナーでアクティビティ デリゲートを定義および使用する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1155">Ability to define and consume activity delegates by using the workflow designer.</span></span>

    - <span data-ttu-id="f2d3b-1156">ステート マシンのアクティビティと遷移、およびフローチャート ワークフローの自動接続と自動挿入。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1156">Auto-connect and auto-insert for activities and transitions in state machine and flowchart workflows.</span></span>

- <span data-ttu-id="f2d3b-1157">ワークフローのビュー状態情報を XAML ファイルの 1 つの要素に保管して、ビュー状態情報を簡単に見つけ、編集できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1157">Storage of the view state information for a workflow in a single element in the XAML file, so you can easily locate and edit the view state information.</span></span>

- <span data-ttu-id="f2d3b-1158">子アクティビティの永続化を防ぐ NoPersistScope コンテナー アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1158">A NoPersistScope container activity to prevent child activities from persisting.</span></span>

- <span data-ttu-id="f2d3b-1159">C# 式のサポート: </span><span class="sxs-lookup"><span data-stu-id="f2d3b-1159">Support for C# expressions:</span></span>

    - <span data-ttu-id="f2d3b-1160">Visual Basic を使用するワークフロー プロジェクトは、Visual Basic 式を使用し、C# ワークフロー プロジェクトは C# 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1160">Workflow projects that use Visual Basic will use Visual Basic expressions, and C# workflow projects will use C# expressions.</span></span>

    - <span data-ttu-id="f2d3b-1161">Visual Studio 2010 で作成され、Visual Basic 式が使用されている C# ワークフロー プロジェクトは、C# 式を使用する C# ワークフロー プロジェクトと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1161">C# workflow projects that were created in Visual Studio 2010 and that have Visual Basic expressions are compatible with C# workflow projects that use C# expressions.</span></span>

- <span data-ttu-id="f2d3b-1162">バージョン管理機能の強化</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1162">Versioning enhancements:</span></span>

    - <span data-ttu-id="f2d3b-1163">永続化されたワークフロー インスタンスとワークフロー定義間のマッピングを提供する新しい <xref:System.Activities.WorkflowIdentity> クラス。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1163">The new  <xref:System.Activities.WorkflowIdentity> class, which provides a mapping between a persisted workflow instance and its workflow definition.</span></span>

    - <span data-ttu-id="f2d3b-1164"><xref:System.ServiceModel.Activities.WorkflowServiceHost> を含む同じホスト内の複数のワークフローのバージョンの並列実行。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1164">Side-by-side execution of multiple workflow versions in the same host, including <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>

    - <span data-ttu-id="f2d3b-1165">動的更新プログラムで、永続化されたワークフロー インスタンスの定義を変更する機能。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1165">In Dynamic Update, the ability to modify the definition of a persisted workflow instance.</span></span>

- <span data-ttu-id="f2d3b-1166">既存のサービス コントラクトに合わせて自動的にアクティビティを生成するサポートが提供されるコントラクト優先のワークフロー サービス開発。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1166">Contract-first workflow service development, which provides support for automatically generating activities to match an existing service contract.</span></span>

 <span data-ttu-id="f2d3b-1167">詳細については、「[.NET 4.5 での Windows Workflow Foundation の新機能](https://go.microsoft.com/fwlink/?LinkId=228176)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1167">For more information, see [What's New in Windows Workflow Foundation](https://go.microsoft.com/fwlink/?LinkId=228176).</span></span>

<a name="tailored" />

### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]

[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] <span data-ttu-id="f2d3b-1168">のアプリは、特定のフォーム ファクターに合わせて設計されており、Windows オペレーティング システムの機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1168">apps are designed for specific form factors and leverage the power of the Windows operating system.</span></span> <span data-ttu-id="f2d3b-1169">C# または Visual Basic を使用して Windows 用の [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] アプリをビルドするために、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] または 4.5.1 のサブセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1169">A subset of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or 4.5.1 is available for building [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps for Windows by using C# or Visual Basic.</span></span> <span data-ttu-id="f2d3b-1170">このサブセットは [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] と呼ばれ、Windows デベロッパー センターの[概要](https://go.microsoft.com/fwlink/?LinkId=228491)のページで説明されています。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1170">This subset is called [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and is discussed in an [overview](https://go.microsoft.com/fwlink/?LinkId=228491) in the Windows Dev Center.</span></span>

### <a name="portable-class-libraries-a-nameportable-"></a><span data-ttu-id="f2d3b-1171">ポータブル クラス ライブラリ <a name="portable" /></span><span class="sxs-lookup"><span data-stu-id="f2d3b-1171">Portable Class Libraries <a name="portable" /></span></span>

<span data-ttu-id="f2d3b-1172">Visual Studio 2012 (および以降のバージョン) のポータブル クラス ライブラリ プロジェクトを使うと、複数の .NET Framework プラットフォームで動作するマネージド アセンブリを作成してビルドできます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1172">The Portable Class Library project in Visual Studio 2012 (and later versions) enables you to write and build managed assemblies that work on multiple .NET Framework platforms.</span></span> <span data-ttu-id="f2d3b-1173">ポータブル クラス ライブラリ プロジェクトを使用して、対象とするプラットフォーム (Windows Phone や [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1173">Using a Portable Class Library project, you choose the platforms (such as Windows Phone and [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]) to target.</span></span> <span data-ttu-id="f2d3b-1174">プロジェクトで使用できる型およびメンバーは、自動的にこれらのプラットフォーム間で共通の型とメンバーに制限されます。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1174">The available types and members in your project are automatically restricted to the common types and members across these platforms.</span></span> <span data-ttu-id="f2d3b-1175">詳細については、[ポータブル クラス ライブラリ](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1175">For more information, see [Portable Class Library](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2d3b-1176">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1176">See also</span></span>

- [<span data-ttu-id="f2d3b-1177">NET Framework および特別なリリース</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1177">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
- [<span data-ttu-id="f2d3b-1178">.NET Framework のアクセシビリティの新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1178">What's new in accessibility in the .NET Framework</span></span>](whats-new-in-accessibility.md)
- [<span data-ttu-id="f2d3b-1179">Visual Studio 2017 の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1179">What's New in Visual Studio 2017</span></span>](/visualstudio/ide/whats-new-in-visual-studio)
- [<span data-ttu-id="f2d3b-1180">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1180">ASP.NET</span></span>](/aspnet)
- [<span data-ttu-id="f2d3b-1181">Visual C++ の新機能</span><span class="sxs-lookup"><span data-stu-id="f2d3b-1181">What’s New in Visual C++</span></span>](/cpp/what-s-new-for-visual-cpp-in-visual-studio)
