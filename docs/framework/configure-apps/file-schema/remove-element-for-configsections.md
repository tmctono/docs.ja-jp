---
title: <configSections> の <remove> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efc7208aa51cbf6abdb2fe151d48071c0aa95b5c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089047"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="ff2d9-102">\<configSections の > 要素を削除 \<</span><span class="sxs-lookup"><span data-stu-id="ff2d9-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="ff2d9-103">定義済みセクションまたはセクショングループを削除します。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="ff2d9-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff2d9-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="ff2d9-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="ff2d9-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="ff2d9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<削除**></span><span class="sxs-lookup"><span data-stu-id="ff2d9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ff2d9-107">構文</span><span class="sxs-lookup"><span data-stu-id="ff2d9-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="ff2d9-108">属性</span><span class="sxs-lookup"><span data-stu-id="ff2d9-108">Attribute</span></span>

|           | <span data-ttu-id="ff2d9-109">説明</span><span class="sxs-lookup"><span data-stu-id="ff2d9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ff2d9-110">**name**</span><span class="sxs-lookup"><span data-stu-id="ff2d9-110">**name**</span></span>  | <span data-ttu-id="ff2d9-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-111">Required attribute.</span></span><br><br><span data-ttu-id="ff2d9-112">削除するセクションまたはセクショングループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ff2d9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="ff2d9-113">Parent element</span></span>

|     | <span data-ttu-id="ff2d9-114">説明</span><span class="sxs-lookup"><span data-stu-id="ff2d9-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ff2d9-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="ff2d9-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="ff2d9-116">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ff2d9-117">子要素</span><span class="sxs-lookup"><span data-stu-id="ff2d9-117">Child elements</span></span>

<span data-ttu-id="ff2d9-118">None</span><span class="sxs-lookup"><span data-stu-id="ff2d9-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ff2d9-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff2d9-119">Remarks</span></span>

<span data-ttu-id="ff2d9-120">**\<remove >** 要素を使用して、構成ファイル階層の上位レベルで定義されたセクションとセクショングループをアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="ff2d9-121">例</span><span class="sxs-lookup"><span data-stu-id="ff2d9-121">Example</span></span>

<span data-ttu-id="ff2d9-122">次の例では、アプリケーション構成ファイルで **\<remove >** 要素を使用して、マシン構成ファイルで以前に定義したセクションを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="ff2d9-123">次のマシン構成ファイルのコードでは、セクション **\<sampleSection >** が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="ff2d9-124">次のアプリケーション構成ファイルのコードでは、 **\<sampleSection >** セクションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="ff2d9-125">削除後、アプリケーションは **\<sampleSection >** の設定を取得できません。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ff2d9-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="ff2d9-126">Configuration file</span></span>

<span data-ttu-id="ff2d9-127">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff2d9-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff2d9-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff2d9-128">See also</span></span>

- [<span data-ttu-id="ff2d9-129">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="ff2d9-129">Configuration file schema for the .NET Framework</span></span>](index.md)
