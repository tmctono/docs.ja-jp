---
title: NameValueSectionHandler および DictionarySectionHandler の <clear> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214750"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="8f441-102">NameValueSectionHandler および DictionarySectionHandler の \<clear > 要素</span><span class="sxs-lookup"><span data-stu-id="8f441-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="8f441-103">セクションで以前に定義したすべての設定を消去します。</span><span class="sxs-lookup"><span data-stu-id="8f441-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="8f441-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f441-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="8f441-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="8f441-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="8f441-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="8f441-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8f441-107">構文</span><span class="sxs-lookup"><span data-stu-id="8f441-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="8f441-108">属性</span><span class="sxs-lookup"><span data-stu-id="8f441-108">Attributes</span></span>

<span data-ttu-id="8f441-109">なし</span><span class="sxs-lookup"><span data-stu-id="8f441-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="8f441-110">親要素</span><span class="sxs-lookup"><span data-stu-id="8f441-110">Parent element</span></span>

|     | <span data-ttu-id="8f441-111">説明</span><span class="sxs-lookup"><span data-stu-id="8f441-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="8f441-112"> **\<sectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="8f441-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="8f441-113"><xref:System.Configuration.NameValueSectionHandler> クラスと <xref:System.Configuration.DictionarySectionHandler> クラスを使用するカスタム構成セクションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f441-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8f441-114">子要素</span><span class="sxs-lookup"><span data-stu-id="8f441-114">Child elements</span></span>

<span data-ttu-id="8f441-115">なし</span><span class="sxs-lookup"><span data-stu-id="8f441-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8f441-116">コメント</span><span class="sxs-lookup"><span data-stu-id="8f441-116">Remarks</span></span>

<span data-ttu-id="8f441-117">**\<clear >** 要素を使用して、構成ファイル階層の上位レベルで定義されているすべての設定をアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="8f441-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="8f441-118">例</span><span class="sxs-lookup"><span data-stu-id="8f441-118">Example</span></span>

<span data-ttu-id="8f441-119">この例では、マシン構成ファイルとアプリケーション構成ファイルを定義し、アプリケーション構成ファイルで **\<clear >** 要素を使用して、マシン構成ファイルで以前に定義したセクションをクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f441-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="8f441-120">次のマシン構成ファイルのコードでは、セクション **\<mysection >** が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="8f441-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="8f441-121">次のアプリケーション構成ファイルのコードは、 **\<mySection >** からすべての設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="8f441-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="8f441-122">アプリケーションは、コンピューター構成ファイルの **\<mysection >** セクションので宣言された設定を取得できません。</span><span class="sxs-lookup"><span data-stu-id="8f441-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8f441-123">［構成ファイル］</span><span class="sxs-lookup"><span data-stu-id="8f441-123">Configuration file</span></span>

<span data-ttu-id="8f441-124">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f441-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f441-125">参照</span><span class="sxs-lookup"><span data-stu-id="8f441-125">See also</span></span>

- [<span data-ttu-id="8f441-126">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="8f441-126">Configuration file schema for the .NET Framework</span></span>](index.md)
