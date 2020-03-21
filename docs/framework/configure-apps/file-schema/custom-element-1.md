---
title: カスタム要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 04360a796b18cf1e414f1f84bff247a1e9d8ef9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155155"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="3de6c-102">カスタム要素</span><span class="sxs-lookup"><span data-stu-id="3de6c-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="3de6c-103">要素の\<セクションで定義され、クラスを使用するカスタム構成セクション>設定を定義<xref:System.Configuration.SingleTagSectionHandler>します。</span><span class="sxs-lookup"><span data-stu-id="3de6c-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="3de6c-104">&nbsp;[**\<構成>**](configuration-element.md)&nbsp;*セクション名>\<*</span><span class="sxs-lookup"><span data-stu-id="3de6c-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="3de6c-105">構文</span><span class="sxs-lookup"><span data-stu-id="3de6c-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="3de6c-106">属性</span><span class="sxs-lookup"><span data-stu-id="3de6c-106">Attributes</span></span>

<span data-ttu-id="3de6c-107">属性と属性値はユーザー定義です。</span><span class="sxs-lookup"><span data-stu-id="3de6c-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="3de6c-108">親要素</span><span class="sxs-lookup"><span data-stu-id="3de6c-108">Parent element</span></span>

|     | <span data-ttu-id="3de6c-109">説明</span><span class="sxs-lookup"><span data-stu-id="3de6c-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3de6c-110">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="3de6c-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="3de6c-111">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="3de6c-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3de6c-112">子要素</span><span class="sxs-lookup"><span data-stu-id="3de6c-112">Child elements</span></span>

<span data-ttu-id="3de6c-113">なし</span><span class="sxs-lookup"><span data-stu-id="3de6c-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="3de6c-114">解説</span><span class="sxs-lookup"><span data-stu-id="3de6c-114">Remarks</span></span>

<span data-ttu-id="3de6c-115">セクション名>要素は、セクション>要素要素の[**\<タグ**](section-element.md)によって定義される**\<**[**\<カスタム要素>。**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="3de6c-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="3de6c-116">構成システムは、<xref:System.Collections.IDictionary>を呼び出<xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>すとオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3de6c-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="3de6c-117">例</span><span class="sxs-lookup"><span data-stu-id="3de6c-117">Example</span></span>

<span data-ttu-id="3de6c-118">次の例では、クラスによって読み取られた設定を含む**\<sampleSection>** と呼ばれるカスタム要素を<xref:System.Configuration.SingleTagSectionHandler>宣言します。</span><span class="sxs-lookup"><span data-stu-id="3de6c-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="3de6c-119">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="3de6c-119">Configuration file</span></span>

<span data-ttu-id="3de6c-120">この要素は、アプリケーションディレクトリレベルではないアプリケーション構成ファイル、マシン構成ファイル (*Machine.config*) および*Web.config*ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3de6c-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="3de6c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3de6c-121">See also</span></span>

- [<span data-ttu-id="3de6c-122">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="3de6c-122">Configuration file schema for the .NET Framework</span></span>](index.md)
