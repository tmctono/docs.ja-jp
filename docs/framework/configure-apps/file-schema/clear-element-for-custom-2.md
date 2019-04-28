---
title: <clear> NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: ad3ac93b2a7f92cd33787620fc0caa2b632aa072
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705364"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="0af9d-102">\<クリア > NameValueSectionHandler および DictionarySectionHandler の要素</span><span class="sxs-lookup"><span data-stu-id="0af9d-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="0af9d-103">セクション内のすべての以前に定義された設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="0af9d-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="0af9d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0af9d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0af9d-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="0af9d-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="0af9d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="0af9d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0af9d-107">構文</span><span class="sxs-lookup"><span data-stu-id="0af9d-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="0af9d-108">属性</span><span class="sxs-lookup"><span data-stu-id="0af9d-108">Attributes</span></span>

<span data-ttu-id="0af9d-109">なし</span><span class="sxs-lookup"><span data-stu-id="0af9d-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0af9d-110">親要素</span><span class="sxs-lookup"><span data-stu-id="0af9d-110">Parent element</span></span>

|     | <span data-ttu-id="0af9d-111">説明</span><span class="sxs-lookup"><span data-stu-id="0af9d-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="0af9d-112">**\<sectionName >** 要素</span><span class="sxs-lookup"><span data-stu-id="0af9d-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="0af9d-113">使用して、カスタム構成セクションの設定を定義、<xref:System.Configuration.NameValueSectionHandler>と<xref:System.Configuration.DictionarySectionHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="0af9d-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0af9d-114">子要素</span><span class="sxs-lookup"><span data-stu-id="0af9d-114">Child elements</span></span>

<span data-ttu-id="0af9d-115">なし</span><span class="sxs-lookup"><span data-stu-id="0af9d-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0af9d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="0af9d-116">Remarks</span></span>

<span data-ttu-id="0af9d-117">使用することができます、 **\<オフ >** 構成ファイル階層内の上位レベルで定義されているアプリケーションからすべての設定を削除する要素。</span><span class="sxs-lookup"><span data-stu-id="0af9d-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="0af9d-118">例</span><span class="sxs-lookup"><span data-stu-id="0af9d-118">Example</span></span>

<span data-ttu-id="0af9d-119">この例は、マシン構成ファイルと、アプリケーション構成ファイルを定義しを使用する方法を示しています、 **\<オフ >** セクションで以前に定義を解除する、アプリケーション構成ファイル内の要素、マシン構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="0af9d-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="0af9d-120">マシン構成ファイルのコードは、次のセクションを宣言します **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="0af9d-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="0af9d-121">次のアプリケーション構成ファイルのコードからすべての設定を削除します **\<mySection >** します。</span><span class="sxs-lookup"><span data-stu-id="0af9d-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="0af9d-122">アプリケーションを取得できませんで宣言されていた設定のいずれかで、  **\<mySection >** マシン構成ファイルのセクション。</span><span class="sxs-lookup"><span data-stu-id="0af9d-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="0af9d-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0af9d-123">Configuration file</span></span>

<span data-ttu-id="0af9d-124">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="0af9d-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0af9d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="0af9d-125">See also</span></span>

- [<span data-ttu-id="0af9d-126">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="0af9d-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
