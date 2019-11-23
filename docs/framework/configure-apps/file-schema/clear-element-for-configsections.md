---
title: <clear> の <configSections> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a45572d0dcb2737558e11f5c38ac2ccc338c754a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119081"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="089de-102">\<configSections の > 要素をクリア \<></span><span class="sxs-lookup"><span data-stu-id="089de-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="089de-103">以前に定義したセクションとセクショングループをすべて消去します。</span><span class="sxs-lookup"><span data-stu-id="089de-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="089de-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="089de-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="089de-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="089de-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="089de-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<クリア >**</span><span class="sxs-lookup"><span data-stu-id="089de-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="089de-107">構文</span><span class="sxs-lookup"><span data-stu-id="089de-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="089de-108">属性</span><span class="sxs-lookup"><span data-stu-id="089de-108">Attribute</span></span>

|           | <span data-ttu-id="089de-109">説明</span><span class="sxs-lookup"><span data-stu-id="089de-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="089de-110">**name**</span><span class="sxs-lookup"><span data-stu-id="089de-110">**name**</span></span>  | <span data-ttu-id="089de-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="089de-111">Required attribute.</span></span><br><br><span data-ttu-id="089de-112">削除するセクションまたはセクショングループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="089de-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="089de-113">親要素</span><span class="sxs-lookup"><span data-stu-id="089de-113">Parent element</span></span>

|     | <span data-ttu-id="089de-114">説明</span><span class="sxs-lookup"><span data-stu-id="089de-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="089de-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="089de-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="089de-116">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="089de-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="089de-117">子要素</span><span class="sxs-lookup"><span data-stu-id="089de-117">Child elements</span></span>

<span data-ttu-id="089de-118">なし</span><span class="sxs-lookup"><span data-stu-id="089de-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="089de-119">コメント</span><span class="sxs-lookup"><span data-stu-id="089de-119">Remarks</span></span>

<span data-ttu-id="089de-120">**\<clear >** 要素は、現在の構成ファイルまたは構成ファイル階層の上位レベルで定義されたすべてのセクションとセクショングループをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="089de-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="089de-121">例</span><span class="sxs-lookup"><span data-stu-id="089de-121">Example</span></span>

<span data-ttu-id="089de-122">この例では、マシン構成ファイルとアプリケーション構成ファイルを定義し、アプリケーション構成ファイルで **\<clear >** 要素を使用して、マシン構成ファイルで以前に定義したセクションをクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="089de-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="089de-123">次のマシン構成ファイルコードでは、アプリケーション構成ファイルの前に読み取られた2つのセクション **\<sampleSection >** と **\<anotherSampleSection >** が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="089de-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="089de-124">次のアプリケーション構成ファイルのコードは、以前に宣言されたすべてのセクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="089de-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="089de-125">アプリケーションでは、コンピューターの構成ファイルで宣言されているセクションのいずれかで設定を使用または取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="089de-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="089de-126">ただし、 **\<clear >** 要素の後にあるため、\<別の**セクション >** の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="089de-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="089de-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="089de-127">Configuration file</span></span>

<span data-ttu-id="089de-128">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="089de-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="089de-129">参照</span><span class="sxs-lookup"><span data-stu-id="089de-129">See also</span></span>

- [<span data-ttu-id="089de-130">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="089de-130">Configuration file schema for the .NET Framework</span></span>](index.md)
