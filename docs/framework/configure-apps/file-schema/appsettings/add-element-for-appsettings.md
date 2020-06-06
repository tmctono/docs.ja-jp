---
title: <appSettings> の <add> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214804"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="9bd87-102">\<appSettings> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="9bd87-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="9bd87-103">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="9bd87-103">Adds a custom application setting.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="9bd87-104">構文</span><span class="sxs-lookup"><span data-stu-id="9bd87-104">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="9bd87-105">属性</span><span class="sxs-lookup"><span data-stu-id="9bd87-105">Attributes</span></span>

|           | <span data-ttu-id="9bd87-106">説明</span><span class="sxs-lookup"><span data-stu-id="9bd87-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="9bd87-107">**key**</span><span class="sxs-lookup"><span data-stu-id="9bd87-107">**key**</span></span>   | <span data-ttu-id="9bd87-108">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9bd87-108">Required attribute.</span></span><br><br><span data-ttu-id="9bd87-109">追加するキーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd87-109">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="9bd87-110">**value**</span><span class="sxs-lookup"><span data-stu-id="9bd87-110">**value**</span></span> | <span data-ttu-id="9bd87-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9bd87-111">Required attribute.</span></span><br><br><span data-ttu-id="9bd87-112">追加するキーの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9bd87-112">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="9bd87-113">親要素</span><span class="sxs-lookup"><span data-stu-id="9bd87-113">Parent element</span></span>

|     | <span data-ttu-id="9bd87-114">Description</span><span class="sxs-lookup"><span data-stu-id="9bd87-114">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="9bd87-115">ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9bd87-115">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9bd87-116">子要素</span><span class="sxs-lookup"><span data-stu-id="9bd87-116">Child elements</span></span>

<span data-ttu-id="9bd87-117">なし</span><span class="sxs-lookup"><span data-stu-id="9bd87-117">None</span></span>

## <a name="example"></a><span data-ttu-id="9bd87-118">例</span><span class="sxs-lookup"><span data-stu-id="9bd87-118">Example</span></span>

<span data-ttu-id="9bd87-119">次の例は、アプリケーション名のカスタム構成設定を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9bd87-119">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="9bd87-120">次の例では、要素を使用して、 `<add>` ASP.NET アプリケーションで2つの互換性設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9bd87-120">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="9bd87-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bd87-121">See also</span></span>

- [<span data-ttu-id="9bd87-122">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="9bd87-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
