---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 94f7709f4bd273515d9fcdd727354ec579c46207
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927227"
---
# <a name="section-element"></a><span data-ttu-id="1300c-102">\<section > 要素</span><span class="sxs-lookup"><span data-stu-id="1300c-102">\<section> element</span></span>

<span data-ttu-id="1300c-103">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1300c-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="1300c-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="1300c-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="1300c-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="1300c-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="1300c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<セクション >**</span><span class="sxs-lookup"><span data-stu-id="1300c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="1300c-107">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="1300c-107">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="1300c-108">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="1300c-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="1300c-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="1300c-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="1300c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<セクション >**</span><span class="sxs-lookup"><span data-stu-id="1300c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1300c-111">構文</span><span class="sxs-lookup"><span data-stu-id="1300c-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="1300c-112">必要な属性</span><span class="sxs-lookup"><span data-stu-id="1300c-112">Required attributes</span></span>

|           | <span data-ttu-id="1300c-113">説明</span><span class="sxs-lookup"><span data-stu-id="1300c-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="1300c-114">**name**</span><span class="sxs-lookup"><span data-stu-id="1300c-114">**name**</span></span>  | <span data-ttu-id="1300c-115">構成セクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1300c-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="1300c-116">**type**</span><span class="sxs-lookup"><span data-stu-id="1300c-116">**type**</span></span>  | <span data-ttu-id="1300c-117">構成ファイルからセクションを読み取る構成セクションハンドラークラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1300c-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="1300c-118">型の値には、"完全修飾名"、"完全修飾名"、". アセンブリ名" の構文があります。</span><span class="sxs-lookup"><span data-stu-id="1300c-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="1300c-119">単純なアセンブリ名は、 *.dll*ファイル拡張子のないルートファイル名です。</span><span class="sxs-lookup"><span data-stu-id="1300c-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="1300c-120">省略可能な属性</span><span class="sxs-lookup"><span data-stu-id="1300c-120">Optional attributes</span></span>

<span data-ttu-id="1300c-121">次の属性は、ASP.NET アプリケーションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1300c-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="1300c-122">構成システムは、他のアプリケーションの種類に対してこれらの属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="1300c-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="1300c-123">説明</span><span class="sxs-lookup"><span data-stu-id="1300c-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="1300c-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="1300c-124">**allowDefinition**</span></span> | <span data-ttu-id="1300c-125">セクションを使用できる構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1300c-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="1300c-126">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="1300c-126">Use one of the following values:</span></span><br><br><span data-ttu-id="1300c-127">**全体**</span><span class="sxs-lookup"><span data-stu-id="1300c-127">**Everywhere**</span></span><br><span data-ttu-id="1300c-128">すべての構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1300c-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="1300c-129">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1300c-129">This is the default.</span></span><br><span data-ttu-id="1300c-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="1300c-130">**MachineOnly**</span></span><br><span data-ttu-id="1300c-131">セクションをコンピューターの構成ファイル (machine.config) でのみ使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1300c-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="1300c-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="1300c-132">**MachineToApplication**</span></span><br><span data-ttu-id="1300c-133">コンピューターの構成ファイルまたはアプリケーション構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1300c-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="1300c-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="1300c-134">**allowLocation**</span></span>   | <span data-ttu-id="1300c-135">位置 > 要素内で **\<** セクションを使用できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1300c-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="1300c-136">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="1300c-136">Use one of the following values:</span></span><br><br><span data-ttu-id="1300c-137">**true**</span><span class="sxs-lookup"><span data-stu-id="1300c-137">**true**</span></span><br><span data-ttu-id="1300c-138">位置 > 要素内で **\<** セクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1300c-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="1300c-139">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1300c-139">This is the default.</span></span><br><span data-ttu-id="1300c-140">**false**</span><span class="sxs-lookup"><span data-stu-id="1300c-140">**false**</span></span><br><span data-ttu-id="1300c-141">では、  **\<location >** 要素内でセクションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1300c-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="1300c-142">親要素</span><span class="sxs-lookup"><span data-stu-id="1300c-142">Parent elements</span></span>

|     | <span data-ttu-id="1300c-143">説明</span><span class="sxs-lookup"><span data-stu-id="1300c-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1300c-144">要素 > configsections  **\<** </span><span class="sxs-lookup"><span data-stu-id="1300c-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="1300c-145">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1300c-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="1300c-146"> **sectionGroup>\<** 要素</span><span class="sxs-lookup"><span data-stu-id="1300c-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="1300c-147">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="1300c-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="1300c-148">セクション > 要素は、  **\<configsections >** または **\<sectionGroup >** のいずれかの子要素ですが、両方を持つことはできません。  **\<**</span><span class="sxs-lookup"><span data-stu-id="1300c-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="1300c-149">子要素</span><span class="sxs-lookup"><span data-stu-id="1300c-149">Child elements</span></span>

<span data-ttu-id="1300c-150">なし</span><span class="sxs-lookup"><span data-stu-id="1300c-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="1300c-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="1300c-151">Remarks</span></span>

<span data-ttu-id="1300c-152">構成セクションを宣言すると、基本的に構成ファイルの新しい要素が定義されます。</span><span class="sxs-lookup"><span data-stu-id="1300c-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="1300c-153">新しい要素には、構成セクションハンドラー (つまり、 <xref:System.Configuration.IConfigurationSectionHandler>インターフェイスを実装するクラス) の読み取りの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1300c-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="1300c-154">定義するセクションの属性と子要素は、設定の読み取りに使用するセクションハンドラーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1300c-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="1300c-155">*Machine.config*ファイルで構成セクションハンドラーを宣言すると、 **allowdefinition**属性で特に指定されていない限り、そのコンピューター上の任意のアプリケーション構成ファイルの構成セクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1300c-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="1300c-156">例</span><span class="sxs-lookup"><span data-stu-id="1300c-156">Example</span></span>

<span data-ttu-id="1300c-157">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1300c-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="1300c-158">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="1300c-158">Configuration file</span></span>

<span data-ttu-id="1300c-159">この要素は、アプリケーション構成ファイル、コンピューター構成ファイル (machine.config)、およびアプリケーションディレクトリレベルではない web.config ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1300c-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1300c-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="1300c-160">See also</span></span>

- [<span data-ttu-id="1300c-161">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="1300c-161">Configuration file schema for the .NET Framework</span></span>](index.md)
