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
ms.openlocfilehash: 8785523d664294e3ca3792fb0f84d739d1f1a376
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215726"
---
# <a name="section-element"></a><span data-ttu-id="5ec67-102">\<section > 要素</span><span class="sxs-lookup"><span data-stu-id="5ec67-102">\<section> element</span></span>

<span data-ttu-id="5ec67-103">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ec67-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="5ec67-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ec67-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="5ec67-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="5ec67-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="5ec67-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<セクション >**</span><span class="sxs-lookup"><span data-stu-id="5ec67-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="5ec67-107">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ec67-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="5ec67-108">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="5ec67-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="5ec67-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="5ec67-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="5ec67-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**セクション >**</span><span class="sxs-lookup"><span data-stu-id="5ec67-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5ec67-111">構文</span><span class="sxs-lookup"><span data-stu-id="5ec67-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="5ec67-112">必須属性</span><span class="sxs-lookup"><span data-stu-id="5ec67-112">Required attributes</span></span>

|           | <span data-ttu-id="5ec67-113">説明</span><span class="sxs-lookup"><span data-stu-id="5ec67-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5ec67-114">**name**</span><span class="sxs-lookup"><span data-stu-id="5ec67-114">**name**</span></span>  | <span data-ttu-id="5ec67-115">構成セクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="5ec67-116">**type**</span><span class="sxs-lookup"><span data-stu-id="5ec67-116">**type**</span></span>  | <span data-ttu-id="5ec67-117">構成ファイルからセクションを読み取る構成セクションハンドラークラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="5ec67-118">型の値には、"完全修飾名"、"完全修飾名"、". アセンブリ名" の構文があります。</span><span class="sxs-lookup"><span data-stu-id="5ec67-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="5ec67-119">単純なアセンブリ名は、 *.dll*ファイル拡張子のないルートファイル名です。</span><span class="sxs-lookup"><span data-stu-id="5ec67-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="5ec67-120">省略可能な属性</span><span class="sxs-lookup"><span data-stu-id="5ec67-120">Optional attributes</span></span>

<span data-ttu-id="5ec67-121">次の属性は、ASP.NET アプリケーションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5ec67-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="5ec67-122">構成システムは、他のアプリケーションの種類に対してこれらの属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="5ec67-123">説明</span><span class="sxs-lookup"><span data-stu-id="5ec67-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="5ec67-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="5ec67-124">**allowDefinition**</span></span> | <span data-ttu-id="5ec67-125">セクションを使用できる構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="5ec67-126">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-126">Use one of the following values:</span></span><br><br><span data-ttu-id="5ec67-127">**全体**</span><span class="sxs-lookup"><span data-stu-id="5ec67-127">**Everywhere**</span></span><br><span data-ttu-id="5ec67-128">すべての構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5ec67-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="5ec67-129">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="5ec67-129">This is the default.</span></span><br><span data-ttu-id="5ec67-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="5ec67-130">**MachineOnly**</span></span><br><span data-ttu-id="5ec67-131">セクション*をコンピューターの構成ファイル (machine.config*) でのみ使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5ec67-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="5ec67-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="5ec67-132">**MachineToApplication**</span></span><br><span data-ttu-id="5ec67-133">コンピューターの構成ファイルまたはアプリケーション構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5ec67-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="5ec67-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="5ec67-134">**allowLocation**</span></span>   | <span data-ttu-id="5ec67-135">セクションを **\<location >** 要素内で使用できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="5ec67-136">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-136">Use one of the following values:</span></span><br><br><span data-ttu-id="5ec67-137">**true**</span><span class="sxs-lookup"><span data-stu-id="5ec67-137">**true**</span></span><br><span data-ttu-id="5ec67-138">セクションを **\<location >** 要素内で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5ec67-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="5ec67-139">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="5ec67-139">This is the default.</span></span><br><span data-ttu-id="5ec67-140">**false**</span><span class="sxs-lookup"><span data-stu-id="5ec67-140">**false**</span></span><br><span data-ttu-id="5ec67-141">では、 **\<location >** 要素内でセクションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5ec67-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="5ec67-142">親要素</span><span class="sxs-lookup"><span data-stu-id="5ec67-142">Parent elements</span></span>

|     | <span data-ttu-id="5ec67-143">説明</span><span class="sxs-lookup"><span data-stu-id="5ec67-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5ec67-144"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="5ec67-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="5ec67-145">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ec67-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="5ec67-146"> **\<sectionGroup >** Element</span><span class="sxs-lookup"><span data-stu-id="5ec67-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="5ec67-147">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="5ec67-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="5ec67-148">**\<section >** 要素は **\<configsections >** または **\<sectionGroup >** のいずれかの子要素であり、両方ではありません。</span><span class="sxs-lookup"><span data-stu-id="5ec67-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="5ec67-149">子要素</span><span class="sxs-lookup"><span data-stu-id="5ec67-149">Child elements</span></span>

<span data-ttu-id="5ec67-150">なし</span><span class="sxs-lookup"><span data-stu-id="5ec67-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5ec67-151">コメント</span><span class="sxs-lookup"><span data-stu-id="5ec67-151">Remarks</span></span>

<span data-ttu-id="5ec67-152">構成セクションを宣言すると、基本的に構成ファイルの新しい要素が定義されます。</span><span class="sxs-lookup"><span data-stu-id="5ec67-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="5ec67-153">新しい要素には、構成セクションハンドラー (つまり、<xref:System.Configuration.IConfigurationSectionHandler> インターフェイスを実装するクラス) が読み取る設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ec67-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="5ec67-154">定義するセクションの属性と子要素は、設定の読み取りに使用するセクションハンドラーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5ec67-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="5ec67-155">*Machine.config*ファイルで構成セクションハンドラーを宣言すると、 **allowdefinition**属性で特に指定されていない限り、そのコンピューター上の任意のアプリケーション構成ファイルの構成セクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ec67-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="5ec67-156">例</span><span class="sxs-lookup"><span data-stu-id="5ec67-156">Example</span></span>

<span data-ttu-id="5ec67-157">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5ec67-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="5ec67-158">［構成ファイル］</span><span class="sxs-lookup"><span data-stu-id="5ec67-158">Configuration file</span></span>

<span data-ttu-id="5ec67-159">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ec67-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ec67-160">参照</span><span class="sxs-lookup"><span data-stu-id="5ec67-160">See also</span></span>

- [<span data-ttu-id="5ec67-161">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="5ec67-161">Configuration file schema for the .NET Framework</span></span>](index.md)
