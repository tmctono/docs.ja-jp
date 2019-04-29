---
title: <appSettings>appSettings&gt;の<configuration>add&gt;要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dcdf8d0f11ae65353da08bba1f8d2fe5ab415c6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705559"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="4c7d1-102">\<appSettings > 要素の\<構成 ></span><span class="sxs-lookup"><span data-stu-id="4c7d1-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="4c7d1-103">カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-103">Contains custom application settings.</span></span> <span data-ttu-id="4c7d1-104">これは、.NET Framework で提供される定義済みの構成セクションです。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="4c7d1-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4c7d1-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="4c7d1-106">&nbsp;&nbsp;**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="4c7d1-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4c7d1-107">構文</span><span class="sxs-lookup"><span data-stu-id="4c7d1-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="4c7d1-108">属性</span><span class="sxs-lookup"><span data-stu-id="4c7d1-108">Attribute</span></span>

|           | <span data-ttu-id="4c7d1-109">説明</span><span class="sxs-lookup"><span data-stu-id="4c7d1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="4c7d1-110">**file**</span><span class="sxs-lookup"><span data-stu-id="4c7d1-110">**file**</span></span>  | <span data-ttu-id="4c7d1-111">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-111">Optional attribute.</span></span><br><br><span data-ttu-id="4c7d1-112">カスタム アプリケーションの構成設定を含む外部ファイルへの相対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="4c7d1-113">同じ種類設定で指定されているにはが、指定したファイルに含まれています、 **\<追加 >** 、 **\<削除 >** 、および **\<オフ >** 要素と同じキー/値ペアは、それらの要素として書式設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="4c7d1-114">指定されたパスでは、主要な構成ファイルの相対です。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="4c7d1-115">Windows フォーム アプリケーションでは、これは、バイナリ フォルダー (など*bin/デバッグ*)、アプリケーション構成ファイルの場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="4c7d1-116">Web フォーム アプリケーション、パスは、アプリケーションのルートを基準とした場所、 *web.config*ファイルが配置されています。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="4c7d1-117">指定したファイルが見つからない場合、ランタイムは、属性を無視します。 注意してください。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="4c7d1-118">親要素</span><span class="sxs-lookup"><span data-stu-id="4c7d1-118">Parent element</span></span>

|     | <span data-ttu-id="4c7d1-119">説明</span><span class="sxs-lookup"><span data-stu-id="4c7d1-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4c7d1-120">**\<configuration >** 要素</span><span class="sxs-lookup"><span data-stu-id="4c7d1-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="4c7d1-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4c7d1-122">子要素</span><span class="sxs-lookup"><span data-stu-id="4c7d1-122">Child elements</span></span>

|     | <span data-ttu-id="4c7d1-123">説明</span><span class="sxs-lookup"><span data-stu-id="4c7d1-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4c7d1-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="4c7d1-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="4c7d1-125">カスタム アプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="4c7d1-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="4c7d1-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="4c7d1-127">すべての定義済みのアプリケーション設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="4c7d1-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="4c7d1-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="4c7d1-129">定義済みのアプリケーション設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="4c7d1-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c7d1-130">Remarks</span></span>

<span data-ttu-id="4c7d1-131"> *\*\<AppSettings >** 要素は、データベース接続文字列、ファイル パス、XML Web サービスの Url の他のカスタム構成情報などのカスタム アプリケーションの構成情報を格納します。アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="4c7d1-132">指定されたキーと値のペア、  **\<appSettings >** 要素は、コードを使用して、<xref:System.Configuration.ConfigurationSettings>クラス。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="4c7d1-133">使用することができます、**ファイル**属性、  **\<appSettings >** の要素、 *Web.config*とアプリケーション構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="4c7d1-134">この属性は、追加の設定を提供またはで指定された設定をオーバーライドする構成ファイルを指定、  **\<appSettings >** 要素。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="4c7d1-135">**ファイル**属性をソース制御チーム開発などのシナリオで、ユーザーがアプリケーション構成ファイルで指定されたプロジェクトの設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="4c7d1-136">指定された構成ファイル、**ファイル**属性のルート ノードが必要です **\<appSettings >** なく **\<構成>** 。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="4c7d1-137">例</span><span class="sxs-lookup"><span data-stu-id="4c7d1-137">Example</span></span>

<span data-ttu-id="4c7d1-138">次の例は、カスタム アプリケーション設定を定義する外部アプリケーション設定ファイル (*custom.config*) を示しています。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="4c7d1-139">次の例は、外部設定ファイルで設定を使用して、独自のアプリケーション設定を設定するアプリケーション構成ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="4c7d1-140">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4c7d1-140">Configuration file</span></span>

<span data-ttu-id="4c7d1-141">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="4c7d1-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c7d1-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c7d1-142">See also</span></span>

- [<span data-ttu-id="4c7d1-143">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4c7d1-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
