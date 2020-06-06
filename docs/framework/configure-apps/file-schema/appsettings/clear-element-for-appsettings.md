---
title: <appSettings> の <clear> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214805"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="7e63b-102">\<appSettings> の \<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="7e63b-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="7e63b-103">カスタムアプリケーション設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="7e63b-103">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="7e63b-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e63b-104">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="7e63b-105">属性</span><span class="sxs-lookup"><span data-stu-id="7e63b-105">Attributes</span></span>

<span data-ttu-id="7e63b-106">なし</span><span class="sxs-lookup"><span data-stu-id="7e63b-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="7e63b-107">親要素</span><span class="sxs-lookup"><span data-stu-id="7e63b-107">Parent element</span></span>

|     | <span data-ttu-id="7e63b-108">説明</span><span class="sxs-lookup"><span data-stu-id="7e63b-108">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="7e63b-109">ファイルパス、XML Web サービス Url、その他のカスタムアプリケーション構成情報などのカスタムアプリケーション設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e63b-109">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7e63b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="7e63b-110">Child elements</span></span>

<span data-ttu-id="7e63b-111">なし</span><span class="sxs-lookup"><span data-stu-id="7e63b-111">None</span></span>

## <a name="example"></a><span data-ttu-id="7e63b-112">例</span><span class="sxs-lookup"><span data-stu-id="7e63b-112">Example</span></span>

<span data-ttu-id="7e63b-113">次の例は、カスタム構成設定をクリアする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e63b-113">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="7e63b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e63b-114">See also</span></span>

- [<span data-ttu-id="7e63b-115">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="7e63b-115">Configuration file schema for the .NET Framework</span></span>](../index.md)
