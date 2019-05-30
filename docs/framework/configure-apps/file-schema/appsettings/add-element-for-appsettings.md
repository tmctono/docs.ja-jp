---
title: <add>appSettings&gt;の<appSettings>add&gt;要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: f8b426dc0e1e180afbfccce50d3b45774991a572
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301348"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="4350d-102">\<appSettings>の\<add>要素</span><span class="sxs-lookup"><span data-stu-id="4350d-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="4350d-103">カスタム アプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="4350d-103">Adds a custom application setting.</span></span>

<span data-ttu-id="4350d-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4350d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="4350d-105">&nbsp;&nbsp;[ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="4350d-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="4350d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="4350d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4350d-107">構文</span><span class="sxs-lookup"><span data-stu-id="4350d-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="4350d-108">属性</span><span class="sxs-lookup"><span data-stu-id="4350d-108">Attributes</span></span>

|           | <span data-ttu-id="4350d-109">説明</span><span class="sxs-lookup"><span data-stu-id="4350d-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="4350d-110">**key**</span><span class="sxs-lookup"><span data-stu-id="4350d-110">**key**</span></span>   | <span data-ttu-id="4350d-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4350d-111">Required attribute.</span></span><br><br><span data-ttu-id="4350d-112">追加するキーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4350d-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="4350d-113">**value**</span><span class="sxs-lookup"><span data-stu-id="4350d-113">**value**</span></span> | <span data-ttu-id="4350d-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4350d-114">Required attribute.</span></span><br><br><span data-ttu-id="4350d-115">追加するキーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4350d-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="4350d-116">親要素</span><span class="sxs-lookup"><span data-stu-id="4350d-116">Parent element</span></span>

|     | <span data-ttu-id="4350d-117">説明</span><span class="sxs-lookup"><span data-stu-id="4350d-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4350d-118"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="4350d-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="4350d-119">ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4350d-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4350d-120">子要素</span><span class="sxs-lookup"><span data-stu-id="4350d-120">Child elements</span></span>

<span data-ttu-id="4350d-121">なし</span><span class="sxs-lookup"><span data-stu-id="4350d-121">None</span></span>

## <a name="example"></a><span data-ttu-id="4350d-122">例</span><span class="sxs-lookup"><span data-stu-id="4350d-122">Example</span></span>

<span data-ttu-id="4350d-123">次の例では、アプリケーションの名前のカスタム構成設定を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4350d-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="4350d-124">次の例では、 `<add>` ASP.NET アプリケーションで 2 つの互換性設定を定義する要素。</span><span class="sxs-lookup"><span data-stu-id="4350d-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="4350d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4350d-125">See also</span></span>

- [<span data-ttu-id="4350d-126">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4350d-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
