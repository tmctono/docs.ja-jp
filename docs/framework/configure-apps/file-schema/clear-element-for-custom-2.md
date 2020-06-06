---
title: <clear>NameValueSectionHandler および DictionarySectionHandler の要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214750"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="96860-102">\<clear>NameValueSectionHandler および DictionarySectionHandler の要素</span><span class="sxs-lookup"><span data-stu-id="96860-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="96860-103">セクションで以前に定義したすべての設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="96860-103">Clears all previously defined settings in a section.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="96860-104">構文</span><span class="sxs-lookup"><span data-stu-id="96860-104">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="96860-105">属性</span><span class="sxs-lookup"><span data-stu-id="96860-105">Attributes</span></span>

<span data-ttu-id="96860-106">なし</span><span class="sxs-lookup"><span data-stu-id="96860-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="96860-107">親要素</span><span class="sxs-lookup"><span data-stu-id="96860-107">Parent element</span></span>

|     | <span data-ttu-id="96860-108">説明</span><span class="sxs-lookup"><span data-stu-id="96860-108">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="96860-109">**\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="96860-109">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="96860-110">クラスおよびクラスを使用するカスタム構成セクションの設定を定義し <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="96860-110">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="96860-111">子要素</span><span class="sxs-lookup"><span data-stu-id="96860-111">Child elements</span></span>

<span data-ttu-id="96860-112">なし</span><span class="sxs-lookup"><span data-stu-id="96860-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="96860-113">解説</span><span class="sxs-lookup"><span data-stu-id="96860-113">Remarks</span></span>

<span data-ttu-id="96860-114">要素を使用して、 **\<clear>** 構成ファイル階層の上位レベルで定義されているすべての設定をアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="96860-114">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="96860-115">例</span><span class="sxs-lookup"><span data-stu-id="96860-115">Example</span></span>

<span data-ttu-id="96860-116">この例では、コンピューター構成ファイルとアプリケーション構成ファイルを定義し、 **\<clear>** アプリケーション構成ファイルで要素を使用して、マシン構成ファイルで以前に定義したセクションをクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="96860-116">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="96860-117">次のマシン構成ファイルのコードでは、セクションを宣言してい **\<mySection>** ます。</span><span class="sxs-lookup"><span data-stu-id="96860-117">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="96860-118">次のアプリケーション構成ファイルのコードは、からすべての設定を削除し **\<mySection>** ます。</span><span class="sxs-lookup"><span data-stu-id="96860-118">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="96860-119">アプリケーションは、 **\<mySection>** コンピューター構成ファイルのセクションので宣言された設定を取得できません。</span><span class="sxs-lookup"><span data-stu-id="96860-119">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="96860-120">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="96860-120">Configuration file</span></span>

<span data-ttu-id="96860-121">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="96860-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="96860-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="96860-122">See also</span></span>

- [<span data-ttu-id="96860-123">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="96860-123">Configuration file schema for the .NET Framework</span></span>](index.md)
