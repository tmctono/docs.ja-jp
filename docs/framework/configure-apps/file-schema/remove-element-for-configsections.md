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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154531"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="48420-102">\<構成>要素を\<削除するセクション></span><span class="sxs-lookup"><span data-stu-id="48420-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="48420-103">定義済みのセクションまたはセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="48420-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="48420-104">[**\<構成>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="48420-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="48420-105">&nbsp;&nbsp;[**\<構成セクション>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="48420-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="48420-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>を削除する**</span><span class="sxs-lookup"><span data-stu-id="48420-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="48420-107">構文</span><span class="sxs-lookup"><span data-stu-id="48420-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="48420-108">属性</span><span class="sxs-lookup"><span data-stu-id="48420-108">Attribute</span></span>

|           | <span data-ttu-id="48420-109">説明</span><span class="sxs-lookup"><span data-stu-id="48420-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="48420-110">**name**</span><span class="sxs-lookup"><span data-stu-id="48420-110">**name**</span></span>  | <span data-ttu-id="48420-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="48420-111">Required attribute.</span></span><br><br><span data-ttu-id="48420-112">削除するセクションまたはセクション グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48420-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="48420-113">親要素</span><span class="sxs-lookup"><span data-stu-id="48420-113">Parent element</span></span>

|     | <span data-ttu-id="48420-114">説明</span><span class="sxs-lookup"><span data-stu-id="48420-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="48420-115">**\<構成セクション>** 要素</span><span class="sxs-lookup"><span data-stu-id="48420-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="48420-116">構成セクションと名前空間の宣言が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48420-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="48420-117">子要素</span><span class="sxs-lookup"><span data-stu-id="48420-117">Child elements</span></span>

<span data-ttu-id="48420-118">なし</span><span class="sxs-lookup"><span data-stu-id="48420-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="48420-119">解説</span><span class="sxs-lookup"><span data-stu-id="48420-119">Remarks</span></span>

<span data-ttu-id="48420-120">**\<削除>** 要素を使用して、構成ファイル階層の上位レベルで定義されたセクションおよびセクション グループをアプリケーションから削除できます。</span><span class="sxs-lookup"><span data-stu-id="48420-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="48420-121">例</span><span class="sxs-lookup"><span data-stu-id="48420-121">Example</span></span>

<span data-ttu-id="48420-122">次の例は、アプリケーション構成ファイルで**\<remove>** 要素を使用して、コンピューター構成ファイルで以前に定義されたセクションを削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="48420-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="48420-123">次のマシン構成ファイル コードは、セクション**\<のサンプルセクション>** を宣言します。</span><span class="sxs-lookup"><span data-stu-id="48420-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="48420-124">次のアプリケーション構成ファイル コードは、**\<セクションセクション>セクション**を削除します。</span><span class="sxs-lookup"><span data-stu-id="48420-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="48420-125">削除後、アプリケーションは**\<sampleSection>** の設定を取得できません。</span><span class="sxs-lookup"><span data-stu-id="48420-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="48420-126">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="48420-126">Configuration file</span></span>

<span data-ttu-id="48420-127">この要素は、アプリケーションディレクトリレベルではないアプリケーション構成ファイル、マシン構成ファイル (*Machine.config*) および*Web.config*ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="48420-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="48420-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="48420-128">See also</span></span>

- [<span data-ttu-id="48420-129">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="48420-129">Configuration file schema for the .NET Framework</span></span>](index.md)
