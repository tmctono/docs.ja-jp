---
title: <configuration> の <configSections> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155350"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="0d7ee-102">\<configuration> の \<configSections> 要素</span><span class="sxs-lookup"><span data-stu-id="0d7ee-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="0d7ee-103">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="0d7ee-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="0d7ee-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="0d7ee-105">属性</span><span class="sxs-lookup"><span data-stu-id="0d7ee-105">Attributes</span></span>

<span data-ttu-id="0d7ee-106">なし</span><span class="sxs-lookup"><span data-stu-id="0d7ee-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0d7ee-107">親要素</span><span class="sxs-lookup"><span data-stu-id="0d7ee-107">Parent element</span></span>

|     | <span data-ttu-id="0d7ee-108">説明</span><span class="sxs-lookup"><span data-stu-id="0d7ee-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="0d7ee-109">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0d7ee-110">子要素</span><span class="sxs-lookup"><span data-stu-id="0d7ee-110">Child elements</span></span>

|     | <span data-ttu-id="0d7ee-111">Description</span><span class="sxs-lookup"><span data-stu-id="0d7ee-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="0d7ee-112">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="0d7ee-113">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-113">Defines a namespace for configuration sections.</span></span> |
| [**\<remove>**](remove-element-for-configsections.md) | <span data-ttu-id="0d7ee-114">定義済みセクションまたはセクショングループを削除します。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-114">Removes a predefined section or section group.</span></span> |
| [**\<clear>**](clear-element-for-configsections.md) | <span data-ttu-id="0d7ee-115">以前に定義したセクションとセクショングループをすべて消去します。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-115">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0d7ee-116">解説</span><span class="sxs-lookup"><span data-stu-id="0d7ee-116">Remarks</span></span>

<span data-ttu-id="0d7ee-117">この要素が構成ファイル内にある場合は、要素の最初の子要素である必要があり **\<configuration>** ます。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-117">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="0d7ee-118">例</span><span class="sxs-lookup"><span data-stu-id="0d7ee-118">Example</span></span>

<span data-ttu-id="0d7ee-119">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-119">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0d7ee-120">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0d7ee-120">Configuration file</span></span>

<span data-ttu-id="0d7ee-121">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d7ee-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d7ee-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d7ee-122">See also</span></span>

- [<span data-ttu-id="0d7ee-123">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="0d7ee-123">Configuration file schema for the .NET Framework</span></span>](index.md)
