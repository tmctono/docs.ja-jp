---
title: <configSections> の <clear> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155428"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="9c141-102">\<configSections> の \<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="9c141-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="9c141-103">以前に定義したセクションとセクショングループをすべて消去します。</span><span class="sxs-lookup"><span data-stu-id="9c141-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="9c141-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="9c141-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9c141-105">構文</span><span class="sxs-lookup"><span data-stu-id="9c141-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="9c141-106">属性</span><span class="sxs-lookup"><span data-stu-id="9c141-106">Attribute</span></span>

|           | <span data-ttu-id="9c141-107">説明</span><span class="sxs-lookup"><span data-stu-id="9c141-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="9c141-108">**name**</span><span class="sxs-lookup"><span data-stu-id="9c141-108">**name**</span></span>  | <span data-ttu-id="9c141-109">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9c141-109">Required attribute.</span></span><br><br><span data-ttu-id="9c141-110">削除するセクションまたはセクショングループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c141-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="9c141-111">親要素</span><span class="sxs-lookup"><span data-stu-id="9c141-111">Parent element</span></span>

|     | <span data-ttu-id="9c141-112">説明</span><span class="sxs-lookup"><span data-stu-id="9c141-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9c141-113">**\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="9c141-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="9c141-114">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c141-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9c141-115">子要素</span><span class="sxs-lookup"><span data-stu-id="9c141-115">Child elements</span></span>

<span data-ttu-id="9c141-116">なし</span><span class="sxs-lookup"><span data-stu-id="9c141-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="9c141-117">解説</span><span class="sxs-lookup"><span data-stu-id="9c141-117">Remarks</span></span>

<span data-ttu-id="9c141-118">要素は、 **\<clear>** アプリケーションから、現在の構成ファイルまたは構成ファイル階層の上位レベルに定義されたすべてのセクションとセクショングループを削除します。</span><span class="sxs-lookup"><span data-stu-id="9c141-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="9c141-119">例</span><span class="sxs-lookup"><span data-stu-id="9c141-119">Example</span></span>

<span data-ttu-id="9c141-120">この例では、コンピューター構成ファイルとアプリケーション構成ファイルを定義し、 **\<clear>** アプリケーション構成ファイルで要素を使用して、マシン構成ファイルで以前に定義したセクションをクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9c141-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="9c141-121">次のマシン構成ファイルのコードでは、とという2つのセクションを宣言 **\<sampleSection>** して **\<anotherSampleSection>** います。これらは、アプリケーション構成ファイルの前に読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="9c141-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="9c141-122">次のアプリケーション構成ファイルのコードは、以前に宣言されたすべてのセクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="9c141-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="9c141-123">アプリケーションでは、コンピューターの構成ファイルで宣言されているセクションのいずれかで設定を使用または取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="9c141-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="9c141-124">ただし、要素の後に来るため、の設定を使用でき **\<anotherSection>** **\<clear>** ます。</span><span class="sxs-lookup"><span data-stu-id="9c141-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="9c141-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="9c141-125">Configuration file</span></span>

<span data-ttu-id="9c141-126">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c141-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c141-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c141-127">See also</span></span>

- [<span data-ttu-id="9c141-128">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="9c141-128">Configuration file schema for the .NET Framework</span></span>](index.md)
