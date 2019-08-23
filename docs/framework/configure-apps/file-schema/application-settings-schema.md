---
title: アプリケーション設定スキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927761"
---
# <a name="application-settings-schema"></a><span data-ttu-id="93cdc-102">アプリケーション設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="93cdc-102">Application Settings schema</span></span>

<span data-ttu-id="93cdc-103">アプリケーション設定を使用すると、Windows フォームまたは ASP.NET アプリケーションで、アプリケーションスコープの設定とユーザースコープの設定を格納および取得できます。</span><span class="sxs-lookup"><span data-stu-id="93cdc-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="93cdc-104">このコンテキストでは、*設定*は、アプリケーションに固有の情報、または現在のユーザーに固有の情報です。データベース接続文字列からユーザーの優先される既定のウィンドウサイズに至るまでのあらゆるものです。</span><span class="sxs-lookup"><span data-stu-id="93cdc-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="93cdc-105">既定では、Windows フォームアプリケーションのアプリケーション設定は<xref:System.Configuration.LocalFileSettingsProvider>クラスを使用します。このクラスは、.net 構成システムを使用して XML 構成ファイルに設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="93cdc-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="93cdc-106">アプリケーション設定で使用されるファイルの詳細については、「[アプリケーション設定アーキテクチャ](../../winforms/advanced/application-settings-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93cdc-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="93cdc-107">アプリケーション設定は、使用する構成ファイルの一部として、次の要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="93cdc-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="93cdc-108">要素</span><span class="sxs-lookup"><span data-stu-id="93cdc-108">Element</span></span>                    | <span data-ttu-id="93cdc-109">説明</span><span class="sxs-lookup"><span data-stu-id="93cdc-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="93cdc-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="93cdc-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="93cdc-111">**\<applicationSettings>\< すべてを含む** \<setting> アプリケーションに固有のタグ</span><span class="sxs-lookup"><span data-stu-id="93cdc-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="93cdc-112">**\<userSettings >**</span><span class="sxs-lookup"><span data-stu-id="93cdc-112">**\<userSettings>**</span></span>        | <span data-ttu-id="93cdc-113">**\<userSettings>\<  すべてが含まれます** \<setting> タグは、現在のユーザーを特定します</span><span class="sxs-lookup"><span data-stu-id="93cdc-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="93cdc-114">**\<setting>**</span><span class="sxs-lookup"><span data-stu-id="93cdc-114">**\<setting>**</span></span>             | <span data-ttu-id="93cdc-115">設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="93cdc-115">Defines a setting.</span></span> <span data-ttu-id="93cdc-116">いずれかの子 **\<applicationSettings >** または **\<userSettings>** します。</span><span class="sxs-lookup"><span data-stu-id="93cdc-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="93cdc-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="93cdc-117">**\<value>**</span></span>               | <span data-ttu-id="93cdc-118">設定の値を定義します。</span><span class="sxs-lookup"><span data-stu-id="93cdc-118">Defines a setting's value.</span></span> <span data-ttu-id="93cdc-119">設定の値を定義します。 子 **\<setting>** します。</span><span class="sxs-lookup"><span data-stu-id="93cdc-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="93cdc-120">\<applicationSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="93cdc-120">\<applicationSettings> element</span></span>

<span data-ttu-id="93cdc-121">この要素には、すべてが含まれています **\<setting>** クライアント コンピューターにアプリケーションのインスタンスに固有のタグ</span><span class="sxs-lookup"><span data-stu-id="93cdc-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="93cdc-122">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="93cdc-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="93cdc-123">\<userSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="93cdc-123">\<userSettings> element</span></span>

<span data-ttu-id="93cdc-124">この要素には、すべてが含まれています **\<設定>** アプリケーションが現在使用してユーザーに固有のタグ。</span><span class="sxs-lookup"><span data-stu-id="93cdc-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="93cdc-125">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="93cdc-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="93cdc-126">\<setting> 要素</span><span class="sxs-lookup"><span data-stu-id="93cdc-126">\<setting> element</span></span>

<span data-ttu-id="93cdc-127">この要素は、設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="93cdc-127">This element defines a setting.</span></span> <span data-ttu-id="93cdc-128">これには次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="93cdc-128">It has the following attributes.</span></span>

| <span data-ttu-id="93cdc-129">属性</span><span class="sxs-lookup"><span data-stu-id="93cdc-129">Attribute</span></span>        | <span data-ttu-id="93cdc-130">説明</span><span class="sxs-lookup"><span data-stu-id="93cdc-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="93cdc-131">**name**</span><span class="sxs-lookup"><span data-stu-id="93cdc-131">**name**</span></span>         | <span data-ttu-id="93cdc-132">必須。</span><span class="sxs-lookup"><span data-stu-id="93cdc-132">Required.</span></span> <span data-ttu-id="93cdc-133">設定の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="93cdc-133">The unique ID of the setting.</span></span> <span data-ttu-id="93cdc-134">Visual Studio で作成された設定は、 `ProjectName.Properties.Settings`という名前で保存されます。</span><span class="sxs-lookup"><span data-stu-id="93cdc-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="93cdc-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="93cdc-135">**serializedAs**</span></span> | <span data-ttu-id="93cdc-136">必須。</span><span class="sxs-lookup"><span data-stu-id="93cdc-136">Required.</span></span> <span data-ttu-id="93cdc-137">値をテキストにシリアル化するために使用する形式。</span><span class="sxs-lookup"><span data-stu-id="93cdc-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="93cdc-138">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="93cdc-138">Valid values are:</span></span><br><br><span data-ttu-id="93cdc-139">- `string`。</span><span class="sxs-lookup"><span data-stu-id="93cdc-139">- `string`.</span></span> <span data-ttu-id="93cdc-140">値は、を<xref:System.ComponentModel.TypeConverter>使用して文字列としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="93cdc-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="93cdc-141">- `xml`。</span><span class="sxs-lookup"><span data-stu-id="93cdc-141">- `xml`.</span></span> <span data-ttu-id="93cdc-142">値は、XML シリアル化を使用してシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="93cdc-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="93cdc-143">- `binary`。</span><span class="sxs-lookup"><span data-stu-id="93cdc-143">- `binary`.</span></span> <span data-ttu-id="93cdc-144">この値は、バイナリシリアル化を使用して、テキストエンコードバイナリとしてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="93cdc-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="93cdc-145">- `custom`。</span><span class="sxs-lookup"><span data-stu-id="93cdc-145">- `custom`.</span></span> <span data-ttu-id="93cdc-146">設定プロバイダーは、この設定に固有の情報を持ち、シリアル化および逆シリアル化を行います。</span><span class="sxs-lookup"><span data-stu-id="93cdc-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="93cdc-147">\<value> 要素</span><span class="sxs-lookup"><span data-stu-id="93cdc-147">\<value> element</span></span>

<span data-ttu-id="93cdc-148">この要素には、設定の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="93cdc-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="93cdc-149">例</span><span class="sxs-lookup"><span data-stu-id="93cdc-149">Example</span></span>

<span data-ttu-id="93cdc-150">次の例は、2つのアプリケーションスコープ設定と2つのユーザースコープ設定を定義するアプリケーション設定ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="93cdc-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="93cdc-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="93cdc-151">See also</span></span>

- [<span data-ttu-id="93cdc-152">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="93cdc-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="93cdc-153">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="93cdc-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
