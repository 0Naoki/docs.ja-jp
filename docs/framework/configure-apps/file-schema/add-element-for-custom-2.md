---
title: <add> NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9b421b4bab32c1aae7a6ba7d69b9f4aea2ab99a5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278279"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ef35d-102">\<追加 > NameValueSectionHandler および DictionarySectionHandler の要素</span><span class="sxs-lookup"><span data-stu-id="ef35d-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ef35d-103">カスタム アプリケーションの設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="ef35d-103">Adds custom application settings.</span></span> <span data-ttu-id="ef35d-104">各**\<追加 >** タグにはキー/値ペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef35d-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="ef35d-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ef35d-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ef35d-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="ef35d-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="ef35d-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span><span class="sxs-lookup"><span data-stu-id="ef35d-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ef35d-108">構文</span><span class="sxs-lookup"><span data-stu-id="ef35d-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="ef35d-109">属性</span><span class="sxs-lookup"><span data-stu-id="ef35d-109">Attributes</span></span>

| <span data-ttu-id="ef35d-110">属性</span><span class="sxs-lookup"><span data-stu-id="ef35d-110">Attribute</span></span> | <span data-ttu-id="ef35d-111">説明</span><span class="sxs-lookup"><span data-stu-id="ef35d-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ef35d-112">**key**</span><span class="sxs-lookup"><span data-stu-id="ef35d-112">**key**</span></span>   | <span data-ttu-id="ef35d-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ef35d-113">Required attribute.</span></span><br><br><span data-ttu-id="ef35d-114">設定の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef35d-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="ef35d-115">**value**</span><span class="sxs-lookup"><span data-stu-id="ef35d-115">**value**</span></span> | <span data-ttu-id="ef35d-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ef35d-116">Required attribute.</span></span><br><br><span data-ttu-id="ef35d-117">設定の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef35d-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ef35d-118">親要素</span><span class="sxs-lookup"><span data-stu-id="ef35d-118">Parent element</span></span>

| <span data-ttu-id="ef35d-119">要素</span><span class="sxs-lookup"><span data-stu-id="ef35d-119">Element</span></span> | <span data-ttu-id="ef35d-120">説明</span><span class="sxs-lookup"><span data-stu-id="ef35d-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="ef35d-121">**\<sectionName >** 要素</span><span class="sxs-lookup"><span data-stu-id="ef35d-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="ef35d-122">使用して、カスタム構成セクションの設定を定義、<xref:System.Configuration.NameValueSectionHandler>と<xref:System.Configuration.DictionarySectionHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="ef35d-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ef35d-123">子要素</span><span class="sxs-lookup"><span data-stu-id="ef35d-123">Child elements</span></span>

<span data-ttu-id="ef35d-124">なし</span><span class="sxs-lookup"><span data-stu-id="ef35d-124">None</span></span>

## <a name="example"></a><span data-ttu-id="ef35d-125">例</span><span class="sxs-lookup"><span data-stu-id="ef35d-125">Example</span></span>

<span data-ttu-id="ef35d-126">次の例では、カスタム構成セクションを定義して使用する方法を示しています、 **\<追加 >** セクションに設定を格納する要素。</span><span class="sxs-lookup"><span data-stu-id="ef35d-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ef35d-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="ef35d-127">Configuration file</span></span>

<span data-ttu-id="ef35d-128">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="ef35d-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef35d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef35d-129">See also</span></span>

- [<span data-ttu-id="ef35d-130">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="ef35d-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
