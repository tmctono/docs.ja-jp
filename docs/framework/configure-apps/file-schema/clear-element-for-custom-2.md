---
title: <clear>NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: fbb689db4abc5d59729d9a4d9807a02a0983d40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927706"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="2872f-102">\<NameValueSectionHandler および DictionarySectionHandler の > 要素をクリアします</span><span class="sxs-lookup"><span data-stu-id="2872f-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="2872f-103">セクションで以前に定義したすべての設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="2872f-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="2872f-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2872f-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="2872f-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="2872f-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="2872f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="2872f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2872f-107">構文</span><span class="sxs-lookup"><span data-stu-id="2872f-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="2872f-108">属性</span><span class="sxs-lookup"><span data-stu-id="2872f-108">Attributes</span></span>

<span data-ttu-id="2872f-109">なし</span><span class="sxs-lookup"><span data-stu-id="2872f-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="2872f-110">親要素</span><span class="sxs-lookup"><span data-stu-id="2872f-110">Parent element</span></span>

|     | <span data-ttu-id="2872f-111">説明</span><span class="sxs-lookup"><span data-stu-id="2872f-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="2872f-112">sectionname > 要素 **\<** </span><span class="sxs-lookup"><span data-stu-id="2872f-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="2872f-113">クラス<xref:System.Configuration.NameValueSectionHandler> および<xref:System.Configuration.DictionarySectionHandler>クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="2872f-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2872f-114">子要素</span><span class="sxs-lookup"><span data-stu-id="2872f-114">Child elements</span></span>

<span data-ttu-id="2872f-115">なし</span><span class="sxs-lookup"><span data-stu-id="2872f-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="2872f-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="2872f-116">Remarks</span></span>

<span data-ttu-id="2872f-117">Clear > 要素を使用 **\<** して、構成ファイル階層の上位レベルで定義されているすべての設定をアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="2872f-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="2872f-118">例</span><span class="sxs-lookup"><span data-stu-id="2872f-118">Example</span></span>

<span data-ttu-id="2872f-119">この例では、コンピューター構成ファイルとアプリケーション構成ファイルを定義し、アプリケーション構成ファイルで **\<clear >** 要素を使用して、コンピューター構成で以前に定義したセクションをクリアする方法を示します。拡張子.</span><span class="sxs-lookup"><span data-stu-id="2872f-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="2872f-120">次のマシン構成ファイルのコードでは、セクション **\<mysection >** が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="2872f-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="2872f-121">次のアプリケーション構成ファイルコードは、  **\<mysection >** からすべての設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="2872f-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="2872f-122">アプリケーションは、  **\<** コンピューター構成ファイルの mysection > セクションので宣言された設定を取得できません。</span><span class="sxs-lookup"><span data-stu-id="2872f-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="2872f-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="2872f-123">Configuration file</span></span>

<span data-ttu-id="2872f-124">この要素は、アプリケーション構成ファイル、コンピューター構成ファイル (machine.config)、およびアプリケーションディレクトリレベルではない web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2872f-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2872f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="2872f-125">See also</span></span>

- [<span data-ttu-id="2872f-126">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="2872f-126">Configuration file schema for the .NET Framework</span></span>](index.md)
