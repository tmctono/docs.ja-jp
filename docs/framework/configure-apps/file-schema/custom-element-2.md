---
title: NameValueSectionHandler および DictionarySectionHandler の Custom 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d73c07d58bb226346cb99a1fe50b12bb0e7e746e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118540"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="af9ee-102">NameValueSectionHandler および DictionarySectionHandler の Custom 要素</span><span class="sxs-lookup"><span data-stu-id="af9ee-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="af9ee-103"><xref:System.Configuration.NameValueSectionHandler> クラスと <xref:System.Configuration.DictionarySectionHandler> クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="af9ee-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="af9ee-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af9ee-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="af9ee-105">&nbsp;&nbsp; **\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="af9ee-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="af9ee-106">属性</span><span class="sxs-lookup"><span data-stu-id="af9ee-106">Attributes</span></span>

<span data-ttu-id="af9ee-107">None</span><span class="sxs-lookup"><span data-stu-id="af9ee-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="af9ee-108">親要素</span><span class="sxs-lookup"><span data-stu-id="af9ee-108">Parent element</span></span>

|     | <span data-ttu-id="af9ee-109">説明</span><span class="sxs-lookup"><span data-stu-id="af9ee-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="af9ee-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="af9ee-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="af9ee-111">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="af9ee-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="af9ee-112">子要素</span><span class="sxs-lookup"><span data-stu-id="af9ee-112">Child elements</span></span>

|     | <span data-ttu-id="af9ee-113">説明</span><span class="sxs-lookup"><span data-stu-id="af9ee-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="af9ee-114"><xref:System.Configuration.NameValueSectionHandler> および <xref:System.Configuration.DictionarySectionHandler> の[ **> を追加\<** ](add-element-for-custom-2.md)には</span><span class="sxs-lookup"><span data-stu-id="af9ee-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="af9ee-115">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="af9ee-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="af9ee-116"><xref:System.Configuration.NameValueSectionHandler> および <xref:System.Configuration.DictionarySectionHandler> の[ **> を削除\<** ](remove-element-for-custom-2.md)には</span><span class="sxs-lookup"><span data-stu-id="af9ee-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="af9ee-117">以前に定義した設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="af9ee-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="af9ee-118"><xref:System.Configuration.NameValueSectionHandler> および <xref:System.Configuration.DictionarySectionHandler> の[ **> をクリア\<** ](clear-element-for-custom-2.md)には</span><span class="sxs-lookup"><span data-stu-id="af9ee-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="af9ee-119">セクションで以前に定義したすべての設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="af9ee-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="af9ee-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="af9ee-120">Remarks</span></span>

<span data-ttu-id="af9ee-121">**\<sectionName >** 要素は、 **\<configsections >** 要素の **\<セクション >** タグで定義されたカスタム要素です。</span><span class="sxs-lookup"><span data-stu-id="af9ee-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="af9ee-122">次の表は、ConfigurationSettings. GetConfig メソッドが各構成セクションハンドラーに対して返すオブジェクトの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="af9ee-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="af9ee-123">構成セクションハンドラー</span><span class="sxs-lookup"><span data-stu-id="af9ee-123">Configuration section handler</span></span>                        | <span data-ttu-id="af9ee-124">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="af9ee-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="af9ee-125">例</span><span class="sxs-lookup"><span data-stu-id="af9ee-125">Example</span></span>

<span data-ttu-id="af9ee-126">次の例は、<xref:System.Configuration.DictionarySectionHandler> クラスと <xref:System.Configuration.NameValueSectionHandler> クラスを使用するセクションを宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="af9ee-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="af9ee-127">最初のカスタム要素は **\<dictionarySample >** です。これには、`System.dll` アセンブリの <xref:System.Configuration.DictionarySectionHandler> クラスによって読み込まれる設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="af9ee-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="af9ee-128">2番目のカスタム要素は、`System.dll` アセンブリの <xref:System.Configuration.NameValueSectionHandler> クラスによって読み取られた設定を含む**mySection >\<** ます。</span><span class="sxs-lookup"><span data-stu-id="af9ee-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="af9ee-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="af9ee-129">Configuration file</span></span>

<span data-ttu-id="af9ee-130">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="af9ee-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="af9ee-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="af9ee-131">See also</span></span>

- [<span data-ttu-id="af9ee-132">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="af9ee-132">Configuration file schema for the .NET Framework</span></span>](index.md)
