---
title: SingleTagSectionHandler のカスタム要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac2d01121e81b545556fb082fa7b82c31cccf9da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118836"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="03ec3-102">SingleTagSectionHandler のカスタム要素</span><span class="sxs-lookup"><span data-stu-id="03ec3-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="03ec3-103">\<セクション > 要素で定義され、<xref:System.Configuration.SingleTagSectionHandler> クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="03ec3-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="03ec3-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="03ec3-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="03ec3-105">&nbsp;&nbsp; *\<sectionName >*</span><span class="sxs-lookup"><span data-stu-id="03ec3-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="03ec3-106">構文</span><span class="sxs-lookup"><span data-stu-id="03ec3-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="03ec3-107">属性</span><span class="sxs-lookup"><span data-stu-id="03ec3-107">Attributes</span></span>

<span data-ttu-id="03ec3-108">属性と属性値はユーザーが定義します。</span><span class="sxs-lookup"><span data-stu-id="03ec3-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="03ec3-109">親要素</span><span class="sxs-lookup"><span data-stu-id="03ec3-109">Parent element</span></span>

|     | <span data-ttu-id="03ec3-110">説明</span><span class="sxs-lookup"><span data-stu-id="03ec3-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03ec3-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="03ec3-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="03ec3-112">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="03ec3-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="03ec3-113">子要素</span><span class="sxs-lookup"><span data-stu-id="03ec3-113">Child elements</span></span>

<span data-ttu-id="03ec3-114">None</span><span class="sxs-lookup"><span data-stu-id="03ec3-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="03ec3-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="03ec3-115">Remarks</span></span>

<span data-ttu-id="03ec3-116">**\<sectionName >** 要素は、 [ **\<configsections >** ](configsections-element-for-configuration.md)要素の[ **\<セクション >** ](section-element.md)タグで定義されたカスタム要素です。</span><span class="sxs-lookup"><span data-stu-id="03ec3-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="03ec3-117"><xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>を呼び出すと、構成システムによって <xref:System.Collections.IDictionary> オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="03ec3-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="03ec3-118">例</span><span class="sxs-lookup"><span data-stu-id="03ec3-118">Example</span></span>

<span data-ttu-id="03ec3-119">次の例では、<xref:System.Configuration.SingleTagSectionHandler> クラスによって読み取られる設定を含む **\<sampleSection >** という名前のカスタム要素を宣言します。</span><span class="sxs-lookup"><span data-stu-id="03ec3-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="03ec3-120">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="03ec3-120">Configuration file</span></span>

<span data-ttu-id="03ec3-121">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="03ec3-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="03ec3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="03ec3-122">See also</span></span>

- [<span data-ttu-id="03ec3-123">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="03ec3-123">Configuration file schema for the .NET Framework</span></span>](index.md)
