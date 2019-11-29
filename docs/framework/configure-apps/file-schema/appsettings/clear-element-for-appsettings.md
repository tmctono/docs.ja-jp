---
title: <appSettings> の <clear> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d321f3169344e9aa40d65b1722a533549de5315a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088733"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="12b35-102">\<appSettings > の \<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="12b35-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="12b35-103">カスタムアプリケーション設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="12b35-103">Clears custom application settings.</span></span>

<span data-ttu-id="12b35-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="12b35-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="12b35-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="12b35-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="12b35-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="12b35-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="12b35-107">構文</span><span class="sxs-lookup"><span data-stu-id="12b35-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="12b35-108">属性</span><span class="sxs-lookup"><span data-stu-id="12b35-108">Attributes</span></span>

<span data-ttu-id="12b35-109">None</span><span class="sxs-lookup"><span data-stu-id="12b35-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="12b35-110">親要素</span><span class="sxs-lookup"><span data-stu-id="12b35-110">Parent element</span></span>

|     | <span data-ttu-id="12b35-111">説明</span><span class="sxs-lookup"><span data-stu-id="12b35-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="12b35-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="12b35-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="12b35-113">ファイルパス、XML Web サービス Url、その他のカスタムアプリケーション構成情報などのカスタムアプリケーション設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="12b35-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="12b35-114">子要素</span><span class="sxs-lookup"><span data-stu-id="12b35-114">Child elements</span></span>

<span data-ttu-id="12b35-115">None</span><span class="sxs-lookup"><span data-stu-id="12b35-115">None</span></span>

## <a name="example"></a><span data-ttu-id="12b35-116">例</span><span class="sxs-lookup"><span data-stu-id="12b35-116">Example</span></span>

<span data-ttu-id="12b35-117">次の例は、カスタム構成設定をクリアする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="12b35-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="12b35-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="12b35-118">See also</span></span>

- [<span data-ttu-id="12b35-119">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="12b35-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
