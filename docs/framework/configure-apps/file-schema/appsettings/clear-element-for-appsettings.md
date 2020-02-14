---
title: <clear> の <appSettings> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214805"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="0007b-102">\<appSettings > の \<クリア > 要素</span><span class="sxs-lookup"><span data-stu-id="0007b-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="0007b-103">カスタムアプリケーション設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0007b-103">Clears custom application settings.</span></span>

<span data-ttu-id="0007b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0007b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0007b-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="0007b-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="0007b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="0007b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0007b-107">構文</span><span class="sxs-lookup"><span data-stu-id="0007b-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="0007b-108">属性</span><span class="sxs-lookup"><span data-stu-id="0007b-108">Attributes</span></span>

<span data-ttu-id="0007b-109">なし</span><span class="sxs-lookup"><span data-stu-id="0007b-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0007b-110">親要素</span><span class="sxs-lookup"><span data-stu-id="0007b-110">Parent element</span></span>

|     | <span data-ttu-id="0007b-111">説明</span><span class="sxs-lookup"><span data-stu-id="0007b-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0007b-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="0007b-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="0007b-113">ファイルパス、XML Web サービス Url、その他のカスタムアプリケーション構成情報などのカスタムアプリケーション設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0007b-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0007b-114">子要素</span><span class="sxs-lookup"><span data-stu-id="0007b-114">Child elements</span></span>

<span data-ttu-id="0007b-115">なし</span><span class="sxs-lookup"><span data-stu-id="0007b-115">None</span></span>

## <a name="example"></a><span data-ttu-id="0007b-116">例</span><span class="sxs-lookup"><span data-stu-id="0007b-116">Example</span></span>

<span data-ttu-id="0007b-117">次の例は、カスタム構成設定をクリアする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0007b-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="0007b-118">参照</span><span class="sxs-lookup"><span data-stu-id="0007b-118">See also</span></span>

- [<span data-ttu-id="0007b-119">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="0007b-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
