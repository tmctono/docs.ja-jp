---
title: SingleTagSectionHandler のカスタム要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927502"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="4b96e-102">SingleTagSectionHandler のカスタム要素</span><span class="sxs-lookup"><span data-stu-id="4b96e-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="4b96e-103">\<セクション > 要素によって定義され、 <xref:System.Configuration.SingleTagSectionHandler>クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4b96e-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="4b96e-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4b96e-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="4b96e-105">&nbsp;&nbsp; *\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="4b96e-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="4b96e-106">構文</span><span class="sxs-lookup"><span data-stu-id="4b96e-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="4b96e-107">属性</span><span class="sxs-lookup"><span data-stu-id="4b96e-107">Attributes</span></span>

<span data-ttu-id="4b96e-108">属性と属性値はユーザーが定義します。</span><span class="sxs-lookup"><span data-stu-id="4b96e-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="4b96e-109">親要素</span><span class="sxs-lookup"><span data-stu-id="4b96e-109">Parent element</span></span>

|     | <span data-ttu-id="4b96e-110">説明</span><span class="sxs-lookup"><span data-stu-id="4b96e-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4b96e-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4b96e-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="4b96e-112">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="4b96e-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4b96e-113">子要素</span><span class="sxs-lookup"><span data-stu-id="4b96e-113">Child elements</span></span>

<span data-ttu-id="4b96e-114">なし</span><span class="sxs-lookup"><span data-stu-id="4b96e-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="4b96e-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b96e-115">Remarks</span></span>

<span data-ttu-id="4b96e-116">Sectionname > 要素は、 [ **\<configsections >** ](configsections-element-for-configuration.md)要素の[ **\<セクション >** ](section-element.md)タグによって定義されたカスタム要素です。  **\<**</span><span class="sxs-lookup"><span data-stu-id="4b96e-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="4b96e-117">を呼び出す<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>と、 <xref:System.Collections.IDictionary>構成システムからオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="4b96e-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="4b96e-118">例</span><span class="sxs-lookup"><span data-stu-id="4b96e-118">Example</span></span>

<span data-ttu-id="4b96e-119">次の例では、 <xref:System.Configuration.SingleTagSectionHandler>クラスによって読み取られた設定を含む **\<sampleSection >** という名前のカスタム要素を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="4b96e-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="4b96e-120">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4b96e-120">Configuration file</span></span>

<span data-ttu-id="4b96e-121">この要素は、アプリケーション構成ファイル、コンピューター構成ファイル (machine.config)、およびアプリケーションディレクトリレベルではない web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b96e-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b96e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b96e-122">See also</span></span>

- [<span data-ttu-id="4b96e-123">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="4b96e-123">Configuration file schema for the .NET Framework</span></span>](index.md)
