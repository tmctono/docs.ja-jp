---
title: <configSections> の <clear> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155428"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="78b73-102">\<構成セクション>の\<>要素をクリアする</span><span class="sxs-lookup"><span data-stu-id="78b73-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="78b73-103">以前に定義したすべてのセクションおよびセクション グループをクリアします。</span><span class="sxs-lookup"><span data-stu-id="78b73-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="78b73-104">&nbsp;&nbsp;[**\<構成>**](configuration-element.md)&nbsp;&nbsp;**な\<>>** セクション[**\<**](configsections-element-for-configuration.md)&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="78b73-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="78b73-105">構文</span><span class="sxs-lookup"><span data-stu-id="78b73-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="78b73-106">属性</span><span class="sxs-lookup"><span data-stu-id="78b73-106">Attribute</span></span>

|           | <span data-ttu-id="78b73-107">説明</span><span class="sxs-lookup"><span data-stu-id="78b73-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="78b73-108">**name**</span><span class="sxs-lookup"><span data-stu-id="78b73-108">**name**</span></span>  | <span data-ttu-id="78b73-109">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="78b73-109">Required attribute.</span></span><br><br><span data-ttu-id="78b73-110">削除するセクションまたはセクション グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="78b73-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="78b73-111">親要素</span><span class="sxs-lookup"><span data-stu-id="78b73-111">Parent element</span></span>

|     | <span data-ttu-id="78b73-112">説明</span><span class="sxs-lookup"><span data-stu-id="78b73-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="78b73-113">**\<構成セクション>** 要素</span><span class="sxs-lookup"><span data-stu-id="78b73-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="78b73-114">構成セクションと名前空間の宣言が含まれます。</span><span class="sxs-lookup"><span data-stu-id="78b73-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="78b73-115">子要素</span><span class="sxs-lookup"><span data-stu-id="78b73-115">Child elements</span></span>

<span data-ttu-id="78b73-116">なし</span><span class="sxs-lookup"><span data-stu-id="78b73-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="78b73-117">解説</span><span class="sxs-lookup"><span data-stu-id="78b73-117">Remarks</span></span>

<span data-ttu-id="78b73-118">\*\* \<clear>\*\* 要素は、現在の構成ファイルで以前に定義された、または構成ファイル階層の上位レベルで定義されたすべてのセクションとセクション グループをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="78b73-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="78b73-119">例</span><span class="sxs-lookup"><span data-stu-id="78b73-119">Example</span></span>

<span data-ttu-id="78b73-120">この例では、マシン構成ファイルとアプリケーション構成ファイルを定義し、**\<アプリケーション**構成ファイルで clear>要素を使用して、マシン構成ファイルで以前に定義されたセクションをクリアする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="78b73-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="78b73-121">次のマシン構成ファイル コードでは、**\<アプリケーション**構成ファイルの前に読み取られる、sampleSection>と**\<別の SampleSection>** の 2 つのセクションを宣言します。</span><span class="sxs-lookup"><span data-stu-id="78b73-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="78b73-122">次のアプリケーション構成ファイルコードは、以前に宣言されたすべてのセクションをクリアします。</span><span class="sxs-lookup"><span data-stu-id="78b73-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="78b73-123">アプリケーションは、マシン構成ファイルで宣言されたセクションの設定を使用または取得できません。</span><span class="sxs-lookup"><span data-stu-id="78b73-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="78b73-124">ただし、クリア**\<>** 要素の後に来るので、**\<別のセクション>** からの設定を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="78b73-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="78b73-125">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="78b73-125">Configuration file</span></span>

<span data-ttu-id="78b73-126">この要素は、アプリケーションディレクトリレベルではないアプリケーション構成ファイル、マシン構成ファイル (*Machine.config*) および*Web.config*ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="78b73-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="78b73-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="78b73-127">See also</span></span>

- [<span data-ttu-id="78b73-128">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="78b73-128">Configuration file schema for the .NET Framework</span></span>](index.md)
