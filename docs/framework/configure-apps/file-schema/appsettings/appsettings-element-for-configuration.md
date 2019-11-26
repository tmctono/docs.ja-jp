---
title: <configuration> の <appSettings> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6112d87afcca8b2f54508d03d3ea4c0781d7e475
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119269"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="7a3e0-102">\<configuration> の \<appSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="7a3e0-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="7a3e0-103">カスタムアプリケーション設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-103">Contains custom application settings.</span></span> <span data-ttu-id="7a3e0-104">これは、.NET Framework によって提供される定義済みの構成セクションです。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="7a3e0-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7a3e0-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="7a3e0-106">&nbsp;&nbsp; **\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="7a3e0-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7a3e0-107">構文</span><span class="sxs-lookup"><span data-stu-id="7a3e0-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="7a3e0-108">属性</span><span class="sxs-lookup"><span data-stu-id="7a3e0-108">Attribute</span></span>

|           | <span data-ttu-id="7a3e0-109">説明</span><span class="sxs-lookup"><span data-stu-id="7a3e0-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7a3e0-110">**file**</span><span class="sxs-lookup"><span data-stu-id="7a3e0-110">**file**</span></span>  | <span data-ttu-id="7a3e0-111">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-111">Optional attribute.</span></span><br><br><span data-ttu-id="7a3e0-112">カスタムアプリケーション構成設定を含む外部ファイルへの相対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="7a3e0-113">同じ種類設定で指定されているにはが、指定したファイルに含まれています、 **\<add>** 、 **\<remove>** 、および **\<clear>** 要素と同じキー/値ペアは、それらの要素として書式設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="7a3e0-114">指定されたパスは、メイン構成ファイルに対する相対パスです。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="7a3e0-115">Windows フォームアプリケーションの場合、これはアプリケーション構成ファイルの場所ではなく、バイナリフォルダー ( */bin/debug*など) です。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="7a3e0-116">Web フォームアプリケーションの場合、パスは、web.config ファイルが配置さ*れている*アプリケーションルートに対する相対パスです。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="7a3e0-117">指定されたファイルが見つからない場合、ランタイムは属性を無視することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7a3e0-118">親要素</span><span class="sxs-lookup"><span data-stu-id="7a3e0-118">Parent element</span></span>

|     | <span data-ttu-id="7a3e0-119">説明</span><span class="sxs-lookup"><span data-stu-id="7a3e0-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7a3e0-120"> **\<configuration>** 要素</span><span class="sxs-lookup"><span data-stu-id="7a3e0-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="7a3e0-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7a3e0-122">子要素</span><span class="sxs-lookup"><span data-stu-id="7a3e0-122">Child elements</span></span>

|     | <span data-ttu-id="7a3e0-123">説明</span><span class="sxs-lookup"><span data-stu-id="7a3e0-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7a3e0-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="7a3e0-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="7a3e0-125">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="7a3e0-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="7a3e0-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="7a3e0-127">以前に定義したアプリケーション設定をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="7a3e0-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="7a3e0-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="7a3e0-129">以前に定義したアプリケーション設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7a3e0-130">コメント</span><span class="sxs-lookup"><span data-stu-id="7a3e0-130">Remarks</span></span>

<span data-ttu-id="7a3e0-131">**\<appSettings>** 要素には、データベース接続文字列、ファイルパス、XML Web サービス url、またはアプリケーションのその他のカスタム構成情報など、カスタムアプリケーション構成情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="7a3e0-132">**\<appSettings >** 要素で指定されたキーと値のペアは、<xref:System.Configuration.ConfigurationSettings> クラスを使用してコードでアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="7a3e0-133">Web.config ファイルと*アプリケーション*構成ファイルの **\<appSettings>** 要素で **file** 属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="7a3e0-134">この属性は、追加設定を提供するか、 **\<appSettings>** 要素で指定された設定をオーバーライドする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="7a3e0-135">**file** 属性は、アプリケーション構成ファイルで指定されたプロジェクト設定をユーザーがオーバーライドする必要がある場合など、ソース管理チームの開発シナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="7a3e0-136">**file** 属性で指定された構成ファイルには、 **\<configuration>** ではなく **\<appSettings >** のルート ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="7a3e0-137">例</span><span class="sxs-lookup"><span data-stu-id="7a3e0-137">Example</span></span>

<span data-ttu-id="7a3e0-138">次の例は、カスタム アプリケーション設定を定義する外部アプリケーション設定ファイル (*custom.config*) を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="7a3e0-139">次の例は、外部設定ファイルで設定を使用して、独自のアプリケーション設定を設定するアプリケーション構成ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="7a3e0-140">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="7a3e0-140">Configuration file</span></span>

<span data-ttu-id="7a3e0-141">この要素は、アプリケーション構成ファイル、マシン構成ファイル *(Machine.config)* 、およびアプリケーションディレクトリレベルではない *Web.config* ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a3e0-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a3e0-142">参照</span><span class="sxs-lookup"><span data-stu-id="7a3e0-142">See also</span></span>

- [<span data-ttu-id="7a3e0-143">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="7a3e0-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
