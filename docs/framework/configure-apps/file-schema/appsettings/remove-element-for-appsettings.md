---
title: <appSettings> の <remove> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215489"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="c2116-102">\<appSettings> の \<remove> 要素</span><span class="sxs-lookup"><span data-stu-id="c2116-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="c2116-103">カスタムアプリケーション設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="c2116-103">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="c2116-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2116-104">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="c2116-105">属性</span><span class="sxs-lookup"><span data-stu-id="c2116-105">Attribute</span></span>

|         | <span data-ttu-id="c2116-106">説明</span><span class="sxs-lookup"><span data-stu-id="c2116-106">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="c2116-107">**key**</span><span class="sxs-lookup"><span data-stu-id="c2116-107">**key**</span></span> | <span data-ttu-id="c2116-108">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c2116-108">Required attribute.</span></span><br><br><span data-ttu-id="c2116-109">削除するキーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2116-109">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="c2116-110">親要素</span><span class="sxs-lookup"><span data-stu-id="c2116-110">Parent element</span></span>

|     | <span data-ttu-id="c2116-111">説明</span><span class="sxs-lookup"><span data-stu-id="c2116-111">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="c2116-112">ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2116-112">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c2116-113">子要素</span><span class="sxs-lookup"><span data-stu-id="c2116-113">Child elements</span></span>

<span data-ttu-id="c2116-114">なし</span><span class="sxs-lookup"><span data-stu-id="c2116-114">None</span></span>

## <a name="example"></a><span data-ttu-id="c2116-115">例</span><span class="sxs-lookup"><span data-stu-id="c2116-115">Example</span></span>

<span data-ttu-id="c2116-116">次の例は、のカスタム構成設定を削除する方法を示してい `ApplicationName` ます。</span><span class="sxs-lookup"><span data-stu-id="c2116-116">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="c2116-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2116-117">See also</span></span>

- [<span data-ttu-id="c2116-118">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="c2116-118">Configuration file schema for the .NET Framework</span></span>](../index.md)
