---
title: アプリケーション設定のスキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: a74716bcdf3c85c08d0ff3bf66407dce30ee91cc
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083471"
---
# <a name="application-settings-schema"></a><span data-ttu-id="a4f10-102">アプリケーション設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="a4f10-102">Application Settings schema</span></span>

<span data-ttu-id="a4f10-103">アプリケーションの設定は、格納およびアプリケーション スコープし、ユーザー スコープの設定を取得する Windows フォームや ASP.NET アプリケーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="a4f10-104">このコンテキストで、*設定*任意のアプリケーションに固有または現在のユーザーに特定できる情報は、-、ユーザーにデータベース接続文字列から何かの既定のウィンドウ サイズを優先します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="a4f10-105">既定では、Windows フォーム アプリケーションでアプリケーションの設定を使用して、<xref:System.Configuration.LocalFileSettingsProvider>クラスは、XML 構成ファイルで設定を格納する、.NET 構成システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="a4f10-106">アプリケーションの設定で使用されるファイルの詳細については、次を参照してください。[アプリケーション設定アーキテクチャ](~/docs/framework/winforms/advanced/application-settings-architecture.md)します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="a4f10-107">アプリケーションの設定は、使用して、構成ファイルの一部として、次の要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="a4f10-108">要素</span><span class="sxs-lookup"><span data-stu-id="a4f10-108">Element</span></span>                    | <span data-ttu-id="a4f10-109">説明</span><span class="sxs-lookup"><span data-stu-id="a4f10-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="a4f10-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="a4f10-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="a4f10-111">すべてを含む**\<設定 >** アプリケーションに固有のタグ。</span><span class="sxs-lookup"><span data-stu-id="a4f10-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="a4f10-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="a4f10-112">**\<userSettings>**</span></span>        | <span data-ttu-id="a4f10-113">すべてが含まれます**\<設定 >** タグは、現在のユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="a4f10-114">**\<setting>**</span><span class="sxs-lookup"><span data-stu-id="a4f10-114">**\<setting>**</span></span>             | <span data-ttu-id="a4f10-115">設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-115">Defines a setting.</span></span> <span data-ttu-id="a4f10-116">いずれかの子 **\<applicationSettings >** または **\<userSettings>** します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="a4f10-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="a4f10-117">**\<value>**</span></span>               | <span data-ttu-id="a4f10-118">設定の値を定義します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-118">Defines a setting's value.</span></span> <span data-ttu-id="a4f10-119">子**\<設定 >** します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="a4f10-120">\<applicationSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="a4f10-120">\<applicationSettings> element</span></span>

<span data-ttu-id="a4f10-121">この要素には、すべてが含まれています**\<設定 >** クライアント コンピューターにアプリケーションのインスタンスに固有のタグ。</span><span class="sxs-lookup"><span data-stu-id="a4f10-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="a4f10-122">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="a4f10-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="a4f10-123">\<userSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="a4f10-123">\<userSettings> element</span></span>

<span data-ttu-id="a4f10-124">この要素には、すべてが含まれています**\<設定>** アプリケーションが現在使用してユーザーに固有のタグ。</span><span class="sxs-lookup"><span data-stu-id="a4f10-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="a4f10-125">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="a4f10-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="a4f10-126">\<setting> 要素</span><span class="sxs-lookup"><span data-stu-id="a4f10-126">\<setting> element</span></span>

<span data-ttu-id="a4f10-127">この要素は、設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-127">This element defines a setting.</span></span> <span data-ttu-id="a4f10-128">次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="a4f10-128">It has the following attributes.</span></span>

| <span data-ttu-id="a4f10-129">属性</span><span class="sxs-lookup"><span data-stu-id="a4f10-129">Attribute</span></span>        | <span data-ttu-id="a4f10-130">説明</span><span class="sxs-lookup"><span data-stu-id="a4f10-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="a4f10-131">**name**</span><span class="sxs-lookup"><span data-stu-id="a4f10-131">**name**</span></span>         | <span data-ttu-id="a4f10-132">必須。</span><span class="sxs-lookup"><span data-stu-id="a4f10-132">Required.</span></span> <span data-ttu-id="a4f10-133">設定の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a4f10-133">The unique ID of the setting.</span></span> <span data-ttu-id="a4f10-134">Visual Studio で作成した設定は、名前で保存は`ProjectName.Properties.Settings`します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="a4f10-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="a4f10-135">**serializedAs**</span></span> | <span data-ttu-id="a4f10-136">必須。</span><span class="sxs-lookup"><span data-stu-id="a4f10-136">Required.</span></span> <span data-ttu-id="a4f10-137">テキスト値をシリアル化するために使用する形式。</span><span class="sxs-lookup"><span data-stu-id="a4f10-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="a4f10-138">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4f10-138">Valid values are:</span></span><br><br><span data-ttu-id="a4f10-139">- `string`。</span><span class="sxs-lookup"><span data-stu-id="a4f10-139">- `string`.</span></span> <span data-ttu-id="a4f10-140">使用して文字列として値をシリアル化、<xref:System.ComponentModel.TypeConverter>します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="a4f10-141">- `xml`。</span><span class="sxs-lookup"><span data-stu-id="a4f10-141">- `xml`.</span></span> <span data-ttu-id="a4f10-142">値は、XML シリアル化を使用してシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a4f10-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="a4f10-143">- `binary`。</span><span class="sxs-lookup"><span data-stu-id="a4f10-143">- `binary`.</span></span> <span data-ttu-id="a4f10-144">値は、バイナリ シリアル化を使用して、テキスト エンコードされたバイナリとしてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="a4f10-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="a4f10-145">- `custom`。</span><span class="sxs-lookup"><span data-stu-id="a4f10-145">- `custom`.</span></span> <span data-ttu-id="a4f10-146">設定プロバイダーは、この設定の固有の情報しシリアル化し、逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="a4f10-147">\<value> 要素</span><span class="sxs-lookup"><span data-stu-id="a4f10-147">\<value> element</span></span>

<span data-ttu-id="a4f10-148">この要素には、設定の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a4f10-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="a4f10-149">例</span><span class="sxs-lookup"><span data-stu-id="a4f10-149">Example</span></span>

<span data-ttu-id="a4f10-150">次の例では、2 つのアプリケーション スコープ設定と 2 つのユーザー スコープ設定を定義するアプリケーション設定ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="a4f10-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a4f10-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4f10-151">See also</span></span>

- [<span data-ttu-id="a4f10-152">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="a4f10-152">Application Settings Overview</span></span>](~/docs/framework/winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="a4f10-153">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a4f10-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
