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
ms.openlocfilehash: ad98617cd4e88d1650f67136536b7dd5994233a4
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301150"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="343c5-102">SingleTagSectionHandler のカスタム要素</span><span class="sxs-lookup"><span data-stu-id="343c5-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="343c5-103">定義されているカスタム構成セクションの設定を定義、\<セクション > 要素と、使用して、<xref:System.Configuration.SingleTagSectionHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="343c5-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="343c5-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="343c5-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="343c5-105">&nbsp;&nbsp; *\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="343c5-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="343c5-106">構文</span><span class="sxs-lookup"><span data-stu-id="343c5-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="343c5-107">属性</span><span class="sxs-lookup"><span data-stu-id="343c5-107">Attributes</span></span>

<span data-ttu-id="343c5-108">属性および属性値は、ユーザー定義です。</span><span class="sxs-lookup"><span data-stu-id="343c5-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="343c5-109">親要素</span><span class="sxs-lookup"><span data-stu-id="343c5-109">Parent element</span></span>

|     | <span data-ttu-id="343c5-110">説明</span><span class="sxs-lookup"><span data-stu-id="343c5-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="343c5-111"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="343c5-111">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="343c5-112">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="343c5-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="343c5-113">子要素</span><span class="sxs-lookup"><span data-stu-id="343c5-113">Child elements</span></span>

<span data-ttu-id="343c5-114">なし</span><span class="sxs-lookup"><span data-stu-id="343c5-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="343c5-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="343c5-115">Remarks</span></span>

<span data-ttu-id="343c5-116"> *\*\<SectionName >** 要素がによって定義されるカスタム要素、 [ *\*\<セクション >** ](~/docs/framework/configure-apps/file-schema/section-element.md)にタグを付ける、 [ *\*\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)要素。</span><span class="sxs-lookup"><span data-stu-id="343c5-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="343c5-117">構成システムから返される、<xref:System.Collections.IDictionary>オブジェクトを呼び出すと<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="343c5-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="343c5-118">例</span><span class="sxs-lookup"><span data-stu-id="343c5-118">Example</span></span>

<span data-ttu-id="343c5-119">次の例と呼ばれるカスタム要素の宣言 **\<sampleSection >** によって読み取られた設定を格納する、<xref:System.Configuration.SingleTagSectionHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="343c5-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="343c5-120">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="343c5-120">Configuration file</span></span>

<span data-ttu-id="343c5-121">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="343c5-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="343c5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="343c5-122">See also</span></span>

- [<span data-ttu-id="343c5-123">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="343c5-123">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
