---
title: <clear>appSettings&gt;の<configSections>add&gt;要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: e79def513637937262d00b0edb1b0f7676fd120b
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300803"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="4e569-102">\<クリア > 要素の\<configSections ></span><span class="sxs-lookup"><span data-stu-id="4e569-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="4e569-103">以前に定義されたセクションおよびセクション グループのすべてをクリアします。</span><span class="sxs-lookup"><span data-stu-id="4e569-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="4e569-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4e569-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="4e569-105">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="4e569-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="4e569-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="4e569-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4e569-107">構文</span><span class="sxs-lookup"><span data-stu-id="4e569-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="4e569-108">属性</span><span class="sxs-lookup"><span data-stu-id="4e569-108">Attribute</span></span>

|           | <span data-ttu-id="4e569-109">説明</span><span class="sxs-lookup"><span data-stu-id="4e569-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="4e569-110">**name**</span><span class="sxs-lookup"><span data-stu-id="4e569-110">**name**</span></span>  | <span data-ttu-id="4e569-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4e569-111">Required attribute.</span></span><br><br><span data-ttu-id="4e569-112">セクションまたは削除するセクション グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e569-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="4e569-113">親要素</span><span class="sxs-lookup"><span data-stu-id="4e569-113">Parent element</span></span>

|     | <span data-ttu-id="4e569-114">説明</span><span class="sxs-lookup"><span data-stu-id="4e569-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4e569-115"> *\*\<configSections >** 要素</span><span class="sxs-lookup"><span data-stu-id="4e569-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="4e569-116">構成セクションと名前空間宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e569-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4e569-117">子要素</span><span class="sxs-lookup"><span data-stu-id="4e569-117">Child elements</span></span>

<span data-ttu-id="4e569-118">なし</span><span class="sxs-lookup"><span data-stu-id="4e569-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="4e569-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="4e569-119">Remarks</span></span>

<span data-ttu-id="4e569-120">**\<オフ >** 要素、または構成ファイル階層内の上位レベルにある現在の構成ファイルで既に定義されているアプリケーションからすべてのセクションおよびセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e569-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="4e569-121">例</span><span class="sxs-lookup"><span data-stu-id="4e569-121">Example</span></span>

<span data-ttu-id="4e569-122">この例は、マシン構成ファイルと、アプリケーション構成ファイルを定義しを使用する方法を示しています、 **\<オフ >** セクションで以前に定義を解除する、アプリケーション構成ファイル内の要素、マシン構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="4e569-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="4e569-123">マシン構成ファイルのコードは、次は、2 つのセクションを宣言します **\<sampleSection >** と **\<anotherSampleSection >** 、アプリケーションを読んでいる。構成ファイル:</span><span class="sxs-lookup"><span data-stu-id="4e569-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="4e569-124">次のアプリケーション構成ファイルのコードでは、以前に宣言されたすべてのセクションをクリアします。</span><span class="sxs-lookup"><span data-stu-id="4e569-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="4e569-125">アプリケーションがコンピューターの構成ファイルで宣言されたセクションのいずれかの設定を取得または使用できません。</span><span class="sxs-lookup"><span data-stu-id="4e569-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="4e569-126">ただしから設定を使用して、  **\<anotherSection >** 後を備えているため、 **\<をオフに >** 要素。</span><span class="sxs-lookup"><span data-stu-id="4e569-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="4e569-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="4e569-127">Configuration file</span></span>

<span data-ttu-id="4e569-128">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="4e569-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e569-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e569-129">See also</span></span>

- [<span data-ttu-id="4e569-130">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4e569-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
