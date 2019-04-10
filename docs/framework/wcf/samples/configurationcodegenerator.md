---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: 7625060cd0512bb7498a931d7b93a731e52c9f00
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195190"
---
# <a name="configurationcodegenerator"></a><span data-ttu-id="f3344-102">ConfigurationCodeGenerator</span><span class="sxs-lookup"><span data-stu-id="f3344-102">ConfigurationCodeGenerator</span></span>
<span data-ttu-id="f3344-103">ConfigurationCodeGenerator は、カスタム チャネルの実装を構成システムに公開する際に使用できるツールです。</span><span class="sxs-lookup"><span data-stu-id="f3344-103">The ConfigurationCodeGenerator is a tool that you can use to expose your custom channel implementations to the configuration system.</span></span> <span data-ttu-id="f3344-104">カスタム チャネルのユーザーは、このツールを使用することによって、`NetTcpBinding` などのシステム指定のバインディングやカスタム バインドを `TcpTransportBindingElement` で構成するのと同じように、.config ファイルを使用してカスタム チャネルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f3344-104">This allows users of your custom channel to configure your channel by using a .config file just as they would configure a system-provided binding such as `NetTcpBinding` or a custom binding using the `TcpTransportBindingElement`.</span></span>  
  
 <span data-ttu-id="f3344-105">新しい `BindingElement` または `Binding` を使用してカスタム チャネルを記述し、プログラミング モデルに公開する場合は、.config ファイルを使用して、`BindingElement` または `Binding` を構成可能にするためのクラスのセットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3344-105">When you write a custom channel and expose it to the programming model by using a new `BindingElement` or `Binding`, you must create a set of classes to make the `BindingElement` or `Binding` configurable using a .config file.</span></span> <span data-ttu-id="f3344-106">ConfigurationCodeGenerator ツールを使用すると、こうしたクラスを生成してユーザーの操作性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f3344-106">You can use the ConfigurationCodeGenerator tool to generate these classes and enhance your customer's experience.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="f3344-107">ツールをビルドするには</span><span class="sxs-lookup"><span data-stu-id="f3344-107">To build the tool</span></span>  
  
1.  <span data-ttu-id="f3344-108">ソリューションをビルドする手順については、 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3344-108">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="f3344-109">ソリューションをビルドするには、1 つのファイルが生成されます。ConfigurationCodeGenerator.exe します。</span><span class="sxs-lookup"><span data-stu-id="f3344-109">Building the solution generates one file: ConfigurationCodeGenerator.exe.</span></span> <span data-ttu-id="f3344-110">SampleRun.cmd ファイルはこのツールを使用して、用のクラスを生成する方法を示すサンプル コマンドラインを持ち、[トランスポート。UDP](../../../../docs/framework/wcf/samples/transport-udp.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="f3344-110">The file SampleRun.cmd has a sample command line that shows how to use this tool to generate the classes for the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="f3344-111">ツールを実行するには</span><span class="sxs-lookup"><span data-stu-id="f3344-111">To run the tool</span></span>  
  
1.  <span data-ttu-id="f3344-112">`BindingElement` のカスタム型と `Binding` のカスタム型の両方がある場合は、コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3344-112">At the command prompt type the following if you have both a custom `BindingElement` type and a custom `Binding` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     <span data-ttu-id="f3344-113">`BindingElement` のカスタム型のみがある場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3344-113">Or type the following if you have only a custom `BindingElement` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="f3344-114">`Binding` のカスタム型のみがある場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3344-114">Or type the following if you have only a custom `Binding` type:</span></span>  
  
    ```  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     <span data-ttu-id="f3344-115">このコマンドにより、`BindingElement` 用の 3 つの .cs ファイル (/be: オプションを指定した場合)、標準の `Binding` 用の 5 つの .cs ファイル (/sb: オプションを指定した場合)、および 1 つの .xml ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f3344-115">The command generates three .cs files for the `BindingElement` (if you specified the /be: option), five .cs files for the standard `Binding` (if you specified the /sb: option), and a .xml file.</span></span>  
  
    1.  <span data-ttu-id="f3344-116">/be オプションを使用した場合、いずれかの .cs ファイルに、バインディング要素用の `BindingElementExtensionSection` が実装されます。</span><span class="sxs-lookup"><span data-stu-id="f3344-116">If you used the /be option, one of the .cs files implements the `BindingElementExtensionSection` for your binding element.</span></span> <span data-ttu-id="f3344-117">このコードにより、`BindingElement` が構成システムに公開されます。したがって他のカスタム バインディングも、このバインディング要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3344-117">This code exposes your `BindingElement` to the configuration system, so that other custom bindings can use your binding element.</span></span> <span data-ttu-id="f3344-118">他のファイルには、既定値と定数を示すクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="f3344-118">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="f3344-119">ファイルでは、既定値を更新する必要があることが `//TODO` コメントで示されています。</span><span class="sxs-lookup"><span data-stu-id="f3344-119">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
    2.  <span data-ttu-id="f3344-120">/sb オプションを指定した場合、2 つの .cs ファイルにそれぞれ `StandardBindingElement` と `StandardBindingCollectionElement` が実装されます。これによって、標準バインディングが構成システムに公開されます。</span><span class="sxs-lookup"><span data-stu-id="f3344-120">If you specified the /sb option, two of the .cs files implement a `StandardBindingElement` and a `StandardBindingCollectionElement` respectively, which exposes your standard binding to the configuration system.</span></span> <span data-ttu-id="f3344-121">他のファイルには、既定値と定数を示すクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="f3344-121">The other files have classes that represent defaults and constants.</span></span> <span data-ttu-id="f3344-122">ファイルでは、既定値を更新する必要があることが `//TODO` コメントで示されています。</span><span class="sxs-lookup"><span data-stu-id="f3344-122">The files have `//TODO` comments to remind you to update the default values.</span></span>  
  
         <span data-ttu-id="f3344-123">/Sb が指定されている場合: オプション、CodeToAddTo\<*YourStdBinding*> .cs にはコードを標準バインディングを実装するクラスに手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3344-123">If you specified the /sb: option the CodeToAddTo\<*YourStdBinding*>.cs has code that you must manually add into the class that implements your standard binding.</span></span>  
  
     <span data-ttu-id="f3344-124">SampleConfig.xml ファイルには、構成コードが含まれます。このコードは、前の手順 1. または 2. で定義されたハンドラーを登録する構成ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3344-124">The SampleConfig.xml file contains the configuration code that you must add to the configuration file that registers the handlers defined in the previous step 1 or 2.</span></span>  
