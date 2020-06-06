---
title: <add>NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215435"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="c2d30-102">\<add>NameValueSectionHandler および DictionarySectionHandler の要素</span><span class="sxs-lookup"><span data-stu-id="c2d30-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="c2d30-103">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2d30-103">Adds custom application settings.</span></span> <span data-ttu-id="c2d30-104">各 **\<add>** タグには、キーと値のペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2d30-104">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="c2d30-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2d30-105">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="c2d30-106">属性</span><span class="sxs-lookup"><span data-stu-id="c2d30-106">Attributes</span></span>

| <span data-ttu-id="c2d30-107">属性</span><span class="sxs-lookup"><span data-stu-id="c2d30-107">Attribute</span></span> | <span data-ttu-id="c2d30-108">説明</span><span class="sxs-lookup"><span data-stu-id="c2d30-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c2d30-109">**key**</span><span class="sxs-lookup"><span data-stu-id="c2d30-109">**key**</span></span>   | <span data-ttu-id="c2d30-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c2d30-110">Required attribute.</span></span><br><br><span data-ttu-id="c2d30-111">設定の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2d30-111">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="c2d30-112">**value**</span><span class="sxs-lookup"><span data-stu-id="c2d30-112">**value**</span></span> | <span data-ttu-id="c2d30-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c2d30-113">Required attribute.</span></span><br><br><span data-ttu-id="c2d30-114">設定の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2d30-114">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="c2d30-115">親要素</span><span class="sxs-lookup"><span data-stu-id="c2d30-115">Parent element</span></span>

| <span data-ttu-id="c2d30-116">要素</span><span class="sxs-lookup"><span data-stu-id="c2d30-116">Element</span></span> | <span data-ttu-id="c2d30-117">Description</span><span class="sxs-lookup"><span data-stu-id="c2d30-117">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="c2d30-118">**\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="c2d30-118">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="c2d30-119">クラスおよびクラスを使用するカスタム構成セクションの設定を定義し <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="c2d30-119">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c2d30-120">子要素</span><span class="sxs-lookup"><span data-stu-id="c2d30-120">Child elements</span></span>

<span data-ttu-id="c2d30-121">なし</span><span class="sxs-lookup"><span data-stu-id="c2d30-121">None</span></span>

## <a name="example"></a><span data-ttu-id="c2d30-122">例</span><span class="sxs-lookup"><span data-stu-id="c2d30-122">Example</span></span>

<span data-ttu-id="c2d30-123">次の例は、カスタム構成セクションを定義し、要素を使用して設定をセクションに格納する方法を示してい **\<add>** ます。</span><span class="sxs-lookup"><span data-stu-id="c2d30-123">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c2d30-124">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c2d30-124">Configuration file</span></span>

<span data-ttu-id="c2d30-125">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2d30-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2d30-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2d30-126">See also</span></span>

- [<span data-ttu-id="c2d30-127">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="c2d30-127">Configuration file schema for the .NET Framework</span></span>](index.md)
