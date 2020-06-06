---
title: <configSections> の <remove> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154531"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="37068-102">\<configSections> の \<remove> 要素</span><span class="sxs-lookup"><span data-stu-id="37068-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="37068-103">定義済みセクションまたはセクショングループを削除します。</span><span class="sxs-lookup"><span data-stu-id="37068-103">Removes a predefined section or section group.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="37068-104">構文</span><span class="sxs-lookup"><span data-stu-id="37068-104">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="37068-105">属性</span><span class="sxs-lookup"><span data-stu-id="37068-105">Attribute</span></span>

|           | <span data-ttu-id="37068-106">説明</span><span class="sxs-lookup"><span data-stu-id="37068-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="37068-107">**name**</span><span class="sxs-lookup"><span data-stu-id="37068-107">**name**</span></span>  | <span data-ttu-id="37068-108">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="37068-108">Required attribute.</span></span><br><br><span data-ttu-id="37068-109">削除するセクションまたはセクショングループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37068-109">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="37068-110">親要素</span><span class="sxs-lookup"><span data-stu-id="37068-110">Parent element</span></span>

|     | <span data-ttu-id="37068-111">説明</span><span class="sxs-lookup"><span data-stu-id="37068-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="37068-112">**\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="37068-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="37068-113">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="37068-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="37068-114">子要素</span><span class="sxs-lookup"><span data-stu-id="37068-114">Child elements</span></span>

<span data-ttu-id="37068-115">なし</span><span class="sxs-lookup"><span data-stu-id="37068-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="37068-116">解説</span><span class="sxs-lookup"><span data-stu-id="37068-116">Remarks</span></span>

<span data-ttu-id="37068-117">要素を使用して、 **\<remove>** 構成ファイル階層の上位レベルで定義されたセクションとセクショングループをアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="37068-117">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="37068-118">例</span><span class="sxs-lookup"><span data-stu-id="37068-118">Example</span></span>

<span data-ttu-id="37068-119">次の例は、 **\<remove>** アプリケーション構成ファイルで要素を使用して、コンピューター構成ファイルで以前に定義されたセクションを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="37068-119">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="37068-120">次のマシン構成ファイルのコードでは、セクションを宣言してい **\<sampleSection>** ます。</span><span class="sxs-lookup"><span data-stu-id="37068-120">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="37068-121">次のアプリケーション構成ファイルのコードでは、セクションが削除され **\<sampleSection>** ます。</span><span class="sxs-lookup"><span data-stu-id="37068-121">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="37068-122">削除後、アプリケーションはの設定を取得できません **\<sampleSection>** 。</span><span class="sxs-lookup"><span data-stu-id="37068-122">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="37068-123">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="37068-123">Configuration file</span></span>

<span data-ttu-id="37068-124">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="37068-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="37068-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="37068-125">See also</span></span>

- [<span data-ttu-id="37068-126">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="37068-126">Configuration file schema for the .NET Framework</span></span>](index.md)
