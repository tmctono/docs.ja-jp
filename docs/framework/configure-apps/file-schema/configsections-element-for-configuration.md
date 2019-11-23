---
title: <configSections> の <configuration> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6024144b6f12df22369366f04c3cbad02c5011d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119016"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="133bb-102">\<> 構成の \<configSections > 要素</span><span class="sxs-lookup"><span data-stu-id="133bb-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="133bb-103">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="133bb-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="133bb-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="133bb-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="133bb-105">&nbsp;&nbsp; **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="133bb-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="133bb-106">属性</span><span class="sxs-lookup"><span data-stu-id="133bb-106">Attributes</span></span>

<span data-ttu-id="133bb-107">なし</span><span class="sxs-lookup"><span data-stu-id="133bb-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="133bb-108">親要素</span><span class="sxs-lookup"><span data-stu-id="133bb-108">Parent element</span></span>

|     | <span data-ttu-id="133bb-109">説明</span><span class="sxs-lookup"><span data-stu-id="133bb-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="133bb-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="133bb-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="133bb-111">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="133bb-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="133bb-112">子要素</span><span class="sxs-lookup"><span data-stu-id="133bb-112">Child elements</span></span>

|     | <span data-ttu-id="133bb-113">説明</span><span class="sxs-lookup"><span data-stu-id="133bb-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="133bb-114"> **\<セクション >** </span><span class="sxs-lookup"><span data-stu-id="133bb-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="133bb-115">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="133bb-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="133bb-116"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="133bb-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="133bb-117">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="133bb-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="133bb-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="133bb-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="133bb-119">定義済みのセクション、またはセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="133bb-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="133bb-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="133bb-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="133bb-121">以前に定義したセクションとセクショングループをすべて消去します。</span><span class="sxs-lookup"><span data-stu-id="133bb-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="133bb-122">コメント</span><span class="sxs-lookup"><span data-stu-id="133bb-122">Remarks</span></span>

<span data-ttu-id="133bb-123">この要素が構成ファイル内にある場合は、 **\<configuration >** 要素の最初の子要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="133bb-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="133bb-124">例</span><span class="sxs-lookup"><span data-stu-id="133bb-124">Example</span></span>

<span data-ttu-id="133bb-125">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="133bb-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="133bb-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="133bb-126">Configuration file</span></span>

<span data-ttu-id="133bb-127">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="133bb-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="133bb-128">参照</span><span class="sxs-lookup"><span data-stu-id="133bb-128">See also</span></span>

- [<span data-ttu-id="133bb-129">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="133bb-129">Configuration file schema for the .NET Framework</span></span>](index.md)
