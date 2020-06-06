---
title: NameValueSectionHandler および DictionarySectionHandler の Custom 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215473"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ac233-102">NameValueSectionHandler および DictionarySectionHandler の Custom 要素</span><span class="sxs-lookup"><span data-stu-id="ac233-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ac233-103">クラスおよびクラスを使用するカスタム構成セクションの設定を定義し <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="ac233-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a><span data-ttu-id="ac233-104">属性</span><span class="sxs-lookup"><span data-stu-id="ac233-104">Attributes</span></span>

<span data-ttu-id="ac233-105">なし</span><span class="sxs-lookup"><span data-stu-id="ac233-105">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="ac233-106">親要素</span><span class="sxs-lookup"><span data-stu-id="ac233-106">Parent element</span></span>

|     | <span data-ttu-id="ac233-107">説明</span><span class="sxs-lookup"><span data-stu-id="ac233-107">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="ac233-108">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ac233-108">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ac233-109">子要素</span><span class="sxs-lookup"><span data-stu-id="ac233-109">Child elements</span></span>

|     | <span data-ttu-id="ac233-110">Description</span><span class="sxs-lookup"><span data-stu-id="ac233-110">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="ac233-111">[**\<add>**](add-element-for-custom-2.md)およびの場合 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ac233-111">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="ac233-112">カスタムアプリケーション設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac233-112">Adds custom application settings.</span></span> |
| <span data-ttu-id="ac233-113">[**\<remove>**](remove-element-for-custom-2.md)およびの場合 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ac233-113">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="ac233-114">以前に定義した設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="ac233-114">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="ac233-115">[**\<clear>**](clear-element-for-custom-2.md)およびの場合 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ac233-115">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="ac233-116">セクションで以前に定義したすべての設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="ac233-116">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ac233-117">解説</span><span class="sxs-lookup"><span data-stu-id="ac233-117">Remarks</span></span>

<span data-ttu-id="ac233-118">要素は、 **\<sectionName>** **\<section>** 要素内のタグによって定義されたカスタム要素です **\<configSections>** 。</span><span class="sxs-lookup"><span data-stu-id="ac233-118">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="ac233-119">次の表は、ConfigurationSettings. GetConfig メソッドが各構成セクションハンドラーに対して返すオブジェクトの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac233-119">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="ac233-120">構成セクションハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac233-120">Configuration section handler</span></span>                        | <span data-ttu-id="ac233-121">の戻り値の型 :</span><span class="sxs-lookup"><span data-stu-id="ac233-121">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="ac233-122">例</span><span class="sxs-lookup"><span data-stu-id="ac233-122">Example</span></span>

<span data-ttu-id="ac233-123">次の例は、クラスとクラスを使用するセクションを宣言する方法を示して <xref:System.Configuration.DictionarySectionHandler> <xref:System.Configuration.NameValueSectionHandler> います。</span><span class="sxs-lookup"><span data-stu-id="ac233-123">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="ac233-124">最初のカスタム要素はです。これには、 **\<dictionarySample>** <xref:System.Configuration.DictionarySectionHandler> アセンブリ内のクラスによって読み取られた設定が含まれ `System.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="ac233-124">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="ac233-125">2番目のカスタム要素はです。これには、 **\<mySection>** アセンブリ内のクラスによって読み取られた設定が含まれ <xref:System.Configuration.NameValueSectionHandler> `System.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="ac233-125">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ac233-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="ac233-126">Configuration file</span></span>

<span data-ttu-id="ac233-127">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac233-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac233-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac233-128">See also</span></span>

- [<span data-ttu-id="ac233-129">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="ac233-129">Configuration file schema for the .NET Framework</span></span>](index.md)
