---
title: '方法: C# のアプリケーションに複数の設定セットを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 106e0ee0b8775f329f3ffd8babe458cac8492bd5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187383"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="6d12d-102">方法: C 言語でアプリケーションに複数の設定セットを追加します。\#</span><span class="sxs-lookup"><span data-stu-id="6d12d-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>
<span data-ttu-id="6d12d-103">場合によっては、アプリケーションで複数の設定のセットがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d12d-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="6d12d-104">たとえば、アプリケーションを開発し、頻繁に変更する設定の特定のグループが必要な場合は場合があります、ファイルごとに、置換できるように、すべて 1 つのファイルにそれらを分離するその他の設定の影響を受けていません。</span><span class="sxs-lookup"><span data-stu-id="6d12d-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="6d12d-105">Visual Studio プロジェクトに複数の設定セットを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6d12d-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="6d12d-106">設定の追加セットは、Properties.Settings オブジェクトを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6d12d-106">Additional sets of settings can be accessed via the Properties.Settings object.</span></span>  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a><span data-ttu-id="6d12d-107">アプリケーションに追加の設定セットを追加するには</span><span class="sxs-lookup"><span data-stu-id="6d12d-107">To Add an Additional Set of Setting to your Application</span></span>  
  
1.  <span data-ttu-id="6d12d-108">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d12d-108">From the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="6d12d-109">**[新しい項目の追加]** ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="6d12d-109">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="6d12d-110">**新しい項目の追加**ダイアログ ボックスで、**設定ファイル**ファイルの名前を入力し、をクリックして、**追加**をソリューションに新しい設定ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d12d-110">In the **Add New Item** dialog box, select **Settings File**, type in a name for the file, and click **Add** to add a new settings file to your solution.</span></span>  
  
3.  <span data-ttu-id="6d12d-111">**ソリューション エクスプ ローラー**に、新しい設定ファイルをドラッグして、**プロパティ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="6d12d-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="6d12d-112">これにより、コードで使用できる新しい設定ができます。</span><span class="sxs-lookup"><span data-stu-id="6d12d-112">This allows your new settings to be available in code.</span></span>  
  
4.  <span data-ttu-id="6d12d-113">追加し、他の設定ファイルと同様に、このファイルの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d12d-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="6d12d-114">この Properties.Settings オブジェクトを使用して設定のグループにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6d12d-114">You can access this group of settings via the Properties.Settings object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d12d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d12d-115">See also</span></span>

- [<span data-ttu-id="6d12d-116">アプリケーション設定とユーザー設定の使用</span><span class="sxs-lookup"><span data-stu-id="6d12d-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="6d12d-117">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="6d12d-117">Application Settings Overview</span></span>](application-settings-overview.md)
