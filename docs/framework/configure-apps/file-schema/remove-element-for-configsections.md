---
title: <remove>appSettings&gt;の<configSections>add&gt;要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4ff9bb537a31e28dbd4b878c1bc04c96262f85ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927457"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="42b99-102">\<configsections の > \<要素を削除し ></span><span class="sxs-lookup"><span data-stu-id="42b99-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="42b99-103">定義済みのセクション、またはセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="42b99-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="42b99-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="42b99-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="42b99-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="42b99-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="42b99-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> の削除**</span><span class="sxs-lookup"><span data-stu-id="42b99-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="42b99-107">構文</span><span class="sxs-lookup"><span data-stu-id="42b99-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="42b99-108">属性</span><span class="sxs-lookup"><span data-stu-id="42b99-108">Attribute</span></span>

|           | <span data-ttu-id="42b99-109">説明</span><span class="sxs-lookup"><span data-stu-id="42b99-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="42b99-110">**name**</span><span class="sxs-lookup"><span data-stu-id="42b99-110">**name**</span></span>  | <span data-ttu-id="42b99-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="42b99-111">Required attribute.</span></span><br><br><span data-ttu-id="42b99-112">削除するセクションまたはセクショングループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="42b99-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="42b99-113">親要素</span><span class="sxs-lookup"><span data-stu-id="42b99-113">Parent element</span></span>

|     | <span data-ttu-id="42b99-114">説明</span><span class="sxs-lookup"><span data-stu-id="42b99-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="42b99-115">要素 > configsections  **\<** </span><span class="sxs-lookup"><span data-stu-id="42b99-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="42b99-116">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="42b99-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="42b99-117">子要素</span><span class="sxs-lookup"><span data-stu-id="42b99-117">Child elements</span></span>

<span data-ttu-id="42b99-118">なし</span><span class="sxs-lookup"><span data-stu-id="42b99-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="42b99-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="42b99-119">Remarks</span></span>

<span data-ttu-id="42b99-120">[  **\<> の削除**] 要素を使用して、構成ファイル階層の上位レベルで定義されたセクションとセクショングループをアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="42b99-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="42b99-121">例</span><span class="sxs-lookup"><span data-stu-id="42b99-121">Example</span></span>

<span data-ttu-id="42b99-122">次の例では、アプリケーション構成ファイルで **\<remove >** 要素を使用して、マシン構成ファイルで以前に定義したセクションを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42b99-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="42b99-123">次のマシン構成ファイルのコードでは、セクション **\<sampleSection >** が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="42b99-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="42b99-124">次のアプリケーション構成ファイルのコードでは、  **\<sampleSection >** セクションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="42b99-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="42b99-125">削除後、アプリケーションは **\<sampleSection >** の設定を取得できません。</span><span class="sxs-lookup"><span data-stu-id="42b99-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="42b99-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="42b99-126">Configuration file</span></span>

<span data-ttu-id="42b99-127">この要素は、アプリケーション構成ファイル、コンピューター構成ファイル (machine.config)、およびアプリケーションディレクトリレベルではない web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="42b99-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="42b99-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="42b99-128">See also</span></span>

- [<span data-ttu-id="42b99-129">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="42b99-129">Configuration file schema for the .NET Framework</span></span>](index.md)
