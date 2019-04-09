---
title: 型コンバーターおよびマークアップ拡張機能で使用できるサービス コンテキスト
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converter services how-to
ms.assetid: b4dad00f-03da-4579-a4e9-d8d72d2ccbce
ms.openlocfilehash: 850e266aed6fc2d69722ba6dac3baa3e115678a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147798"
---
# <a name="service-contexts-available-to-type-converters-and-markup-extensions"></a><span data-ttu-id="5c627-102">型コンバーターおよびマークアップ拡張機能で使用できるサービス コンテキスト</span><span class="sxs-lookup"><span data-stu-id="5c627-102">Service Contexts Available to Type Converters and Markup Extensions</span></span>
<span data-ttu-id="5c627-103">型コンバーターとマークアップ拡張機能の使用をサポートする型の作成者には、マークアップまたは周辺のオブジェクト グラフ構造体のどこで使用されているかを示す文脈情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c627-103">Authors of the types that support type converter and markup extension usages must often have contextual information about where a usage is located in the markup, or in surrounding object graph structure.</span></span> <span data-ttu-id="5c627-104">情報は、指定されるオブジェクトを正しくインスタンス化するため、またオブジェクト グラフ内の既存オブジェクトへのオブジェクト参照を行うために必要です。</span><span class="sxs-lookup"><span data-stu-id="5c627-104">Information might be needed so that the provided object is instantiated correctly or so that object references to existing objects in the object graph can be made.</span></span> <span data-ttu-id="5c627-105">.NET Framework XAML サービスを使用している場合、必要となる可能性のあるコンテキストは一連のサービス インターフェイスとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-105">When using .NET Framework XAML Services, the context that might be required is exposed as a series of service interfaces.</span></span> <span data-ttu-id="5c627-106">型コンバーターまたはマークアップ拡張のサポート コードでは、 <xref:System.Xaml.XamlObjectWriter> または関連する型から渡される使用可能なサービス プロバイダー コンテキストを使用して、サービスを照会できます。</span><span class="sxs-lookup"><span data-stu-id="5c627-106">Type converter or markup extension support code can query for a service by using a service provider context that is available and passed through from <xref:System.Xaml.XamlObjectWriter> or related types.</span></span> <span data-ttu-id="5c627-107">XAML スキーマ コンテキストは、このようなサービスを通じて直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c627-107">The XAML schema context is directly available through one such service.</span></span> <span data-ttu-id="5c627-108">このトピックでは、値コンバーター実装からサービス コンテキストにアクセスする方法を説明し、通常使用できるサービスとその役割の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5c627-108">This topic describes how to access service contexts from a value converter implementation, and lists typically available services and their roles.</span></span>  
  
<a name="obtaining_services"></a>   
## <a name="obtaining-services"></a><span data-ttu-id="5c627-109">サービスの取得</span><span class="sxs-lookup"><span data-stu-id="5c627-109">Obtaining Services</span></span>  
 <span data-ttu-id="5c627-110">値コンバーターの実装者は、通常、値コンバーターが適用される何らかの種類のコンテキストにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c627-110">As an implementer of a value converter, you often need access to some type of context in which the value converter is applied.</span></span> <span data-ttu-id="5c627-111">たとえば、アクティブな XAML スキーマ コンテキスト、XAML スキーマ コンテキストや XAML オブジェクト ライターが提供する型マッピング システムへのアクセスなどの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c627-111">This context might include information such as the active XAML schema context, access to the type mapping system that the XAML schema context and XAML object writer provide, and so on.</span></span> <span data-ttu-id="5c627-112">マークアップ拡張機能または型コンバーターの実装で使用されるサービスは、各仮想メソッドのシグネチャの一部であるコンテキスト パラメーターを通じて伝達されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-112">The services available for a markup extension or type converter implementation are communicated through the context parameters that are part of the signature of each virtual method.</span></span> <span data-ttu-id="5c627-113">いずれの場合でも、コンテキストに <xref:System.IServiceProvider> が実装されているので、 <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> を呼び出してサービスを要求することができます。</span><span class="sxs-lookup"><span data-stu-id="5c627-113">In every case, you have <xref:System.IServiceProvider> implemented in the context, and can call <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> to request a service.</span></span>  
  
<a name="services_for_a_markup_extension"></a>   
## <a name="services-for-a-markup-extension"></a><span data-ttu-id="5c627-114">マークアップ拡張機能のサービス</span><span class="sxs-lookup"><span data-stu-id="5c627-114">Services for a Markup Extension</span></span>  
 <xref:System.Windows.Markup.MarkupExtension> <span data-ttu-id="5c627-115">1 つだけの仮想メソッドを持つ<xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>します。</span><span class="sxs-lookup"><span data-stu-id="5c627-115">has only one virtual method, <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>.</span></span> <span data-ttu-id="5c627-116">入力パラメーター `serviceProvider` は、XAML プロセッサによってマークアップ拡張機能が呼び出されたときに、サービスが実装に伝達される方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5c627-116">The input `serviceProvider` parameter is how the services are communicated to implementations when the markup extension is called by a XAML processor.</span></span> <span data-ttu-id="5c627-117">次の疑似コードは、マークアップ拡張機能の実装が <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>でサービスを照会する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5c627-117">The following pseudocode illustrates how a markup extension implementation might query for services in its <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>:</span></span>  
  
```  
public override object ProvideValue(IServiceProvider serviceProvider)  
{  
...  
    // Get the IXamlTypeResolver from the service provider  
    if (serviceProvider == null)  
    {  
        throw new ArgumentNullException("serviceProvider");  
    }  
    IXamlTypeResolver xamlTypeResolver = serviceProvider.GetService(typeof(IXamlTypeResolver)) as IXamlTypeResolver;  
    if (xamlTypeResolver == null)  
   {  
        throw new ArgumentException("IXamlTypeResolver"));  
    }  
...  
}  
```  
  
<a name="services_for_a_type_converter"></a>   
## <a name="services-for-a-type-converter"></a><span data-ttu-id="5c627-118">型コンバーターのサービス</span><span class="sxs-lookup"><span data-stu-id="5c627-118">Services for a Type Converter</span></span>  
 <xref:System.ComponentModel.TypeConverter> <span data-ttu-id="5c627-119">サービス コンテキストを使用して、XAML の使用方法をサポートする 4 つの仮想メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="5c627-119">has four virtual methods that use a service context and that support XAML usages.</span></span> <span data-ttu-id="5c627-120">これらのメソッドは、それぞれ入力パラメーター `context` を渡します。</span><span class="sxs-lookup"><span data-stu-id="5c627-120">Each of these methods passes an input `context` parameter.</span></span> <span data-ttu-id="5c627-121">このパラメーターの型は <xref:System.ComponentModel.ITypeDescriptorContext>ですが、そのインターフェイスは <xref:System.IServiceProvider>を継承するため、型コンバーターの実装では <xref:System.IServiceProvider.GetService%2A> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c627-121">This parameter is of type <xref:System.ComponentModel.ITypeDescriptorContext>, but that interface inherits <xref:System.IServiceProvider>, and therefore, there is a <xref:System.IServiceProvider.GetService%2A> method available to type converter implementations.</span></span>  
  
 <span data-ttu-id="5c627-122">次の疑似コードは、XAML の使用に対する型コンバーターの実装が、そのオーバーライドの 1 つ (このケースでは <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>) の中でサービスを照会する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5c627-122">The following pseudocode illustrates how a type converter implementation for XAML usages might query for services in one of its overrides, in this case <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>:</span></span>  
  
```  
public override object ConvertFrom(ITypeDescriptorContext typeDescriptorContext,  
  CultureInfo cultureInfo,  
  object source)  
{  
    IRootObjectProvider rootProvider = typeDescriptorContext.GetService(typeof(IRootObjectProvider)) as IRootObjectProvider;  
    if (rootProvider != null && source is String)  
    {  
        //return something, else ...  
    }  
    throw GetConvertFromException(source);  
}  
```  
  
<a name="services_for_a_value_serializer"></a>   
## <a name="services-for-a-value-serializer"></a><span data-ttu-id="5c627-123">値シリアライザー サービス</span><span class="sxs-lookup"><span data-stu-id="5c627-123">Services for a Value Serializer</span></span>  
 <span data-ttu-id="5c627-124">値シリアライザーのコンテキストでは、 <xref:System.Windows.Markup.ValueSerializer> クラスに固有のサービス プロバイダー型 <xref:System.Windows.Markup.IValueSerializerContext>を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c627-124">For value serializer context, you use a service provider type that is specific to the <xref:System.Windows.Markup.ValueSerializer> class, <xref:System.Windows.Markup.IValueSerializerContext>.</span></span> <span data-ttu-id="5c627-125">このコンテキストは、 <xref:System.Windows.Markup.ValueSerializer> の 4 つの仮想メソッドのオーバーライドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-125">That context is passed to overrides of the four <xref:System.Windows.Markup.ValueSerializer> virtual methods.</span></span> <span data-ttu-id="5c627-126">サービスを取得するには、コンテキストから <xref:System.IServiceProvider.GetService%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5c627-126">Call <xref:System.IServiceProvider.GetService%2A> from the context to obtain services.</span></span>  
  
<a name="using_the_xaml_service_provider_contexts"></a>   
## <a name="using-the-xaml-service-provider-contexts"></a><span data-ttu-id="5c627-127">XAML サービス プロバイダー コンテキストの使用</span><span class="sxs-lookup"><span data-stu-id="5c627-127">Using the XAML Service Provider Contexts</span></span>  
 <span data-ttu-id="5c627-128">マークアップ拡張機能または型コンバーターで使用できる XAML サービスにアクセスするための <xref:System.IServiceProvider.GetService%2A> のサービス プロバイダーは、内部クラスとして実装されており、インターフェイスを通して、および関連コンテキストに渡されるという方法を通してのみ公開されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-128">The service provider for <xref:System.IServiceProvider.GetService%2A> access to XAML services available to markup extensions or type converters is implemented as an internal class, with exposure only through the interface and how it is passed into the relevant context .</span></span> <span data-ttu-id="5c627-129">読み込みパスまたは保存パスの既定の .NET Framework XAML サービス実装にある XAML 処理操作が、サービス コンテキストを必要とする関連マークアップ拡張機能または型コンバーター メソッドを呼び出すと、この内部オブジェクトが渡されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-129">Whenever a XAML processing operation in the default .NET Framework XAML Services implementations of load path or save path invokes the relevant markup extension or type converter methods that require a service context, this internal object is passed.</span></span> <span data-ttu-id="5c627-130">状況に応じて、システムのサービス コンテキストは `MarkupExtensionContext` か `TextSyntaxContext`を提供しますが、これら両方のクラスの詳細は内部にあります。</span><span class="sxs-lookup"><span data-stu-id="5c627-130">Depending on the circumstance, the system service context provides either `MarkupExtensionContext` or `TextSyntaxContext`, but the specifics of both of these classes are internal.</span></span> <span data-ttu-id="5c627-131">これらのクラスとの対話は、 <xref:System.IServiceProvider.GetService%2A>を通してサービスを要求することに限定されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-131">Your interaction with these classes is limited to requesting services from them, through <xref:System.IServiceProvider.GetService%2A>.</span></span>  
  
<a name="available_systemxaml_services"></a>   
## <a name="available-services-from-the-net-framework-xaml-service-context"></a><span data-ttu-id="5c627-132">.NET Framework XAML サービス コンテキストから使用できるサービス</span><span class="sxs-lookup"><span data-stu-id="5c627-132">Available Services from the .NET Framework XAML Service Context</span></span>  
 <span data-ttu-id="5c627-133">.NET Framework XAML サービスは、マークアップ拡張機能、型コンバーター、値シリアライザーに加え、その他の使用も可能なサービスを定義します。</span><span class="sxs-lookup"><span data-stu-id="5c627-133">.NET Framework XAML Services defines services for markup extensions, type converters, value serializers, and potentially other usages.</span></span> <span data-ttu-id="5c627-134">この後のセクションでは、これらの各サービスについて説明し、実装でのサービスの使用方法についてガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c627-134">The following sections describe each of these services and provide guidance about how the service might be used in an implementation.</span></span>  
  
### <a name="iserviceprovider"></a><span data-ttu-id="5c627-135">IServiceProvider</span><span class="sxs-lookup"><span data-stu-id="5c627-135">IServiceProvider</span></span>  
 <span data-ttu-id="5c627-136">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-136">**Reference documentation**:</span></span> <xref:System.IServiceProvider>  
  
 <span data-ttu-id="5c627-137">**関連:**.NET Framework でのサービス ベースのインフラストラクチャの基本的な操作を呼び出せるように<xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="5c627-137">**Relevant to:** Basic operation of a service-based infrastructure in the .NET Framework so that you can call <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="itypedescriptorcontext"></a><span data-ttu-id="5c627-138">ITypeDescriptorContext</span><span class="sxs-lookup"><span data-stu-id="5c627-138">ITypeDescriptorContext</span></span>  
 <span data-ttu-id="5c627-139">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-139">**Reference documentation**:</span></span> <xref:System.ComponentModel.ITypeDescriptorContext>  
  
 <span data-ttu-id="5c627-140"><xref:System.IServiceProvider>から派生します。</span><span class="sxs-lookup"><span data-stu-id="5c627-140">Derives from <xref:System.IServiceProvider>.</span></span> <span data-ttu-id="5c627-141">このクラスは <xref:System.ComponentModel.TypeConverter> の標準シグネチャのコンテキストを表します。 <xref:System.ComponentModel.TypeConverter> は、.NET Framework 1.0 の時点から存在していたクラスです。</span><span class="sxs-lookup"><span data-stu-id="5c627-141">This class represents context in the standard <xref:System.ComponentModel.TypeConverter> signatures; <xref:System.ComponentModel.TypeConverter> is a class that has existed since .NET Framework 1.0.</span></span> <span data-ttu-id="5c627-142">つまり、XAML や、文字列値の型変換という XAML <xref:System.ComponentModel.TypeConverter> のシナリオが登場する前から使用されていました。</span><span class="sxs-lookup"><span data-stu-id="5c627-142">It predates XAML and the XAML <xref:System.ComponentModel.TypeConverter> scenario for string-value type conversion.</span></span> <span data-ttu-id="5c627-143">.NET Framework XAML サービスのコンテキストでは、 <xref:System.ComponentModel.TypeConverter> のメソッドは明示的に実装されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-143">In the .NET Framework XAML Services context, methods of <xref:System.ComponentModel.TypeConverter> are implemented explicitly.</span></span> <span data-ttu-id="5c627-144">その明示的な実装の動作により、 <xref:System.ComponentModel.ITypeDescriptorContext> API が XAML の型システムまたは XAML からのオブジェクトの読み取りや書き込みに関連したものでないことが、呼び出し側に示されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-144">The explicit implementation's behavior indicates to callers that the <xref:System.ComponentModel.ITypeDescriptorContext> API is not relevant for XAML type systems, or for reading or writing objects from XAML.</span></span> <xref:System.ComponentModel.ITypeDescriptorContext.Container%2A><span data-ttu-id="5c627-145">、 <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>、および<xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A>通常返す`null`.NET Framework XAML サービス コンテキストから。</span><span class="sxs-lookup"><span data-stu-id="5c627-145">, <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>, and <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> generally return `null` from .NET Framework XAML Services contexts.</span></span>  
  
### <a name="ivalueserializercontext"></a><span data-ttu-id="5c627-146">IValueSerializerContext</span><span class="sxs-lookup"><span data-stu-id="5c627-146">IValueSerializerContext</span></span>  
 <span data-ttu-id="5c627-147">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-147">**Reference documentation**:</span></span> <xref:System.Windows.Markup.IValueSerializerContext>  
  
 <span data-ttu-id="5c627-148"><xref:System.ComponentModel.ITypeDescriptorContext> から派生します。これについても、XAML の型システムに不適切な影響を与えないようにするために、明示的な実装に依存します。</span><span class="sxs-lookup"><span data-stu-id="5c627-148">Derives from <xref:System.ComponentModel.ITypeDescriptorContext> and also relies on explicit implementations to suppress false implications about the XAML type system.</span></span> <span data-ttu-id="5c627-149"><xref:System.Windows.Markup.ValueSerializer>の静的ルックアップ ヘルパー メソッドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5c627-149">Supports the static lookup helper methods on <xref:System.Windows.Markup.ValueSerializer>.</span></span>  
  
### <a name="ixamltyperesolver"></a><span data-ttu-id="5c627-150">IXamlTypeResolver</span><span class="sxs-lookup"><span data-stu-id="5c627-150">IXamlTypeResolver</span></span>  
 <span data-ttu-id="5c627-151">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-151">**Reference documentation**:</span></span> <xref:System.Windows.Markup.IXamlTypeResolver>  
  
 <span data-ttu-id="5c627-152">**定義元:**  <xref:System.Windows.Markup> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-152">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-153">**関連:** 読み込みパスのシナリオ、および XAML スキーマ コンテキストとの対話</span><span class="sxs-lookup"><span data-stu-id="5c627-153">**Relevant to:** Load path scenarios, and interaction with XAML schema context</span></span>  
  
 **<span data-ttu-id="5c627-154">サービス API:</span><span class="sxs-lookup"><span data-stu-id="5c627-154">Service API:</span></span>**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A>  
  
 <span data-ttu-id="5c627-155">XAML ライターがオブジェクト グラフに CLR オブジェクトを構築するときに必要な、XAML から CLR への型マッピングに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="5c627-155">Can influence the XAML-to-CLR type mapping that is necessary when the XAML writer constructs a CLR object in an object graph.</span></span> <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A> <span data-ttu-id="5c627-156">XAML の型名に対応する可能性のあるプレフィックスで修飾された文字列を処理 (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>)、CLR を返しますと<xref:System.Type>します。</span><span class="sxs-lookup"><span data-stu-id="5c627-156">processes a potentially prefix-qualified string that corresponds to a XAML type name (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>), and returns a CLR <xref:System.Type>.</span></span> <span data-ttu-id="5c627-157">型の解決は、通常、XAML スキーマ コンテキストに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="5c627-157">Resolving types is typically heavily dependent on XAML schema context.</span></span> <span data-ttu-id="5c627-158">XAML スキーマ コンテキストだけが、どのアセンブリが読み込まれているか、これらのアセンブリの中で、型を解決するためにアクセスできる、またはアクセスする必要があるものはどれかといった考慮事項を認識しています。</span><span class="sxs-lookup"><span data-stu-id="5c627-158">Only the XAML schema context is aware of considerations such as which assemblies are loaded, and which of these assemblies can or should be accessed for type resolution.</span></span>  
  
### <a name="iuricontext"></a><span data-ttu-id="5c627-159">IUriContext</span><span class="sxs-lookup"><span data-stu-id="5c627-159">IUriContext</span></span>  
 <span data-ttu-id="5c627-160">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-160">**Reference documentation**:</span></span> <xref:System.Windows.Markup.IUriContext>  
  
 <span data-ttu-id="5c627-161">**定義元:**  <xref:System.Windows.Markup> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-161">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-162">**関連:** 読み込みパス、パスの処理の Uri であるメンバーの値を保存または`x:Uri`値。</span><span class="sxs-lookup"><span data-stu-id="5c627-162">**Relevant to:** Load path and save path handling of member values that are URIs or `x:Uri` values.</span></span>  
  
 **<span data-ttu-id="5c627-163">サービス API:</span><span class="sxs-lookup"><span data-stu-id="5c627-163">Service API:</span></span>**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A>  
  
 <span data-ttu-id="5c627-164">このサービスは、グローバルに使用できる URI ルート (存在する場合) を報告します。</span><span class="sxs-lookup"><span data-stu-id="5c627-164">This service reports a globally available URI root, if any.</span></span> <span data-ttu-id="5c627-165">URI ルートは、相対 URI を絶対 URI に解決する場合、またはその逆を行う場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c627-165">The URI root can be used to resolve relative URIs to absolute URIs or vice versa.</span></span> <span data-ttu-id="5c627-166">このシナリオは主に、特定のフレームワークによって、またはフレームワークでよく使用されるルート要素クラスの機能によって公開されるアプリケーション サービスに関連しています。</span><span class="sxs-lookup"><span data-stu-id="5c627-166">This scenario is mainly relevant to application services that are exposed by a particular framework, or capabilities of a frequently used root element class in a framework.</span></span> <span data-ttu-id="5c627-167">ベース URI は、XAML リーダーの設定として確立することができます。その後、XAML オブジェクト ライターに渡され、このサービスによってレポートされます。</span><span class="sxs-lookup"><span data-stu-id="5c627-167">The base URI can be established as a XAML reader setting, which is then passed through to the XAML object writer and reported by this service.</span></span>  
  
### <a name="iambientprovider"></a><span data-ttu-id="5c627-168">IAmbientProvider</span><span class="sxs-lookup"><span data-stu-id="5c627-168">IAmbientProvider</span></span>  
 <span data-ttu-id="5c627-169">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-169">**Reference documentation**:</span></span> <xref:System.Xaml.IAmbientProvider>  
  
 <span data-ttu-id="5c627-170">**定義元:**  <xref:System.Xaml> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-170">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-171">**関連:** パスの処理と型参照の遅延または最適化を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="5c627-171">**Relevant to:** Load path handling and type lookup deferrals or optimizations.</span></span>  
  
 <span data-ttu-id="5c627-172">**サービス API:**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>、その他 3 つ。</span><span class="sxs-lookup"><span data-stu-id="5c627-172">**Service APIs:**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>, 3 others.</span></span>  
  
 <span data-ttu-id="5c627-173">XAML におけるアンビエンスの概念は、型の特定のメンバーをアンビエントとしてマーク付けする手法です。</span><span class="sxs-lookup"><span data-stu-id="5c627-173">The ambience concept in XAML is a technique for marking a particular member of a type as ambient.</span></span> <span data-ttu-id="5c627-174">あるいは、型のインスタンスを保持するすべてのプロパティ値をアンビエント プロパティと見なす必要がある場合には、型をアンビエントにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5c627-174">Alternatively, a type can be ambient so that all property values that hold an instance of the type should be considered ambient properties.</span></span> <span data-ttu-id="5c627-175">XAML ノード ストリームの先にあるか、オブジェクト グラフの下位にあるマークアップ拡張機能または型コンバーターは、読み込み時にアンビエント プロパティまたは型インスタンスにアクセスしたり、保存時にアンビエント構造の情報を活用したりできます。</span><span class="sxs-lookup"><span data-stu-id="5c627-175">Markup extensions or type converters that are further along the XAML node stream and that are descendants in the object graph can access the ambient property or type instance at load time; or they can use knowledge of the ambient structure at save time.</span></span> <span data-ttu-id="5c627-176">これにより、 <xref:System.Windows.Markup.IXamlTypeResolver> や `x:Type`など、その他のサービスの型解決に必要な修飾の程度が左右されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-176">This can affect the degree of qualification that is needed to resolve types for other services, such as for <xref:System.Windows.Markup.IXamlTypeResolver> or for `x:Type`.</span></span> <span data-ttu-id="5c627-177">「 <xref:System.Xaml.AmbientPropertyValue>」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c627-177">See also <xref:System.Xaml.AmbientPropertyValue>.</span></span>  
  
### <a name="ixamlschemacontextprovider"></a><span data-ttu-id="5c627-178">IXamlSchemaContextProvider</span><span class="sxs-lookup"><span data-stu-id="5c627-178">IXamlSchemaContextProvider</span></span>  
 <span data-ttu-id="5c627-179">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-179">**Reference documentation**:</span></span> <xref:System.Xaml.IXamlSchemaContextProvider>  
  
 <span data-ttu-id="5c627-180">**定義元:**  <xref:System.Xaml> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-180">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-181">**関連:** 読み込みパス、および XAML 型をバッキング型に解決する必要がある操作を行う。</span><span class="sxs-lookup"><span data-stu-id="5c627-181">**Relevant to:** Load path, and any operation that must resolve a XAML type to a backing type.</span></span>  
  
 **<span data-ttu-id="5c627-182">サービス API:</span><span class="sxs-lookup"><span data-stu-id="5c627-182">Service API:</span></span>**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A>  
  
 <span data-ttu-id="5c627-183">遅延コンテンツを統合するには、同じスキーマ コンテキストを遅延領域に対しても適用する必要があるので、遅延読み込み操作には XAML スキーマ コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5c627-183">XAML schema context is necessary for any defer load operations, because the same schema context must act on the deferred area in order to integrate the deferred content.</span></span> <span data-ttu-id="5c627-184">XAML スキーマ コンテキストの役割の詳細については、「 [XAML Services](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c627-184">For more information about the role of the XAML schema context, see [XAML Services](index.md).</span></span>  
  
### <a name="irootobjectprovider"></a><span data-ttu-id="5c627-185">IRootObjectProvider</span><span class="sxs-lookup"><span data-stu-id="5c627-185">IRootObjectProvider</span></span>  
 <span data-ttu-id="5c627-186">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-186">**Reference documentation**:</span></span> <xref:System.Xaml.IRootObjectProvider>  
  
 <span data-ttu-id="5c627-187">**定義元:**  <xref:System.Xaml> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-187">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-188">**関連:** 読み込みパス。</span><span class="sxs-lookup"><span data-stu-id="5c627-188">**Relevant to:** Load path.</span></span>  
  
 **<span data-ttu-id="5c627-189">サービス API:</span><span class="sxs-lookup"><span data-stu-id="5c627-189">Service API:</span></span>**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A>  
  
 <span data-ttu-id="5c627-190">このサービスは、特定のフレームワークによって、またはフレームワークでよく使用されるルート要素クラスの機能によって公開されるアプリケーション サービスに関連しています。</span><span class="sxs-lookup"><span data-stu-id="5c627-190">The service is relevant to application services that are exposed by a particular framework or by capabilities of a frequently used root element class in a framework.</span></span> <span data-ttu-id="5c627-191">ルート オブジェクトを取得する 1 つのシナリオは、分離コードとイベント接続をつなげることです。</span><span class="sxs-lookup"><span data-stu-id="5c627-191">One scenario for obtaining the root object is connecting code-behind and event wiring.</span></span> <span data-ttu-id="5c627-192">たとえば、 `x:Class` の WPF 実装は、マークアップ コンパイルと、XAML マークアップの他の場所にあるイベント ハンドラー属性の関連付けにおいて使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c627-192">For example, the WPF implementation of `x:Class` is used for markup compile and wiring of any event handler attribute that is found at any other position in the XAML markup.</span></span> <span data-ttu-id="5c627-193">マークアップ コンパイルの部分クラスで定義されたマークアップと分離コードのコネクション ポイントは、ルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5c627-193">The connection point of markup and code-behind defined partial classes for markup compile is at the root element.</span></span>  
  
### <a name="ixamlnamespaceresolver"></a><span data-ttu-id="5c627-194">IXamlNamespaceResolver</span><span class="sxs-lookup"><span data-stu-id="5c627-194">IXamlNamespaceResolver</span></span>  
 <span data-ttu-id="5c627-195">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-195">**Reference documentation**:</span></span> <xref:System.Xaml.IXamlNamespaceResolver>  
  
 <span data-ttu-id="5c627-196">**定義元:**  <xref:System.Xaml> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-196">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-197">**関連:** 読み込みパス、保存パス。</span><span class="sxs-lookup"><span data-stu-id="5c627-197">**Relevant to:** Load path, save path.</span></span>  
  
 <span data-ttu-id="5c627-198">**サービス API:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> 、保存パスの場合は <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5c627-198">**Service API:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> for load path, <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> for save path.</span></span>  
  
 <xref:System.Xaml.IXamlNamespaceResolver> <span data-ttu-id="5c627-199">XAML 名前空間の識別子を返すことができるサービスは、URI は、元の XAML マークアップで対応付けられたプレフィックスに基づく/。</span><span class="sxs-lookup"><span data-stu-id="5c627-199">is a service that can return a XAML namespace identifier / URI based on its prefix as mapped in the originating XAML markup.</span></span>  
  
### <a name="iprovidevaluetarget"></a><span data-ttu-id="5c627-200">IProvideValueTarget</span><span class="sxs-lookup"><span data-stu-id="5c627-200">IProvideValueTarget</span></span>  
 <span data-ttu-id="5c627-201">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-201">**Reference documentation**:</span></span> <xref:System.Windows.Markup.IProvideValueTarget>  
  
 <span data-ttu-id="5c627-202">**定義元:**  <xref:System.Windows.Markup> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-202">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-203">**関連:** 読み込みパス、パスを保存します。</span><span class="sxs-lookup"><span data-stu-id="5c627-203">**Relevant to:** Load path and save path.</span></span>  
  
 <span data-ttu-id="5c627-204">**サービス API:**  <xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>、 <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>。</span><span class="sxs-lookup"><span data-stu-id="5c627-204">**Service APIs:**  <xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>, <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>.</span></span>  
  
 <xref:System.Windows.Markup.IProvideValueTarget> <span data-ttu-id="5c627-205">読み込み時に機能しているに関するコンテキストを取得する型コンバーターまたはマークアップ拡張を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5c627-205">enables a type converter or markup extension to obtain context about where it is acting at load time.</span></span> <span data-ttu-id="5c627-206">実装では、このコンテキストを使用して、特定の使用を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5c627-206">Implementations might use this context to invalidate a usage.</span></span> <span data-ttu-id="5c627-207">たとえば、WPF では、 <xref:System.Windows.DynamicResourceExtension>などの一部のマークアップ拡張機能内にロジックを保持しています。</span><span class="sxs-lookup"><span data-stu-id="5c627-207">For example, WPF has logic inside some of its markup extensions such as <xref:System.Windows.DynamicResourceExtension>.</span></span> <span data-ttu-id="5c627-208">そのロジックは、 <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> を確認して、依存関係のあるプロパティ (または、その他の依存関係のないプロパティの短い一覧) を設定する場合にのみ拡張機能が使用されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="5c627-208">The logic checks the <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> to make sure that the extension is only used to set dependency properties (or a short list of other non-dependency properties).</span></span>  
  
### <a name="ixamlnameresolver"></a><span data-ttu-id="5c627-209">IXamlNameResolver</span><span class="sxs-lookup"><span data-stu-id="5c627-209">IXamlNameResolver</span></span>  
 <span data-ttu-id="5c627-210">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-210">**Reference documentation**:</span></span> <xref:System.Xaml.IXamlNameResolver>  
  
 <span data-ttu-id="5c627-211">**定義元:**  <xref:System.Xaml> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-211">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-212">**関連:** によって識別されるオブジェクトを解決するパス オブジェクト グラフ定義を読み込む`x:Name`、 `x:Reference`、またはフレームワーク固有の手法です。</span><span class="sxs-lookup"><span data-stu-id="5c627-212">**Relevant to:** Load path object graph definition, resolving objects identified by `x:Name`, `x:Reference`, or framework-specific techniques.</span></span>  
  
 <span data-ttu-id="5c627-213">**サービス API:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>、前方参照を処理する場合などの高度なシナリオで使用されるその他の API。</span><span class="sxs-lookup"><span data-stu-id="5c627-213">**Service APIs:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>; other APIs for more advanced scenarios such as dealing with forward references.</span></span>  
  
 <span data-ttu-id="5c627-214">.NET Framework XAML サービスでの `x:Reference` 処理の 実装は、このサービスに依存しています。</span><span class="sxs-lookup"><span data-stu-id="5c627-214">The .NET Framework XAML Services implementation of `x:Reference` handling relies on this service.</span></span> <span data-ttu-id="5c627-215">特定のフレームワークまたはそのフレームワークをサポートするツールは、このサービスを使用して、 `x:Name` の処理、または同等の (<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 属性で指定された) プロパティの処理を行います。</span><span class="sxs-lookup"><span data-stu-id="5c627-215">Specific frameworks or tools that support the framework use this service for `x:Name` handling or equivalent (<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> attributed) property handling.</span></span>  
  
### <a name="idestinationtypeprovider"></a><span data-ttu-id="5c627-216">IDestinationTypeProvider</span><span class="sxs-lookup"><span data-stu-id="5c627-216">IDestinationTypeProvider</span></span>  
 <span data-ttu-id="5c627-217">**リファレンス ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="5c627-217">**Reference documentation**:</span></span> <xref:System.Xaml.IDestinationTypeProvider>  
  
 <span data-ttu-id="5c627-218">**定義元:**  <xref:System.Xaml> 名前空間、System.Xaml アセンブリ</span><span class="sxs-lookup"><span data-stu-id="5c627-218">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>  
  
 <span data-ttu-id="5c627-219">**関連:** 間接的な CLR 型情報のパスの解決を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="5c627-219">**Relevant to:** Load path resolution of indirect CLR type information.</span></span>  
  
 **<span data-ttu-id="5c627-220">サービス API:</span><span class="sxs-lookup"><span data-stu-id="5c627-220">Service API:</span></span>** <xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A>  
  
 <span data-ttu-id="5c627-221">詳細については、「 <xref:System.Xaml.IDestinationTypeProvider> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c627-221">For more information, see <xref:System.Xaml.IDestinationTypeProvider>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c627-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c627-222">See also</span></span>

- <xref:System.Windows.Markup.MarkupExtension>
- <xref:System.Xaml.XamlObjectWriter>
- [<span data-ttu-id="5c627-223">XAML のマークアップ拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="5c627-223">Markup Extensions for XAML Overview</span></span>](markup-extensions-for-xaml-overview.md)
- [<span data-ttu-id="5c627-224">XAML の型コンバーターの概要</span><span class="sxs-lookup"><span data-stu-id="5c627-224">Type Converters for XAML Overview</span></span>](type-converters-for-xaml-overview.md)
