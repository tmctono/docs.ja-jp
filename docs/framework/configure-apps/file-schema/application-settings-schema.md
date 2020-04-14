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
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242830"
---
# <a name="application-settings-schema"></a><span data-ttu-id="d33c2-102">アプリケーション設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d33c2-102">Application Settings schema</span></span>

<span data-ttu-id="d33c2-103">アプリケーション設定を使用すると、Windows フォームまたはASP.NET アプリケーションは、アプリケーション スコープおよびユーザー スコープの設定を格納および取得できます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="d33c2-104">このコンテキストでは、*設定*は、アプリケーションに固有の情報、または現在のユーザーに固有の情報の一部です。</span><span class="sxs-lookup"><span data-stu-id="d33c2-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="d33c2-105">既定では、Windows フォーム アプリケーションのアプリケーション設定では<xref:System.Configuration.LocalFileSettingsProvider>、.NET 構成システムを使用して設定を XML 構成ファイルに格納するクラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="d33c2-106">アプリケーション設定で使用されるファイルの詳細については、「[アプリケーション設定のアーキテクチャ](../../winforms/advanced/application-settings-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d33c2-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="d33c2-107">アプリケーション設定では、使用する構成ファイルの一部として、次の要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="d33c2-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="d33c2-108">要素</span><span class="sxs-lookup"><span data-stu-id="d33c2-108">Element</span></span>                    | <span data-ttu-id="d33c2-109">説明</span><span class="sxs-lookup"><span data-stu-id="d33c2-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="d33c2-110">**\<アプリケーション設定>**</span><span class="sxs-lookup"><span data-stu-id="d33c2-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="d33c2-111">アプリケーションに固有のすべての**\<設定>** タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="d33c2-112">**\<ユーザー設定>**</span><span class="sxs-lookup"><span data-stu-id="d33c2-112">**\<userSettings>**</span></span>        | <span data-ttu-id="d33c2-113">現在のユーザーに固有のすべての**\<設定>** タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="d33c2-114">**\<>の設定**</span><span class="sxs-lookup"><span data-stu-id="d33c2-114">**\<setting>**</span></span>             | <span data-ttu-id="d33c2-115">設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d33c2-115">Defines a setting.</span></span> <span data-ttu-id="d33c2-116">アプリケーションの子設定>または**\<ユーザー設定>。 \*\* \*\* \<**</span><span class="sxs-lookup"><span data-stu-id="d33c2-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="d33c2-117">**\<値>**</span><span class="sxs-lookup"><span data-stu-id="d33c2-117">**\<value>**</span></span>               | <span data-ttu-id="d33c2-118">設定の値を定義します。</span><span class="sxs-lookup"><span data-stu-id="d33c2-118">Defines a setting's value.</span></span> <span data-ttu-id="d33c2-119">**\<設定>** の子。</span><span class="sxs-lookup"><span data-stu-id="d33c2-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="d33c2-120">\<アプリケーション設定>要素</span><span class="sxs-lookup"><span data-stu-id="d33c2-120">\<applicationSettings> element</span></span>

<span data-ttu-id="d33c2-121">この要素には、クライアント コンピューター**\<上のアプリケーションの**インスタンスに固有のすべての設定>タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="d33c2-122">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="d33c2-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="d33c2-123">\<ユーザー設定>要素</span><span class="sxs-lookup"><span data-stu-id="d33c2-123">\<userSettings> element</span></span>

<span data-ttu-id="d33c2-124">この要素には、現在アプリケーションを使用しているユーザーに固有のすべての**\<設定>** タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="d33c2-125">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="d33c2-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="d33c2-126">\<>要素の設定</span><span class="sxs-lookup"><span data-stu-id="d33c2-126">\<setting> element</span></span>

<span data-ttu-id="d33c2-127">この要素は、設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d33c2-127">This element defines a setting.</span></span> <span data-ttu-id="d33c2-128">この属性には、次の属性があります。</span><span class="sxs-lookup"><span data-stu-id="d33c2-128">It has the following attributes.</span></span>

| <span data-ttu-id="d33c2-129">属性</span><span class="sxs-lookup"><span data-stu-id="d33c2-129">Attribute</span></span>        | <span data-ttu-id="d33c2-130">説明</span><span class="sxs-lookup"><span data-stu-id="d33c2-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="d33c2-131">**name**</span><span class="sxs-lookup"><span data-stu-id="d33c2-131">**name**</span></span>         | <span data-ttu-id="d33c2-132">必須。</span><span class="sxs-lookup"><span data-stu-id="d33c2-132">Required.</span></span> <span data-ttu-id="d33c2-133">設定の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="d33c2-133">The unique ID of the setting.</span></span> <span data-ttu-id="d33c2-134">Visual Studio で作成された設定は、`ProjectName.Properties.Settings`という名前で保存されます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="d33c2-135">**シリアライズア**</span><span class="sxs-lookup"><span data-stu-id="d33c2-135">**serializeAs**</span></span> | <span data-ttu-id="d33c2-136">必須。</span><span class="sxs-lookup"><span data-stu-id="d33c2-136">Required.</span></span> <span data-ttu-id="d33c2-137">値をテキストにシリアル化するために使用する形式。</span><span class="sxs-lookup"><span data-stu-id="d33c2-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="d33c2-138">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d33c2-138">Valid values are:</span></span><br><br><span data-ttu-id="d33c2-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="d33c2-139">- `string`.</span></span> <span data-ttu-id="d33c2-140">値は、<xref:System.ComponentModel.TypeConverter>を使用して文字列としてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="d33c2-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="d33c2-141">- `xml`.</span></span> <span data-ttu-id="d33c2-142">値は、XML シリアル化を使用してシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="d33c2-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="d33c2-143">- `binary`.</span></span> <span data-ttu-id="d33c2-144">値は、バイナリ シリアル化を使用してテキスト エンコードされたバイナリとしてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="d33c2-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="d33c2-145">- `custom`.</span></span> <span data-ttu-id="d33c2-146">設定プロバイダーには、この設定に関する固有の知識があり、シリアル化と逆シリアル化を行います。</span><span class="sxs-lookup"><span data-stu-id="d33c2-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="d33c2-147">\<要素>値</span><span class="sxs-lookup"><span data-stu-id="d33c2-147">\<value> element</span></span>

<span data-ttu-id="d33c2-148">この要素には、設定の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d33c2-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="d33c2-149">例</span><span class="sxs-lookup"><span data-stu-id="d33c2-149">Example</span></span>

<span data-ttu-id="d33c2-150">次の例は、2 つのアプリケーション スコープ設定と 2 つのユーザー スコープの設定を定義するアプリケーション設定ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="d33c2-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d33c2-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="d33c2-151">See also</span></span>

- [<span data-ttu-id="d33c2-152">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="d33c2-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="d33c2-153">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d33c2-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
