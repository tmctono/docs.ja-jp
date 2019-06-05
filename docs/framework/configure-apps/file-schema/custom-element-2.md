---
title: NameValueSectionHandler および DictionarySectionHandler のカスタム要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8636050b2618d1b2c2da0c08c756b0ed221c7f6f
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300769"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="cb20e-102">NameValueSectionHandler および DictionarySectionHandler のカスタム要素</span><span class="sxs-lookup"><span data-stu-id="cb20e-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="cb20e-103">使用して、カスタム構成セクションの設定を定義、<xref:System.Configuration.NameValueSectionHandler>と<xref:System.Configuration.DictionarySectionHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="cb20e-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="cb20e-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span><span class="sxs-lookup"><span data-stu-id="cb20e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span></span>
<span data-ttu-id="cb20e-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="cb20e-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="cb20e-106">属性</span><span class="sxs-lookup"><span data-stu-id="cb20e-106">Attributes</span></span>

<span data-ttu-id="cb20e-107">なし</span><span class="sxs-lookup"><span data-stu-id="cb20e-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="cb20e-108">親要素</span><span class="sxs-lookup"><span data-stu-id="cb20e-108">Parent element</span></span>

|     | <span data-ttu-id="cb20e-109">説明</span><span class="sxs-lookup"><span data-stu-id="cb20e-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cb20e-110"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="cb20e-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="cb20e-111">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="cb20e-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cb20e-112">子要素</span><span class="sxs-lookup"><span data-stu-id="cb20e-112">Child elements</span></span>

|     | <span data-ttu-id="cb20e-113">説明</span><span class="sxs-lookup"><span data-stu-id="cb20e-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="cb20e-114">[ **\<追加 >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md)の<xref:System.Configuration.NameValueSectionHandler>と <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="cb20e-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="cb20e-115">カスタム アプリケーションの設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="cb20e-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="cb20e-116">[ **\<削除 >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md)の<xref:System.Configuration.NameValueSectionHandler>と <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="cb20e-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="cb20e-117">以前に定義された設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="cb20e-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="cb20e-118">[ **\<クリア >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md)の<xref:System.Configuration.NameValueSectionHandler>と <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="cb20e-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="cb20e-119">セクション内のすべての以前に定義された設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="cb20e-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cb20e-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb20e-120">Remarks</span></span>

<span data-ttu-id="cb20e-121"> *\*\<SectionName>** 要素がによって定義されるカスタム要素、  *\*\<セクション>** にタグを付ける、  *\*\<configSections>** 要素。</span><span class="sxs-lookup"><span data-stu-id="cb20e-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="cb20e-122">次の表は、各構成セクション ハンドラー オブジェクト ConfigurationSettings.GetConfig メソッドの型を返します。</span><span class="sxs-lookup"><span data-stu-id="cb20e-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="cb20e-123">構成セクション ハンドラー</span><span class="sxs-lookup"><span data-stu-id="cb20e-123">Configuration section handler</span></span>                        | <span data-ttu-id="cb20e-124">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="cb20e-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="cb20e-125">例</span><span class="sxs-lookup"><span data-stu-id="cb20e-125">Example</span></span>

<span data-ttu-id="cb20e-126">次の例を使用するセクションを宣言する方法を示しています、<xref:System.Configuration.DictionarySectionHandler>と<xref:System.Configuration.NameValueSectionHandler>クラス。</span><span class="sxs-lookup"><span data-stu-id="cb20e-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="cb20e-127">最初のカスタム要素は **\<dictionarySample >** 、によって読み取られた設定を含む、<xref:System.Configuration.DictionarySectionHandler>クラス、`System.dll`アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="cb20e-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="cb20e-128">2 番目のカスタム要素は **\<mySection >** 、によって読み取られた設定を含む、<xref:System.Configuration.NameValueSectionHandler>クラス、`System.dll`アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="cb20e-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="cb20e-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="cb20e-129">Configuration file</span></span>

<span data-ttu-id="cb20e-130">この要素は、アプリケーション構成ファイル、マシン構成ファイルで使用できます (*Machine.config*)、および*Web.config*アプリケーション ディレクトリ レベルではないファイル。</span><span class="sxs-lookup"><span data-stu-id="cb20e-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb20e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb20e-131">See also</span></span>

- [<span data-ttu-id="cb20e-132">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="cb20e-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
