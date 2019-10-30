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
ms.openlocfilehash: c3e1c3a3cfd61a9fa8e7abdae9a25ec1bc674492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119226"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="332e4-102">\<appSettings > の \<クリア > 要素</span><span class="sxs-lookup"><span data-stu-id="332e4-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="332e4-103">カスタムアプリケーション設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="332e4-103">Clears custom application settings.</span></span>

<span data-ttu-id="332e4-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="332e4-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="332e4-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="332e4-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="332e4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="332e4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="332e4-107">構文</span><span class="sxs-lookup"><span data-stu-id="332e4-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="332e4-108">属性</span><span class="sxs-lookup"><span data-stu-id="332e4-108">Attributes</span></span>

<span data-ttu-id="332e4-109">None</span><span class="sxs-lookup"><span data-stu-id="332e4-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="332e4-110">親要素</span><span class="sxs-lookup"><span data-stu-id="332e4-110">Parent element</span></span>

|     | <span data-ttu-id="332e4-111">説明</span><span class="sxs-lookup"><span data-stu-id="332e4-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="332e4-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="332e4-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="332e4-113">ファイルパス、XML Web サービス Url、その他のカスタムアプリケーション構成情報などのカスタムアプリケーション設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="332e4-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="332e4-114">子要素</span><span class="sxs-lookup"><span data-stu-id="332e4-114">Child elements</span></span>

<span data-ttu-id="332e4-115">None</span><span class="sxs-lookup"><span data-stu-id="332e4-115">None</span></span>

## <a name="example"></a><span data-ttu-id="332e4-116">例</span><span class="sxs-lookup"><span data-stu-id="332e4-116">Example</span></span>

<span data-ttu-id="332e4-117">次の例は、カスタム構成設定をクリアする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="332e4-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="332e4-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="332e4-118">See also</span></span>

- [<span data-ttu-id="332e4-119">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="332e4-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
