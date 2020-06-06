---
title: アプリケーション設定スキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "81242830"
---
# <a name="application-settings-schema"></a><span data-ttu-id="e3ecd-102">アプリケーション設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="e3ecd-102">Application Settings schema</span></span>

<span data-ttu-id="e3ecd-103">アプリケーション設定を使用すると、Windows フォームまたは ASP.NET アプリケーションで、アプリケーションスコープの設定とユーザースコープの設定を格納および取得できます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="e3ecd-104">このコンテキストでは、*設定*は、アプリケーションに固有の情報、または現在のユーザーに固有の情報です。データベース接続文字列からユーザーの優先される既定のウィンドウサイズに至るまでのあらゆるものです。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="e3ecd-105">既定では、Windows フォームアプリケーションのアプリケーション設定はクラスを使用します。このクラスは、 <xref:System.Configuration.LocalFileSettingsProvider> .net 構成システムを使用して XML 構成ファイルに設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="e3ecd-106">アプリケーション設定で使用されるファイルの詳細については、「[アプリケーション設定アーキテクチャ](../../winforms/advanced/application-settings-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="e3ecd-107">アプリケーション設定は、使用する構成ファイルの一部として、次の要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="e3ecd-108">要素</span><span class="sxs-lookup"><span data-stu-id="e3ecd-108">Element</span></span>                    | <span data-ttu-id="e3ecd-109">Description</span><span class="sxs-lookup"><span data-stu-id="e3ecd-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | <span data-ttu-id="e3ecd-110">**\<setting>** アプリケーションに固有のすべてのタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-110">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| **\<userSettings>**        | <span data-ttu-id="e3ecd-111">**\<setting>** 現在のユーザーに固有のすべてのタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-111">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| **\<setting>**             | <span data-ttu-id="e3ecd-112">設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-112">Defines a setting.</span></span> <span data-ttu-id="e3ecd-113">**\<applicationSettings>** またはの子 **\<userSettings>** 。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-113">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| **\<value>**               | <span data-ttu-id="e3ecd-114">設定の値を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-114">Defines a setting's value.</span></span> <span data-ttu-id="e3ecd-115">の子 **\<setting>** 。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-115">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="e3ecd-116">\<applicationSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="e3ecd-116">\<applicationSettings> element</span></span>

<span data-ttu-id="e3ecd-117">この要素に **\<setting>** は、クライアントコンピューター上のアプリケーションのインスタンスに固有のすべてのタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-117">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="e3ecd-118">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-118">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="e3ecd-119">\<userSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="e3ecd-119">\<userSettings> element</span></span>

<span data-ttu-id="e3ecd-120">この要素 **\<setting>** には、アプリケーションを現在使用しているユーザーに固有のすべてのタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-120">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="e3ecd-121">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-121">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="e3ecd-122">\<setting> 要素</span><span class="sxs-lookup"><span data-stu-id="e3ecd-122">\<setting> element</span></span>

<span data-ttu-id="e3ecd-123">この要素は、設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-123">This element defines a setting.</span></span> <span data-ttu-id="e3ecd-124">これには次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-124">It has the following attributes.</span></span>

| <span data-ttu-id="e3ecd-125">属性</span><span class="sxs-lookup"><span data-stu-id="e3ecd-125">Attribute</span></span>        | <span data-ttu-id="e3ecd-126">説明</span><span class="sxs-lookup"><span data-stu-id="e3ecd-126">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="e3ecd-127">**name**</span><span class="sxs-lookup"><span data-stu-id="e3ecd-127">**name**</span></span>         | <span data-ttu-id="e3ecd-128">必須。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-128">Required.</span></span> <span data-ttu-id="e3ecd-129">設定の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-129">The unique ID of the setting.</span></span> <span data-ttu-id="e3ecd-130">Visual Studio で作成された設定は、という名前で保存され `ProjectName.Properties.Settings` ます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-130">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="e3ecd-131">**serializeAs**</span><span class="sxs-lookup"><span data-stu-id="e3ecd-131">**serializeAs**</span></span> | <span data-ttu-id="e3ecd-132">必須。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-132">Required.</span></span> <span data-ttu-id="e3ecd-133">値をテキストにシリアル化するために使用する形式。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-133">The format to use for serializing the value to text.</span></span> <span data-ttu-id="e3ecd-134">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-134">Valid values are:</span></span><br><br><span data-ttu-id="e3ecd-135">- `string`.</span><span class="sxs-lookup"><span data-stu-id="e3ecd-135">- `string`.</span></span> <span data-ttu-id="e3ecd-136">値は、を使用して文字列としてシリアル化され <xref:System.ComponentModel.TypeConverter> ます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-136">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="e3ecd-137">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="e3ecd-137">- `xml`.</span></span> <span data-ttu-id="e3ecd-138">値は、XML シリアル化を使用してシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-138">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="e3ecd-139">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="e3ecd-139">- `binary`.</span></span> <span data-ttu-id="e3ecd-140">この値は、バイナリシリアル化を使用して、テキストエンコードバイナリとしてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-140">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="e3ecd-141">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="e3ecd-141">- `custom`.</span></span> <span data-ttu-id="e3ecd-142">設定プロバイダーは、この設定に固有の情報を持ち、シリアル化および逆シリアル化を行います。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-142">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="e3ecd-143">\<value> 要素</span><span class="sxs-lookup"><span data-stu-id="e3ecd-143">\<value> element</span></span>

<span data-ttu-id="e3ecd-144">この要素には、設定の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-144">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="e3ecd-145">例</span><span class="sxs-lookup"><span data-stu-id="e3ecd-145">Example</span></span>

<span data-ttu-id="e3ecd-146">次の例は、2つのアプリケーションスコープ設定と2つのユーザースコープ設定を定義するアプリケーション設定ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3ecd-146">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e3ecd-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3ecd-147">See also</span></span>

- [<span data-ttu-id="e3ecd-148">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="e3ecd-148">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="e3ecd-149">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e3ecd-149">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
