---
title: <add>NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: ec6d5045580e887de5f05a05c8f39fa62c6e3f2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921335"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="e579f-102">\<NameValueSectionHandler および DictionarySectionHandler の > 要素を追加します</span><span class="sxs-lookup"><span data-stu-id="e579f-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="e579f-103">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="e579f-103">Adds custom application settings.</span></span> <span data-ttu-id="e579f-104">**各\<add >** タグには、キーと値のペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e579f-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="e579f-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e579f-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="e579f-106">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="e579f-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="e579f-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="e579f-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e579f-108">構文</span><span class="sxs-lookup"><span data-stu-id="e579f-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="e579f-109">属性</span><span class="sxs-lookup"><span data-stu-id="e579f-109">Attributes</span></span>

| <span data-ttu-id="e579f-110">属性</span><span class="sxs-lookup"><span data-stu-id="e579f-110">Attribute</span></span> | <span data-ttu-id="e579f-111">説明</span><span class="sxs-lookup"><span data-stu-id="e579f-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e579f-112">**key**</span><span class="sxs-lookup"><span data-stu-id="e579f-112">**key**</span></span>   | <span data-ttu-id="e579f-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e579f-113">Required attribute.</span></span><br><br><span data-ttu-id="e579f-114">設定の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e579f-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="e579f-115">**value**</span><span class="sxs-lookup"><span data-stu-id="e579f-115">**value**</span></span> | <span data-ttu-id="e579f-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e579f-116">Required attribute.</span></span><br><br><span data-ttu-id="e579f-117">設定の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e579f-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e579f-118">親要素</span><span class="sxs-lookup"><span data-stu-id="e579f-118">Parent element</span></span>

| <span data-ttu-id="e579f-119">要素</span><span class="sxs-lookup"><span data-stu-id="e579f-119">Element</span></span> | <span data-ttu-id="e579f-120">説明</span><span class="sxs-lookup"><span data-stu-id="e579f-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="e579f-121">sectionname > 要素 **\<** </span><span class="sxs-lookup"><span data-stu-id="e579f-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="e579f-122">クラス<xref:System.Configuration.NameValueSectionHandler> および<xref:System.Configuration.DictionarySectionHandler>クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e579f-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e579f-123">子要素</span><span class="sxs-lookup"><span data-stu-id="e579f-123">Child elements</span></span>

<span data-ttu-id="e579f-124">なし</span><span class="sxs-lookup"><span data-stu-id="e579f-124">None</span></span>

## <a name="example"></a><span data-ttu-id="e579f-125">例</span><span class="sxs-lookup"><span data-stu-id="e579f-125">Example</span></span>

<span data-ttu-id="e579f-126">次の例は、カスタム構成セクションを定義し、  **\<add >** 要素を使用して設定をセクションに配置する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e579f-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e579f-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="e579f-127">Configuration file</span></span>

<span data-ttu-id="e579f-128">この要素は、アプリケーション構成ファイル、コンピューター構成ファイル (machine.config)、およびアプリケーションディレクトリレベルではない web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e579f-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e579f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e579f-129">See also</span></span>

- [<span data-ttu-id="e579f-130">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="e579f-130">Configuration file schema for the .NET Framework</span></span>](index.md)
