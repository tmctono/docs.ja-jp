---
title: <configuration> の <appSettings> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155532"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="7e5d5-102">\<構成>の\<>要素</span><span class="sxs-lookup"><span data-stu-id="7e5d5-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="7e5d5-103">カスタム アプリケーション設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-103">Contains custom application settings.</span></span> <span data-ttu-id="7e5d5-104">これは、.NET Framework によって提供される定義済みの構成セクションです。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="7e5d5-105">&nbsp;[**\<構成>**](../configuration-element.md)&nbsp;**アプリ設定>\<**</span><span class="sxs-lookup"><span data-stu-id="7e5d5-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7e5d5-106">構文</span><span class="sxs-lookup"><span data-stu-id="7e5d5-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="7e5d5-107">属性</span><span class="sxs-lookup"><span data-stu-id="7e5d5-107">Attribute</span></span>

|           | <span data-ttu-id="7e5d5-108">説明</span><span class="sxs-lookup"><span data-stu-id="7e5d5-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7e5d5-109">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="7e5d5-109">**file**</span></span>  | <span data-ttu-id="7e5d5-110">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-110">Optional attribute.</span></span><br><br><span data-ttu-id="7e5d5-111">カスタム アプリケーション構成設定を含む外部ファイルへの相対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="7e5d5-112">指定したファイルには、[**\<追加>、\*\*\*\*\<削除**、>、および**\<>** 要素をクリアする] で指定した同じ種類の設定が含まれ、それらの要素と同じキー/値ペア形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="7e5d5-113">指定されたパスは、メイン構成ファイルを基準にしています。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="7e5d5-114">Windows フォーム アプリケーションの場合、これはバイナリ フォルダ *(/bin/debug*など) であり、アプリケーション構成ファイルの場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="7e5d5-115">Web フォーム アプリケーションの場合、パスは *、web.config*ファイルが配置されているアプリケーション ルートを基準にしています。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="7e5d5-116">指定されたファイルが見つからない場合、ランタイムはこの属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7e5d5-117">親要素</span><span class="sxs-lookup"><span data-stu-id="7e5d5-117">Parent element</span></span>

|     | <span data-ttu-id="7e5d5-118">説明</span><span class="sxs-lookup"><span data-stu-id="7e5d5-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7e5d5-119">**\<構成>** 要素</span><span class="sxs-lookup"><span data-stu-id="7e5d5-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="7e5d5-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7e5d5-121">子要素</span><span class="sxs-lookup"><span data-stu-id="7e5d5-121">Child elements</span></span>

|     | <span data-ttu-id="7e5d5-122">説明</span><span class="sxs-lookup"><span data-stu-id="7e5d5-122">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7e5d5-123">**\<>を追加する**</span><span class="sxs-lookup"><span data-stu-id="7e5d5-123">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="7e5d5-124">カスタム アプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-124">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="7e5d5-125">**\<クリア>**</span><span class="sxs-lookup"><span data-stu-id="7e5d5-125">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="7e5d5-126">以前に定義したアプリケーション設定をすべてクリアします。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-126">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="7e5d5-127">**\<>を削除する**</span><span class="sxs-lookup"><span data-stu-id="7e5d5-127">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="7e5d5-128">以前に定義したアプリケーション設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-128">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7e5d5-129">解説</span><span class="sxs-lookup"><span data-stu-id="7e5d5-129">Remarks</span></span>

<span data-ttu-id="7e5d5-130">\*\* \<appSettings>\*\* 要素には、データベース接続文字列、ファイル パス、XML Web サービス URL、アプリケーションのその他のカスタム構成情報などのカスタム アプリケーション構成情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-130">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="7e5d5-131">\*\* \<appSettings>\*\* 要素で指定されたキーと値のペアは、クラスを使用<xref:System.Configuration.ConfigurationSettings>してコードでアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-131">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="7e5d5-132">*web.config*およびアプリケーション構成ファイルの**\<>** 要素の appSettings で**ファイル**属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-132">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="7e5d5-133">この属性は、追加の設定を提供する構成ファイルを指定するか**\<、appSettings>** 要素で指定された設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-133">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="7e5d5-134">**file**属性は、ソース管理チームの開発シナリオで使用できます (ユーザーがアプリケーション構成ファイルで指定されたプロジェクト設定を上書きする場合など)。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-134">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="7e5d5-135">**file**属性で指定される構成ファイルには、**\<構成>** ではなく**\<、appSettings>** のルート ノードが必要です。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-135">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="7e5d5-136">例</span><span class="sxs-lookup"><span data-stu-id="7e5d5-136">Example</span></span>

<span data-ttu-id="7e5d5-137">次の例は、カスタム アプリケーション設定を定義する外部アプリケーション設定ファイル (*custom.config*) を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-137">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="7e5d5-138">次の例は、外部設定ファイルで設定を使用して、独自のアプリケーション設定を設定するアプリケーション構成ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-138">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="7e5d5-139">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="7e5d5-139">Configuration file</span></span>

<span data-ttu-id="7e5d5-140">この要素は、アプリケーションディレクトリレベルではないアプリケーション構成ファイル、マシン構成ファイル (*Machine.config*) および*Web.config*ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e5d5-140">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e5d5-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e5d5-141">See also</span></span>

- [<span data-ttu-id="7e5d5-142">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="7e5d5-142">Configuration file schema for the .NET Framework</span></span>](../index.md)
