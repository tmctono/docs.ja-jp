---
title: <appSettings>の<remove>要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 121b1c4b124ba07ff3bd312fd3832d3da592f486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921290"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="4545b-102">\<appSettings>の\<remove>要素</span><span class="sxs-lookup"><span data-stu-id="4545b-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="4545b-103">カスタムアプリケーション設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="4545b-103">Removes custom application settings.</span></span>

<span data-ttu-id="4545b-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4545b-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="4545b-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="4545b-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="4545b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> の削除**</span><span class="sxs-lookup"><span data-stu-id="4545b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4545b-107">構文</span><span class="sxs-lookup"><span data-stu-id="4545b-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="4545b-108">属性</span><span class="sxs-lookup"><span data-stu-id="4545b-108">Attribute</span></span>

|         | <span data-ttu-id="4545b-109">説明</span><span class="sxs-lookup"><span data-stu-id="4545b-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="4545b-110">**key**</span><span class="sxs-lookup"><span data-stu-id="4545b-110">**key**</span></span> | <span data-ttu-id="4545b-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4545b-111">Required attribute.</span></span><br><br><span data-ttu-id="4545b-112">削除するキーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4545b-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="4545b-113">親要素</span><span class="sxs-lookup"><span data-stu-id="4545b-113">Parent element</span></span>

|     | <span data-ttu-id="4545b-114">説明</span><span class="sxs-lookup"><span data-stu-id="4545b-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4545b-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="4545b-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="4545b-116">ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4545b-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4545b-117">子要素</span><span class="sxs-lookup"><span data-stu-id="4545b-117">Child elements</span></span>

<span data-ttu-id="4545b-118">なし</span><span class="sxs-lookup"><span data-stu-id="4545b-118">None</span></span>

## <a name="example"></a><span data-ttu-id="4545b-119">例</span><span class="sxs-lookup"><span data-stu-id="4545b-119">Example</span></span>

<span data-ttu-id="4545b-120">次の例は、の`ApplicationName`カスタム構成設定を削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4545b-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="4545b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4545b-121">See also</span></span>

- [<span data-ttu-id="4545b-122">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="4545b-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
