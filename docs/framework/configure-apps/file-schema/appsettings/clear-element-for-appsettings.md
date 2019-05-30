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
ms.openlocfilehash: 5d4d96143dbd1db440de2247a7dc2f0c66f20403
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301295"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="93df8-102">\<appSettings>の\<clear>要素</span><span class="sxs-lookup"><span data-stu-id="93df8-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="93df8-103">カスタム アプリケーションの設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="93df8-103">Clears custom application settings.</span></span>

<span data-ttu-id="93df8-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="93df8-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="93df8-105">&nbsp;&nbsp;[ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="93df8-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="93df8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="93df8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="93df8-107">構文</span><span class="sxs-lookup"><span data-stu-id="93df8-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="93df8-108">属性</span><span class="sxs-lookup"><span data-stu-id="93df8-108">Attributes</span></span>

<span data-ttu-id="93df8-109">なし</span><span class="sxs-lookup"><span data-stu-id="93df8-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="93df8-110">親要素</span><span class="sxs-lookup"><span data-stu-id="93df8-110">Parent element</span></span>

|     | <span data-ttu-id="93df8-111">説明</span><span class="sxs-lookup"><span data-stu-id="93df8-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="93df8-112"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="93df8-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="93df8-113">ファイル パス、XML Web サービスの Url、またはその他のカスタム アプリケーションの構成情報など、カスタム アプリケーション設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="93df8-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="93df8-114">子要素</span><span class="sxs-lookup"><span data-stu-id="93df8-114">Child elements</span></span>

<span data-ttu-id="93df8-115">なし</span><span class="sxs-lookup"><span data-stu-id="93df8-115">None</span></span>

## <a name="example"></a><span data-ttu-id="93df8-116">例</span><span class="sxs-lookup"><span data-stu-id="93df8-116">Example</span></span>

<span data-ttu-id="93df8-117">次の例では、カスタム構成設定をクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="93df8-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="93df8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="93df8-118">See also</span></span>

- [<span data-ttu-id="93df8-119">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="93df8-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
