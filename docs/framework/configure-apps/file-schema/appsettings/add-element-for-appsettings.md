---
title: <add> の <appSettings> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214804"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="2e59c-102">\<appSettings > の > 要素を追加 \<には</span><span class="sxs-lookup"><span data-stu-id="2e59c-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="2e59c-103">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="2e59c-103">Adds a custom application setting.</span></span>

<span data-ttu-id="2e59c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e59c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e59c-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="2e59c-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="2e59c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<追加 >**</span><span class="sxs-lookup"><span data-stu-id="2e59c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2e59c-107">構文</span><span class="sxs-lookup"><span data-stu-id="2e59c-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="2e59c-108">属性</span><span class="sxs-lookup"><span data-stu-id="2e59c-108">Attributes</span></span>

|           | <span data-ttu-id="2e59c-109">説明</span><span class="sxs-lookup"><span data-stu-id="2e59c-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2e59c-110">**key**</span><span class="sxs-lookup"><span data-stu-id="2e59c-110">**key**</span></span>   | <span data-ttu-id="2e59c-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2e59c-111">Required attribute.</span></span><br><br><span data-ttu-id="2e59c-112">追加するキーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e59c-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="2e59c-113">**value**</span><span class="sxs-lookup"><span data-stu-id="2e59c-113">**value**</span></span> | <span data-ttu-id="2e59c-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="2e59c-114">Required attribute.</span></span><br><br><span data-ttu-id="2e59c-115">追加するキーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e59c-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2e59c-116">親要素</span><span class="sxs-lookup"><span data-stu-id="2e59c-116">Parent element</span></span>

|     | <span data-ttu-id="2e59c-117">説明</span><span class="sxs-lookup"><span data-stu-id="2e59c-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2e59c-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="2e59c-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="2e59c-119">ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e59c-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2e59c-120">子要素</span><span class="sxs-lookup"><span data-stu-id="2e59c-120">Child elements</span></span>

<span data-ttu-id="2e59c-121">なし</span><span class="sxs-lookup"><span data-stu-id="2e59c-121">None</span></span>

## <a name="example"></a><span data-ttu-id="2e59c-122">例</span><span class="sxs-lookup"><span data-stu-id="2e59c-122">Example</span></span>

<span data-ttu-id="2e59c-123">次の例は、アプリケーション名のカスタム構成設定を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2e59c-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="2e59c-124">次の例では、`<add>` 要素を使用して、ASP.NET アプリケーションで2つの互換性設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e59c-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="2e59c-125">参照</span><span class="sxs-lookup"><span data-stu-id="2e59c-125">See also</span></span>

- [<span data-ttu-id="2e59c-126">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="2e59c-126">Configuration file schema for the .NET Framework</span></span>](../index.md)
