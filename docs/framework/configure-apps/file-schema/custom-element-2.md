---
title: NameValueSectionHandler および DictionarySectionHandler の Custom 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921035"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="11c4c-102">NameValueSectionHandler および DictionarySectionHandler の Custom 要素</span><span class="sxs-lookup"><span data-stu-id="11c4c-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="11c4c-103">クラス<xref:System.Configuration.NameValueSectionHandler> および<xref:System.Configuration.DictionarySectionHandler>クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="11c4c-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="11c4c-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="11c4c-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="11c4c-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="11c4c-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="11c4c-106">属性</span><span class="sxs-lookup"><span data-stu-id="11c4c-106">Attributes</span></span>

<span data-ttu-id="11c4c-107">なし</span><span class="sxs-lookup"><span data-stu-id="11c4c-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="11c4c-108">親要素</span><span class="sxs-lookup"><span data-stu-id="11c4c-108">Parent element</span></span>

|     | <span data-ttu-id="11c4c-109">説明</span><span class="sxs-lookup"><span data-stu-id="11c4c-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="11c4c-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="11c4c-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="11c4c-111">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="11c4c-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="11c4c-112">子要素</span><span class="sxs-lookup"><span data-stu-id="11c4c-112">Child elements</span></span>

|     | <span data-ttu-id="11c4c-113">説明</span><span class="sxs-lookup"><span data-stu-id="11c4c-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="11c4c-114">およびの<xref:System.Configuration.NameValueSectionHandler> > を[ **\<追加**](add-element-for-custom-2.md)します。<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="11c4c-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="11c4c-115">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="11c4c-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="11c4c-116">およびの<xref:System.Configuration.NameValueSectionHandler> > を[ **\<削除**](remove-element-for-custom-2.md)します。<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="11c4c-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="11c4c-117">以前に定義した設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="11c4c-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="11c4c-118">およびの<xref:System.Configuration.NameValueSectionHandler> > を[ **\<クリア**](clear-element-for-custom-2.md)します。<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="11c4c-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="11c4c-119">セクションで以前に定義したすべての設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="11c4c-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="11c4c-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="11c4c-120">Remarks</span></span>

<span data-ttu-id="11c4c-121">**\<SectionName>** 要素がによって定義されるカスタム要素、  **\<セクション>** にタグを付ける、  **\<configSections>** 要素。</span><span class="sxs-lookup"><span data-stu-id="11c4c-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="11c4c-122">次の表は、ConfigurationSettings. GetConfig メソッドが各構成セクションハンドラーに対して返すオブジェクトの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="11c4c-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="11c4c-123">構成セクションハンドラー</span><span class="sxs-lookup"><span data-stu-id="11c4c-123">Configuration section handler</span></span>                        | <span data-ttu-id="11c4c-124">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="11c4c-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="11c4c-125">例</span><span class="sxs-lookup"><span data-stu-id="11c4c-125">Example</span></span>

<span data-ttu-id="11c4c-126">次の例は、クラス<xref:System.Configuration.DictionarySectionHandler>と<xref:System.Configuration.NameValueSectionHandler>クラスを使用するセクションを宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="11c4c-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="11c4c-127">最初のカスタム要素は、 `System.dll`アセンブリ内の<xref:System.Configuration.DictionarySectionHandler>クラスによって読み取られた設定を含む **\<dictionarySample >** です。</span><span class="sxs-lookup"><span data-stu-id="11c4c-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="11c4c-128">2番目のカスタム要素は **\<mysection >** です。この要素に<xref:System.Configuration.NameValueSectionHandler>は、 `System.dll`アセンブリのクラスによって読み込まれる設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="11c4c-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="11c4c-129">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="11c4c-129">Configuration file</span></span>

<span data-ttu-id="11c4c-130">この要素は、アプリケーション構成ファイル、コンピューター構成ファイル (machine.config)、およびアプリケーションディレクトリレベルではない web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="11c4c-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="11c4c-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="11c4c-131">See also</span></span>

- [<span data-ttu-id="11c4c-132">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="11c4c-132">Configuration file schema for the .NET Framework</span></span>](index.md)
