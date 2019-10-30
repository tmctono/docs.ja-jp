---
title: NameValueSectionHandler および DictionarySectionHandler の <remove> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc1519a794e24e04074dd2a674ecc2c0f3666521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118558"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="d2ac8-102">NameValueSectionHandler および DictionarySectionHandler の > 要素を削除 \<には</span><span class="sxs-lookup"><span data-stu-id="d2ac8-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="d2ac8-103">以前に定義した設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="d2ac8-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d2ac8-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="d2ac8-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="d2ac8-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="d2ac8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<削除**></span><span class="sxs-lookup"><span data-stu-id="d2ac8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d2ac8-107">構文</span><span class="sxs-lookup"><span data-stu-id="d2ac8-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="d2ac8-108">属性</span><span class="sxs-lookup"><span data-stu-id="d2ac8-108">Attribute</span></span>

|           | <span data-ttu-id="d2ac8-109">説明</span><span class="sxs-lookup"><span data-stu-id="d2ac8-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d2ac8-110">**key**</span><span class="sxs-lookup"><span data-stu-id="d2ac8-110">**key**</span></span>   | <span data-ttu-id="d2ac8-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-111">Required attribute.</span></span><br><br><span data-ttu-id="d2ac8-112">削除する設定の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d2ac8-113">親要素</span><span class="sxs-lookup"><span data-stu-id="d2ac8-113">Parent element</span></span>

| <span data-ttu-id="d2ac8-114">要素</span><span class="sxs-lookup"><span data-stu-id="d2ac8-114">Element</span></span> | <span data-ttu-id="d2ac8-115">説明</span><span class="sxs-lookup"><span data-stu-id="d2ac8-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="d2ac8-116"> **\<sectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="d2ac8-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="d2ac8-117"><xref:System.Configuration.NameValueSectionHandler> クラスと <xref:System.Configuration.DictionarySectionHandler> クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d2ac8-118">子要素</span><span class="sxs-lookup"><span data-stu-id="d2ac8-118">Child elements</span></span>

<span data-ttu-id="d2ac8-119">None</span><span class="sxs-lookup"><span data-stu-id="d2ac8-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="d2ac8-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2ac8-120">Remarks</span></span>

<span data-ttu-id="d2ac8-121">**\<remove >** 要素を使用して、構成ファイル階層の上位レベルで定義された設定をアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="d2ac8-122">例</span><span class="sxs-lookup"><span data-stu-id="d2ac8-122">Example</span></span>

<span data-ttu-id="d2ac8-123">次の例では、アプリケーション構成ファイルで **\<remove >** 要素を使用して、マシン構成ファイルで以前に定義した設定を削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="d2ac8-124">次のマシン構成ファイルコードでは、セクション **\<mysection >** を宣言し、`key1` と `key2`の2つの設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="d2ac8-125">次のアプリケーション構成ファイルのコードは、 **\<mySection >** から `key2` 設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="d2ac8-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="d2ac8-126">Configuration file</span></span>

<span data-ttu-id="d2ac8-127">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2ac8-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2ac8-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2ac8-128">See also</span></span>

- [<span data-ttu-id="d2ac8-129">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="d2ac8-129">Configuration file schema for the .NET Framework</span></span>](index.md)
