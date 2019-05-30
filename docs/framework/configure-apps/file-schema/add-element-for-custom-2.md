---
title: <add> NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 3bbe4ad6559e324db5853b95e797f50a7b908dcb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301424"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="57571-102">\<追加 > NameValueSectionHandler および DictionarySectionHandler の要素</span><span class="sxs-lookup"><span data-stu-id="57571-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="57571-103">カスタム アプリケーションの設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="57571-103">Adds custom application settings.</span></span> <span data-ttu-id="57571-104">各 **\<追加 >** タグにはキー/値ペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57571-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="57571-105">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="57571-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="57571-106">&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="57571-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="57571-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="57571-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="57571-108">構文</span><span class="sxs-lookup"><span data-stu-id="57571-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="57571-109">属性</span><span class="sxs-lookup"><span data-stu-id="57571-109">Attributes</span></span>

| <span data-ttu-id="57571-110">属性</span><span class="sxs-lookup"><span data-stu-id="57571-110">Attribute</span></span> | <span data-ttu-id="57571-111">説明</span><span class="sxs-lookup"><span data-stu-id="57571-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="57571-112">**key**</span><span class="sxs-lookup"><span data-stu-id="57571-112">**key**</span></span>   | <span data-ttu-id="57571-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="57571-113">Required attribute.</span></span><br><br><span data-ttu-id="57571-114">設定の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="57571-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="57571-115">**value**</span><span class="sxs-lookup"><span data-stu-id="57571-115">**value**</span></span> | <span data-ttu-id="57571-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="57571-116">Required attribute.</span></span><br><br><span data-ttu-id="57571-117">設定の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="57571-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="57571-118">親要素</span><span class="sxs-lookup"><span data-stu-id="57571-118">Parent element</span></span>

| <span data-ttu-id="57571-119">要素</span><span class="sxs-lookup"><span data-stu-id="57571-119">Element</span></span> | <span data-ttu-id="57571-120">説明</span><span class="sxs-lookup"><span data-stu-id="57571-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="57571-121"> *\*\<sectionName >** 要素</span><span class="sxs-lookup"><span data-stu-id="57571-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="57571-122">使用して、カスタム構成セクションの設定を定義、<xref:System.Configuration.NameValueSectionHandler>と<xref:System.Configuration.DictionarySectionHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="57571-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="57571-123">子要素</span><span class="sxs-lookup"><span data-stu-id="57571-123">Child elements</span></span>

<span data-ttu-id="57571-124">なし</span><span class="sxs-lookup"><span data-stu-id="57571-124">None</span></span>

## <a name="example"></a><span data-ttu-id="57571-125">例</span><span class="sxs-lookup"><span data-stu-id="57571-125">Example</span></span>

<span data-ttu-id="57571-126">次の例では、カスタム構成セクションを定義して使用する方法を示しています、 **\<追加 >** セクションに設定を格納する要素。</span><span class="sxs-lookup"><span data-stu-id="57571-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="57571-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="57571-127">Configuration file</span></span>

<span data-ttu-id="57571-128">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="57571-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="57571-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="57571-129">See also</span></span>

- [<span data-ttu-id="57571-130">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="57571-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
