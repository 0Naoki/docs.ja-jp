---
title: '方法: WSDL コントラクトと共にサービス モニカーを使用する'
ms.date: 03/30/2017
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
ms.openlocfilehash: 2968641538bf0b4d0e136d5784bf69e5e7fcb3a0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298085"
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a><span data-ttu-id="6afb0-102">方法: WSDL コントラクトと共にサービス モニカーを使用する</span><span class="sxs-lookup"><span data-stu-id="6afb0-102">How to: Use a Service Moniker with WSDL Contracts</span></span>
<span data-ttu-id="6afb0-103">完全に自己完結型である COM Interop クライアントの構築が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6afb0-103">There are situations when you may want to have a completely self-contained COM Interop client.</span></span> <span data-ttu-id="6afb0-104">呼び出そうとするサービスで MEX エンドポイントが公開されておらず、WCF クライアントの DLL が COM interop に登録されていないこともあります。</span><span class="sxs-lookup"><span data-stu-id="6afb0-104">The service you want to call may not expose a MEX endpoint, and the WCF client DLL may not be registered for COM interop.</span></span> <span data-ttu-id="6afb0-105">このような場合、サービスを記述した WSDL ファイルを作成し、そのファイルを WCF サービス モニカーに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="6afb0-105">In these cases, you can create a WSDL file that describes the service and pass it into the WCF service moniker.</span></span> <span data-ttu-id="6afb0-106">ここでは、WCF WSDL モニカーを使用して、WCF の入門サンプルを呼び出す方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-106">This topic describes how to call the Getting Started WCF sample using a WCF WSDL moniker.</span></span>  
  
### <a name="using-the-wsdl-service-moniker"></a><span data-ttu-id="6afb0-107">WSDL サービス モニカーの使用</span><span class="sxs-lookup"><span data-stu-id="6afb0-107">Using the WSDL service moniker</span></span>  
  
1. <span data-ttu-id="6afb0-108">入門サンプル ソリューションを開き、ビルドします。</span><span class="sxs-lookup"><span data-stu-id="6afb0-108">Open and build the GettingStarted sample solution.</span></span>  
  
2. <span data-ttu-id="6afb0-109">Internet Explorer を開きを参照する`http://localhost/ServiceModelSamples/Service.svc`サービスが動作しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-109">Open Internet Explorer and browse to `http://localhost/ServiceModelSamples/Service.svc` to make sure that the service is working.</span></span>  
  
3. <span data-ttu-id="6afb0-110">Service.cs ファイルで、次の属性を CalculatorService クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-110">In the Service.cs file, add the following attribute on the CalculatorService class:</span></span>  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4. <span data-ttu-id="6afb0-111">バインディング名前空間をサービスの App.config に追加します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-111">Add a binding namespace to the service App.config:</span></span>  

5. <span data-ttu-id="6afb0-112">アプリケーションが読み取る WSDL ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-112">Create a WSDL file for the application to read.</span></span> <span data-ttu-id="6afb0-113">参照して、サービスの WSDL 記述全体を照会する IE を使用するには、名前空間は、手順 3 と 4 で追加された、ため、`http://localhost/ServiceModelSamples/Service.svc?wsdl`します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-113">Because the namespaces were added in steps 3 and 4, you can use IE to query for the entire WSDL description of the service by browsing to `http://localhost/ServiceModelSamples/Service.svc?wsdl`.</span></span> <span data-ttu-id="6afb0-114">次に、そのファイルをサービスの WSDL.xml として Internet Explorer で保存できます。</span><span class="sxs-lookup"><span data-stu-id="6afb0-114">You can then save the file from Internet Explorer as serviceWSDL.xml.</span></span> <span data-ttu-id="6afb0-115">手順 3. と 4. で名前空間を指定しなかった場合、上記の URL を照会したときに返される WSDL ドキュメントは、完全な WSDL ではありません。</span><span class="sxs-lookup"><span data-stu-id="6afb0-115">If you do not specify the namespaces in steps 3 and 4, the WSDL document returned from querying the above URL will not be the complete WSDL.</span></span> <span data-ttu-id="6afb0-116">返される WSDL ドキュメントには、他の WSDL ドキュメントをインポートするためのインポート ステートメントが追加されています。</span><span class="sxs-lookup"><span data-stu-id="6afb0-116">The WSDL document returned will include several import statements that import other WSDL documents.</span></span> <span data-ttu-id="6afb0-117">各インポート ステートメントを実行し、サービスから返された WSDL とインポートした WSDL を組み合わせることによって、完全な WSDL ドキュメントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6afb0-117">You will have to go through each import statement and build the complete WSDL document, combining the WSDL returned from the service with the WSDL imported.</span></span>  
  
6. <span data-ttu-id="6afb0-118">Visual Basic 6.0 を開き、新しい標準 .exe ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-118">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="6afb0-119">フォームにボタンを追加し、追加したボタンをダブルクリックして次のコードをクリック ハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-119">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```  
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    >  モニカーの形式が正しくないか、`GetObject` を呼び出せない場合は、"構文が無効です" というメッセージが返されます。  <span data-ttu-id="6afb0-121">このエラーが発生した場合は、使用しているモニカーが正しく、サービスが使用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6afb0-121">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
7. <span data-ttu-id="6afb0-122">Visual Basic アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6afb0-122">Run the Visual Basic application.</span></span> <span data-ttu-id="6afb0-123">メッセージ ボックスに、Subtract(145, 76.54) を呼び出した結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6afb0-123">A message box will be displayed with the results of calling Subtract(145, 76.54).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6afb0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6afb0-124">See also</span></span>

- [<span data-ttu-id="6afb0-125">作業の開始</span><span class="sxs-lookup"><span data-stu-id="6afb0-125">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="6afb0-126">COM アプリケーションとの統合の概要</span><span class="sxs-lookup"><span data-stu-id="6afb0-126">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
