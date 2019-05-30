---
title: <section> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 64556054df2689ff758f52c7e98556997a3e9d3d
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301184"
---
# <a name="section-element"></a><span data-ttu-id="0b295-102">\<セクション > 要素</span><span class="sxs-lookup"><span data-stu-id="0b295-102">\<section> element</span></span>

<span data-ttu-id="0b295-103">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b295-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="0b295-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0b295-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0b295-105">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0b295-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0b295-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<section>**</span><span class="sxs-lookup"><span data-stu-id="0b295-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="0b295-107">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0b295-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0b295-108">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0b295-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0b295-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup>** ](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="0b295-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="0b295-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<section>**</span><span class="sxs-lookup"><span data-stu-id="0b295-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0b295-111">構文</span><span class="sxs-lookup"><span data-stu-id="0b295-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="0b295-112">必要な属性</span><span class="sxs-lookup"><span data-stu-id="0b295-112">Required attributes</span></span>

|           | <span data-ttu-id="0b295-113">説明</span><span class="sxs-lookup"><span data-stu-id="0b295-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0b295-114">**name**</span><span class="sxs-lookup"><span data-stu-id="0b295-114">**name**</span></span>  | <span data-ttu-id="0b295-115">構成セクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b295-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="0b295-116">**type**</span><span class="sxs-lookup"><span data-stu-id="0b295-116">**type**</span></span>  | <span data-ttu-id="0b295-117">構成ファイルからセクションを読み取る構成セクション ハンドラー クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b295-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="0b295-118">型の値には、構文"fully-qualified-section-handler-class-name、単純なアセンブリ名"があります。</span><span class="sxs-lookup"><span data-stu-id="0b295-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="0b295-119">単純なアセンブリ名がなく、ルート ファイル名、 *.dll*ファイル拡張子。</span><span class="sxs-lookup"><span data-stu-id="0b295-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="0b295-120">省略可能な属性</span><span class="sxs-lookup"><span data-stu-id="0b295-120">Optional attributes</span></span>

<span data-ttu-id="0b295-121">次の属性は、ASP.NET アプリケーションでのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b295-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="0b295-122">構成システムは、その他のアプリケーションの種類に対してこれらの属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="0b295-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="0b295-123">説明</span><span class="sxs-lookup"><span data-stu-id="0b295-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="0b295-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="0b295-124">**allowDefinition**</span></span> | <span data-ttu-id="0b295-125">セクションで使用できる構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0b295-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="0b295-126">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b295-126">Use one of the following values:</span></span><br><br><span data-ttu-id="0b295-127">**すべての場所**</span><span class="sxs-lookup"><span data-stu-id="0b295-127">**Everywhere**</span></span><br><span data-ttu-id="0b295-128">すべての構成ファイルで使用するセクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b295-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="0b295-129">既定値です。</span><span class="sxs-lookup"><span data-stu-id="0b295-129">This is the default.</span></span><br><span data-ttu-id="0b295-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="0b295-130">**MachineOnly**</span></span><br><span data-ttu-id="0b295-131">セクションは、マシン構成ファイルでのみ使用 (*Machine.config*)。</span><span class="sxs-lookup"><span data-stu-id="0b295-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="0b295-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="0b295-132">**MachineToApplication**</span></span><br><span data-ttu-id="0b295-133">マシン構成ファイルまたはアプリケーション構成ファイルで使用するセクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b295-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="0b295-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="0b295-134">**allowLocation**</span></span>   | <span data-ttu-id="0b295-135">セクション内で使用できるかどうかを決定、 **\<場所 >** 要素。</span><span class="sxs-lookup"><span data-stu-id="0b295-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="0b295-136">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b295-136">Use one of the following values:</span></span><br><br><span data-ttu-id="0b295-137">**true**</span><span class="sxs-lookup"><span data-stu-id="0b295-137">**true**</span></span><br><span data-ttu-id="0b295-138">セクション内で使用される、 **\<場所 >** 要素。</span><span class="sxs-lookup"><span data-stu-id="0b295-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="0b295-139">既定値です。</span><span class="sxs-lookup"><span data-stu-id="0b295-139">This is the default.</span></span><br><span data-ttu-id="0b295-140">**false**</span><span class="sxs-lookup"><span data-stu-id="0b295-140">**false**</span></span><br><span data-ttu-id="0b295-141">セクション内で使用することはできません、 **\<場所 >** 要素。</span><span class="sxs-lookup"><span data-stu-id="0b295-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="0b295-142">親要素</span><span class="sxs-lookup"><span data-stu-id="0b295-142">Parent elements</span></span>

|     | <span data-ttu-id="0b295-143">説明</span><span class="sxs-lookup"><span data-stu-id="0b295-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0b295-144"> *\*\<configSections >** 要素</span><span class="sxs-lookup"><span data-stu-id="0b295-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="0b295-145">構成セクションと名前空間宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b295-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="0b295-146"> *\*\<sectionGroup >** 要素</span><span class="sxs-lookup"><span data-stu-id="0b295-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="0b295-147">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="0b295-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="0b295-148">A **\<セクション >** 要素は、いずれかの子要素 **\<configSections >** または **\<sectionGroup >** がありません両方とも。</span><span class="sxs-lookup"><span data-stu-id="0b295-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="0b295-149">子要素</span><span class="sxs-lookup"><span data-stu-id="0b295-149">Child elements</span></span>

<span data-ttu-id="0b295-150">なし</span><span class="sxs-lookup"><span data-stu-id="0b295-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0b295-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="0b295-151">Remarks</span></span>

<span data-ttu-id="0b295-152">基本的に、構成セクションを宣言するには、構成ファイルの新しい要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="0b295-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="0b295-153">新しい要素には、セクション ハンドラーを構成する設定が含まれています (実装するクラスは、<xref:System.Configuration.IConfigurationSectionHandler>インターフェイス) を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="0b295-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="0b295-154">属性と子要素を定義するセクションの設定の読み取りに使用するセクション ハンドラーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0b295-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="0b295-155">構成セクション ハンドラーを宣言する、 *Machine.config*ファイル使用すると、そのコンピューターで、アプリケーション構成ファイルで構成セクションを使用しない限り、**仮想ディレクトリ**属性がそれ以外の場合を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b295-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="0b295-156">例</span><span class="sxs-lookup"><span data-stu-id="0b295-156">Example</span></span>

<span data-ttu-id="0b295-157">次の例では、構成セクションを定義し、そのセクションの設定を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0b295-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="0b295-158">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0b295-158">Configuration file</span></span>

<span data-ttu-id="0b295-159">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="0b295-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b295-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b295-160">See also</span></span>

- [<span data-ttu-id="0b295-161">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="0b295-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
