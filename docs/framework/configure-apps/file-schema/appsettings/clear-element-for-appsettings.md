---
title: <appSettings>の<clear>要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d5da531bff3a0e9e198ba9b5ab6cf2b52bf36b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921311"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="e6b54-102">\<appSettings>の\<clear>要素</span><span class="sxs-lookup"><span data-stu-id="e6b54-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="e6b54-103">カスタムアプリケーション設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="e6b54-103">Clears custom application settings.</span></span>

<span data-ttu-id="e6b54-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e6b54-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="e6b54-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e6b54-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="e6b54-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="e6b54-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e6b54-107">構文</span><span class="sxs-lookup"><span data-stu-id="e6b54-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="e6b54-108">属性</span><span class="sxs-lookup"><span data-stu-id="e6b54-108">Attributes</span></span>

<span data-ttu-id="e6b54-109">なし</span><span class="sxs-lookup"><span data-stu-id="e6b54-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="e6b54-110">親要素</span><span class="sxs-lookup"><span data-stu-id="e6b54-110">Parent element</span></span>

|     | <span data-ttu-id="e6b54-111">説明</span><span class="sxs-lookup"><span data-stu-id="e6b54-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e6b54-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="e6b54-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="e6b54-113">ファイルパス、XML Web サービス Url、その他のカスタムアプリケーション構成情報などのカスタムアプリケーション設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6b54-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e6b54-114">子要素</span><span class="sxs-lookup"><span data-stu-id="e6b54-114">Child elements</span></span>

<span data-ttu-id="e6b54-115">なし</span><span class="sxs-lookup"><span data-stu-id="e6b54-115">None</span></span>

## <a name="example"></a><span data-ttu-id="e6b54-116">例</span><span class="sxs-lookup"><span data-stu-id="e6b54-116">Example</span></span>

<span data-ttu-id="e6b54-117">次の例は、カスタム構成設定をクリアする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e6b54-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="e6b54-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6b54-118">See also</span></span>

- [<span data-ttu-id="e6b54-119">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="e6b54-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
