---
title: <remove>NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214755"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="56970-102">\<remove>NameValueSectionHandler および DictionarySectionHandler の要素</span><span class="sxs-lookup"><span data-stu-id="56970-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="56970-103">以前に定義した設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="56970-103">Removes a previously defined setting.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="56970-104">構文</span><span class="sxs-lookup"><span data-stu-id="56970-104">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="56970-105">属性</span><span class="sxs-lookup"><span data-stu-id="56970-105">Attribute</span></span>

|           | <span data-ttu-id="56970-106">説明</span><span class="sxs-lookup"><span data-stu-id="56970-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="56970-107">**key**</span><span class="sxs-lookup"><span data-stu-id="56970-107">**key**</span></span>   | <span data-ttu-id="56970-108">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="56970-108">Required attribute.</span></span><br><br><span data-ttu-id="56970-109">削除する設定の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="56970-109">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="56970-110">親要素</span><span class="sxs-lookup"><span data-stu-id="56970-110">Parent element</span></span>

| <span data-ttu-id="56970-111">要素</span><span class="sxs-lookup"><span data-stu-id="56970-111">Element</span></span> | <span data-ttu-id="56970-112">Description</span><span class="sxs-lookup"><span data-stu-id="56970-112">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="56970-113">**\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="56970-113">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="56970-114">クラスおよびクラスを使用するカスタム構成セクションの設定を定義し <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="56970-114">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="56970-115">子要素</span><span class="sxs-lookup"><span data-stu-id="56970-115">Child elements</span></span>

<span data-ttu-id="56970-116">なし</span><span class="sxs-lookup"><span data-stu-id="56970-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="56970-117">解説</span><span class="sxs-lookup"><span data-stu-id="56970-117">Remarks</span></span>

<span data-ttu-id="56970-118">要素を使用して、 **\<remove>** 構成ファイル階層の上位レベルで定義されているアプリケーションから設定を削除できます。</span><span class="sxs-lookup"><span data-stu-id="56970-118">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="56970-119">例</span><span class="sxs-lookup"><span data-stu-id="56970-119">Example</span></span>

<span data-ttu-id="56970-120">次の例は、 **\<remove>** アプリケーション構成ファイルで要素を使用して、マシン構成ファイルで以前に定義した設定を削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="56970-120">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="56970-121">次のマシン構成ファイルのコードでは、セクションを宣言 **\<mySection>** し、2つの設定 ( `key1` と `key2` ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="56970-121">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="56970-122">次のアプリケーション構成ファイルのコードは、から設定を削除し `key2` **\<mySection>** ます。</span><span class="sxs-lookup"><span data-stu-id="56970-122">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="56970-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="56970-123">Configuration file</span></span>

<span data-ttu-id="56970-124">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="56970-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="56970-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="56970-125">See also</span></span>

- [<span data-ttu-id="56970-126">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="56970-126">Configuration file schema for the .NET Framework</span></span>](index.md)
