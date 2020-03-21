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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155350"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="60946-102">\<構成>>要素\<</span><span class="sxs-lookup"><span data-stu-id="60946-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="60946-103">構成セクションと名前空間の宣言が含まれます。</span><span class="sxs-lookup"><span data-stu-id="60946-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="60946-104">&nbsp;[**\<構成>**](configuration-element.md)&nbsp;**構成セクション>\<**</span><span class="sxs-lookup"><span data-stu-id="60946-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="60946-105">属性</span><span class="sxs-lookup"><span data-stu-id="60946-105">Attributes</span></span>

<span data-ttu-id="60946-106">なし</span><span class="sxs-lookup"><span data-stu-id="60946-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="60946-107">親要素</span><span class="sxs-lookup"><span data-stu-id="60946-107">Parent element</span></span>

|     | <span data-ttu-id="60946-108">説明</span><span class="sxs-lookup"><span data-stu-id="60946-108">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="60946-109">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="60946-109">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="60946-110">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="60946-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="60946-111">子要素</span><span class="sxs-lookup"><span data-stu-id="60946-111">Child elements</span></span>

|     | <span data-ttu-id="60946-112">説明</span><span class="sxs-lookup"><span data-stu-id="60946-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="60946-113">**\<セクション>**</span><span class="sxs-lookup"><span data-stu-id="60946-113">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="60946-114">構成セクションの宣言を含みます。</span><span class="sxs-lookup"><span data-stu-id="60946-114">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="60946-115">**\<セクショングループ>**</span><span class="sxs-lookup"><span data-stu-id="60946-115">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="60946-116">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="60946-116">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="60946-117">**\<>を削除する**</span><span class="sxs-lookup"><span data-stu-id="60946-117">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="60946-118">定義済みのセクションまたはセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="60946-118">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="60946-119">**\<クリア>**</span><span class="sxs-lookup"><span data-stu-id="60946-119">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="60946-120">以前に定義したすべてのセクションおよびセクション グループをクリアします。</span><span class="sxs-lookup"><span data-stu-id="60946-120">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="60946-121">解説</span><span class="sxs-lookup"><span data-stu-id="60946-121">Remarks</span></span>

<span data-ttu-id="60946-122">この要素が構成ファイル内にある場合は、**\<要素の構成要素**の最初の子要素>必要があります。</span><span class="sxs-lookup"><span data-stu-id="60946-122">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="60946-123">例</span><span class="sxs-lookup"><span data-stu-id="60946-123">Example</span></span>

<span data-ttu-id="60946-124">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="60946-124">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="60946-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="60946-125">Configuration file</span></span>

<span data-ttu-id="60946-126">この要素は、アプリケーションディレクトリレベルではないアプリケーション構成ファイル、マシン構成ファイル (*Machine.config*) および*Web.config*ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="60946-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="60946-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="60946-127">See also</span></span>

- [<span data-ttu-id="60946-128">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="60946-128">Configuration file schema for the .NET Framework</span></span>](index.md)
