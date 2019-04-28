---
title: <clear>appSettings&gt;の<configSections>add&gt;要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d824ae828dd025f3292990facaa5e423add9c282
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705351"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="6d8dd-102">\<クリア > 要素の\<configSections ></span><span class="sxs-lookup"><span data-stu-id="6d8dd-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="6d8dd-103">以前に定義されたセクションおよびセクション グループのすべてをクリアします。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="6d8dd-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6d8dd-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6d8dd-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6d8dd-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="6d8dd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="6d8dd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6d8dd-107">構文</span><span class="sxs-lookup"><span data-stu-id="6d8dd-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="6d8dd-108">属性</span><span class="sxs-lookup"><span data-stu-id="6d8dd-108">Attribute</span></span>

|           | <span data-ttu-id="6d8dd-109">説明</span><span class="sxs-lookup"><span data-stu-id="6d8dd-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6d8dd-110">**name**</span><span class="sxs-lookup"><span data-stu-id="6d8dd-110">**name**</span></span>  | <span data-ttu-id="6d8dd-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-111">Required attribute.</span></span><br><br><span data-ttu-id="6d8dd-112">セクションまたは削除するセクション グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6d8dd-113">親要素</span><span class="sxs-lookup"><span data-stu-id="6d8dd-113">Parent element</span></span>

|     | <span data-ttu-id="6d8dd-114">説明</span><span class="sxs-lookup"><span data-stu-id="6d8dd-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6d8dd-115">**\<configSections >** 要素</span><span class="sxs-lookup"><span data-stu-id="6d8dd-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="6d8dd-116">構成セクションと名前空間宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6d8dd-117">子要素</span><span class="sxs-lookup"><span data-stu-id="6d8dd-117">Child elements</span></span>

<span data-ttu-id="6d8dd-118">なし</span><span class="sxs-lookup"><span data-stu-id="6d8dd-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6d8dd-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d8dd-119">Remarks</span></span>

<span data-ttu-id="6d8dd-120">**\<オフ >** 要素、または構成ファイル階層内の上位レベルにある現在の構成ファイルで既に定義されているアプリケーションからすべてのセクションおよびセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="6d8dd-121">例</span><span class="sxs-lookup"><span data-stu-id="6d8dd-121">Example</span></span>

<span data-ttu-id="6d8dd-122">この例は、マシン構成ファイルと、アプリケーション構成ファイルを定義しを使用する方法を示しています、 **\<オフ >** セクションで以前に定義を解除する、アプリケーション構成ファイル内の要素、マシン構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="6d8dd-123">マシン構成ファイルのコードは、次は、2 つのセクションを宣言します **\<sampleSection >** と **\<anotherSampleSection >**、アプリケーションを読んでいる。構成ファイル:</span><span class="sxs-lookup"><span data-stu-id="6d8dd-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="6d8dd-124">次のアプリケーション構成ファイルのコードでは、以前に宣言されたすべてのセクションをクリアします。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="6d8dd-125">アプリケーションがコンピューターの構成ファイルで宣言されたセクションのいずれかの設定を取得または使用できません。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="6d8dd-126">ただしから設定を使用して、  **\<anotherSection >** 後を備えているため、 **\<をオフに >** 要素。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="6d8dd-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="6d8dd-127">Configuration file</span></span>

<span data-ttu-id="6d8dd-128">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="6d8dd-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d8dd-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d8dd-129">See also</span></span>

- [<span data-ttu-id="6d8dd-130">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6d8dd-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
