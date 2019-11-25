---
title: <section> 要素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c1675540df6844f98572c11cfb140bff23b31a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089016"
---
# <a name="section-element"></a><span data-ttu-id="8aa07-102">\<section > 要素</span><span class="sxs-lookup"><span data-stu-id="8aa07-102">\<section> element</span></span>

<span data-ttu-id="8aa07-103">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8aa07-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="8aa07-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8aa07-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="8aa07-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="8aa07-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="8aa07-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<セクション >**</span><span class="sxs-lookup"><span data-stu-id="8aa07-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="8aa07-107">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8aa07-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="8aa07-108">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="8aa07-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="8aa07-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="8aa07-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="8aa07-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セクション >**</span><span class="sxs-lookup"><span data-stu-id="8aa07-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8aa07-111">構文</span><span class="sxs-lookup"><span data-stu-id="8aa07-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="8aa07-112">必要な属性</span><span class="sxs-lookup"><span data-stu-id="8aa07-112">Required attributes</span></span>

|           | <span data-ttu-id="8aa07-113">説明</span><span class="sxs-lookup"><span data-stu-id="8aa07-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8aa07-114">**name**</span><span class="sxs-lookup"><span data-stu-id="8aa07-114">**name**</span></span>  | <span data-ttu-id="8aa07-115">構成セクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="8aa07-116">**type**</span><span class="sxs-lookup"><span data-stu-id="8aa07-116">**type**</span></span>  | <span data-ttu-id="8aa07-117">構成ファイルからセクションを読み取る構成セクションハンドラークラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="8aa07-118">型の値には、"完全修飾名"、"完全修飾名"、". アセンブリ名" の構文があります。</span><span class="sxs-lookup"><span data-stu-id="8aa07-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="8aa07-119">単純なアセンブリ名は、 *.dll*ファイル拡張子のないルートファイル名です。</span><span class="sxs-lookup"><span data-stu-id="8aa07-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="8aa07-120">省略可能な属性</span><span class="sxs-lookup"><span data-stu-id="8aa07-120">Optional attributes</span></span>

<span data-ttu-id="8aa07-121">次の属性は、ASP.NET アプリケーションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8aa07-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="8aa07-122">構成システムは、他のアプリケーションの種類に対してこれらの属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="8aa07-123">説明</span><span class="sxs-lookup"><span data-stu-id="8aa07-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="8aa07-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="8aa07-124">**allowDefinition**</span></span> | <span data-ttu-id="8aa07-125">セクションを使用できる構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="8aa07-126">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-126">Use one of the following values:</span></span><br><br><span data-ttu-id="8aa07-127">**全体**</span><span class="sxs-lookup"><span data-stu-id="8aa07-127">**Everywhere**</span></span><br><span data-ttu-id="8aa07-128">すべての構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8aa07-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="8aa07-129">既定値です。</span><span class="sxs-lookup"><span data-stu-id="8aa07-129">This is the default.</span></span><br><span data-ttu-id="8aa07-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="8aa07-130">**MachineOnly**</span></span><br><span data-ttu-id="8aa07-131">セクション*をコンピューターの構成ファイル (machine.config*) でのみ使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8aa07-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="8aa07-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="8aa07-132">**MachineToApplication**</span></span><br><span data-ttu-id="8aa07-133">コンピューターの構成ファイルまたはアプリケーション構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8aa07-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="8aa07-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="8aa07-134">**allowLocation**</span></span>   | <span data-ttu-id="8aa07-135">セクションを **\<location >** 要素内で使用できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="8aa07-136">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-136">Use one of the following values:</span></span><br><br><span data-ttu-id="8aa07-137">**true**</span><span class="sxs-lookup"><span data-stu-id="8aa07-137">**true**</span></span><br><span data-ttu-id="8aa07-138">セクションを **\<location >** 要素内で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8aa07-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="8aa07-139">既定値です。</span><span class="sxs-lookup"><span data-stu-id="8aa07-139">This is the default.</span></span><br><span data-ttu-id="8aa07-140">**false**</span><span class="sxs-lookup"><span data-stu-id="8aa07-140">**false**</span></span><br><span data-ttu-id="8aa07-141">では、 **\<location >** 要素内でセクションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8aa07-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="8aa07-142">親要素</span><span class="sxs-lookup"><span data-stu-id="8aa07-142">Parent elements</span></span>

|     | <span data-ttu-id="8aa07-143">説明</span><span class="sxs-lookup"><span data-stu-id="8aa07-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8aa07-144"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="8aa07-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="8aa07-145">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8aa07-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="8aa07-146"> **\<sectionGroup >** Element</span><span class="sxs-lookup"><span data-stu-id="8aa07-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="8aa07-147">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="8aa07-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="8aa07-148">**\<section >** 要素は **\<configsections >** または **\<sectionGroup >** のいずれかの子要素であり、両方ではありません。</span><span class="sxs-lookup"><span data-stu-id="8aa07-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="8aa07-149">子要素</span><span class="sxs-lookup"><span data-stu-id="8aa07-149">Child elements</span></span>

<span data-ttu-id="8aa07-150">None</span><span class="sxs-lookup"><span data-stu-id="8aa07-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8aa07-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="8aa07-151">Remarks</span></span>

<span data-ttu-id="8aa07-152">構成セクションを宣言すると、基本的に構成ファイルの新しい要素が定義されます。</span><span class="sxs-lookup"><span data-stu-id="8aa07-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="8aa07-153">新しい要素には、構成セクションハンドラー (つまり、<xref:System.Configuration.IConfigurationSectionHandler> インターフェイスを実装するクラス) が読み取る設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8aa07-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="8aa07-154">定義するセクションの属性と子要素は、設定の読み取りに使用するセクションハンドラーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8aa07-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="8aa07-155">*Machine.config*ファイルで構成セクションハンドラーを宣言すると、 **allowdefinition**属性で特に指定されていない限り、そのコンピューター上の任意のアプリケーション構成ファイルの構成セクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8aa07-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="8aa07-156">例</span><span class="sxs-lookup"><span data-stu-id="8aa07-156">Example</span></span>

<span data-ttu-id="8aa07-157">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8aa07-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8aa07-158">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="8aa07-158">Configuration file</span></span>

<span data-ttu-id="8aa07-159">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8aa07-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8aa07-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="8aa07-160">See also</span></span>

- [<span data-ttu-id="8aa07-161">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="8aa07-161">Configuration file schema for the .NET Framework</span></span>](index.md)
