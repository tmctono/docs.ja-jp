---
title: <sectionGroup> の <configSections> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: eb221027470fe6e485f8fcc4b939b71e4f219712
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215257"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="0b980-102">\<configSections の \<sectionGroup > 要素 ></span><span class="sxs-lookup"><span data-stu-id="0b980-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="0b980-103">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="0b980-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="0b980-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b980-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="0b980-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="0b980-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="0b980-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="0b980-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0b980-107">構文</span><span class="sxs-lookup"><span data-stu-id="0b980-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="0b980-108">属性</span><span class="sxs-lookup"><span data-stu-id="0b980-108">Attribute</span></span>

|           | <span data-ttu-id="0b980-109">説明</span><span class="sxs-lookup"><span data-stu-id="0b980-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0b980-110">**name**</span><span class="sxs-lookup"><span data-stu-id="0b980-110">**name**</span></span>  | <span data-ttu-id="0b980-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="0b980-111">Required attribute.</span></span><br><br><span data-ttu-id="0b980-112">定義するセクショングループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0b980-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="0b980-113">親要素</span><span class="sxs-lookup"><span data-stu-id="0b980-113">Parent element</span></span>

|     | <span data-ttu-id="0b980-114">説明</span><span class="sxs-lookup"><span data-stu-id="0b980-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0b980-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="0b980-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="0b980-116">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b980-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0b980-117">子要素</span><span class="sxs-lookup"><span data-stu-id="0b980-117">Child elements</span></span>

|     | <span data-ttu-id="0b980-118">説明</span><span class="sxs-lookup"><span data-stu-id="0b980-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0b980-119"> **\<セクション >** </span><span class="sxs-lookup"><span data-stu-id="0b980-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="0b980-120">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b980-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0b980-121">コメント</span><span class="sxs-lookup"><span data-stu-id="0b980-121">Remarks</span></span>

<span data-ttu-id="0b980-122">セクショングループを宣言すると、構成セクションのコンテナータグが作成され、他のユーザーが定義した構成セクションと名前の競合が発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="0b980-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="0b980-123">**\<sectionGroup >** 要素を入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b980-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="0b980-124">例</span><span class="sxs-lookup"><span data-stu-id="0b980-124">Example</span></span>

<span data-ttu-id="0b980-125">次の例は、セクショングループを宣言し、セクショングループ内でセクションを宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b980-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="0b980-126">［構成ファイル］</span><span class="sxs-lookup"><span data-stu-id="0b980-126">Configuration file</span></span>

<span data-ttu-id="0b980-127">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b980-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b980-128">参照</span><span class="sxs-lookup"><span data-stu-id="0b980-128">See also</span></span>

- [<span data-ttu-id="0b980-129">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="0b980-129">Configuration file schema for the .NET Framework</span></span>](index.md)
