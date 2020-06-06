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
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153732"
---
# <a name="section-element"></a><span data-ttu-id="efe63-102">\<section> 要素</span><span class="sxs-lookup"><span data-stu-id="efe63-102">\<section> element</span></span>

<span data-ttu-id="efe63-103">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="efe63-103">Contains a configuration section declaration.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a><span data-ttu-id="efe63-104">構文</span><span class="sxs-lookup"><span data-stu-id="efe63-104">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="efe63-105">必須属性</span><span class="sxs-lookup"><span data-stu-id="efe63-105">Required attributes</span></span>

|           | <span data-ttu-id="efe63-106">説明</span><span class="sxs-lookup"><span data-stu-id="efe63-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="efe63-107">**name**</span><span class="sxs-lookup"><span data-stu-id="efe63-107">**name**</span></span>  | <span data-ttu-id="efe63-108">構成セクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="efe63-108">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="efe63-109">**type**</span><span class="sxs-lookup"><span data-stu-id="efe63-109">**type**</span></span>  | <span data-ttu-id="efe63-110">構成ファイルからセクションを読み取る構成セクションハンドラークラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="efe63-110">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="efe63-111">型の値には、"完全修飾名"、"完全修飾名"、".. アセンブリ名" の構文があります。</span><span class="sxs-lookup"><span data-stu-id="efe63-111">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="efe63-112">単純なアセンブリ名は、 *.dll*ファイル拡張子のないルートファイル名です。</span><span class="sxs-lookup"><span data-stu-id="efe63-112">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="efe63-113">省略可能な属性</span><span class="sxs-lookup"><span data-stu-id="efe63-113">Optional attributes</span></span>

<span data-ttu-id="efe63-114">次の属性は、ASP.NET アプリケーションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="efe63-114">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="efe63-115">構成システムは、他のアプリケーションの種類に対してこれらの属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="efe63-115">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="efe63-116">Description</span><span class="sxs-lookup"><span data-stu-id="efe63-116">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="efe63-117">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="efe63-117">**allowDefinition**</span></span> | <span data-ttu-id="efe63-118">セクションを使用できる構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="efe63-118">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="efe63-119">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="efe63-119">Use one of the following values:</span></span><br><br><span data-ttu-id="efe63-120">**すべての場所**</span><span class="sxs-lookup"><span data-stu-id="efe63-120">**Everywhere**</span></span><br><span data-ttu-id="efe63-121">すべての構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="efe63-121">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="efe63-122">既定値です。</span><span class="sxs-lookup"><span data-stu-id="efe63-122">This is the default.</span></span><br><span data-ttu-id="efe63-123">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="efe63-123">**MachineOnly**</span></span><br><span data-ttu-id="efe63-124">セクション*をコンピューターの構成ファイル (machine.config*) でのみ使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="efe63-124">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="efe63-125">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="efe63-125">**MachineToApplication**</span></span><br><span data-ttu-id="efe63-126">コンピューターの構成ファイルまたはアプリケーション構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="efe63-126">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="efe63-127">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="efe63-127">**allowLocation**</span></span>   | <span data-ttu-id="efe63-128">要素内でセクションを使用できるかどうかを判断し **\<location>** ます。</span><span class="sxs-lookup"><span data-stu-id="efe63-128">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="efe63-129">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="efe63-129">Use one of the following values:</span></span><br><br><span data-ttu-id="efe63-130">**true**</span><span class="sxs-lookup"><span data-stu-id="efe63-130">**true**</span></span><br><span data-ttu-id="efe63-131">要素内でセクションを使用できるようにし **\<location>** ます。</span><span class="sxs-lookup"><span data-stu-id="efe63-131">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="efe63-132">既定値です。</span><span class="sxs-lookup"><span data-stu-id="efe63-132">This is the default.</span></span><br><span data-ttu-id="efe63-133">**false**</span><span class="sxs-lookup"><span data-stu-id="efe63-133">**false**</span></span><br><span data-ttu-id="efe63-134">では、要素内でセクションを使用することはできません **\<location>** 。</span><span class="sxs-lookup"><span data-stu-id="efe63-134">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="efe63-135">親要素</span><span class="sxs-lookup"><span data-stu-id="efe63-135">Parent elements</span></span>

|     | <span data-ttu-id="efe63-136">Description</span><span class="sxs-lookup"><span data-stu-id="efe63-136">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="efe63-137">**\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="efe63-137">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="efe63-138">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="efe63-138">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="efe63-139">**\<sectionGroup>** Element</span><span class="sxs-lookup"><span data-stu-id="efe63-139">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="efe63-140">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="efe63-140">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="efe63-141">**\<section>** 要素はまたはのいずれかの子要素であり、両方では **\<configSections>** **\<sectionGroup>** ありません。</span><span class="sxs-lookup"><span data-stu-id="efe63-141">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="efe63-142">子要素</span><span class="sxs-lookup"><span data-stu-id="efe63-142">Child elements</span></span>

<span data-ttu-id="efe63-143">なし</span><span class="sxs-lookup"><span data-stu-id="efe63-143">None</span></span>

## <a name="remarks"></a><span data-ttu-id="efe63-144">解説</span><span class="sxs-lookup"><span data-stu-id="efe63-144">Remarks</span></span>

<span data-ttu-id="efe63-145">構成セクションを宣言すると、基本的に構成ファイルの新しい要素が定義されます。</span><span class="sxs-lookup"><span data-stu-id="efe63-145">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="efe63-146">新しい要素には、構成セクションハンドラー (つまり、インターフェイスを実装するクラス) の読み取りの設定が含まれ <xref:System.Configuration.IConfigurationSectionHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="efe63-146">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="efe63-147">定義するセクションの属性と子要素は、設定の読み取りに使用するセクションハンドラーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="efe63-147">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="efe63-148">*Machine.config*ファイルで構成セクションハンドラーを宣言すると、 **allowdefinition**属性で特に指定されていない限り、そのコンピューター上の任意のアプリケーション構成ファイルの構成セクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="efe63-148">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="efe63-149">例</span><span class="sxs-lookup"><span data-stu-id="efe63-149">Example</span></span>

<span data-ttu-id="efe63-150">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="efe63-150">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="efe63-151">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="efe63-151">Configuration file</span></span>

<span data-ttu-id="efe63-152">この要素は、アプリケーション構成ファイル *、コンピューター構成*ファイル (machine.config)、およびアプリケーションディレクトリレベルでは*ない web.config ファイル*で使用できます。</span><span class="sxs-lookup"><span data-stu-id="efe63-152">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="efe63-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="efe63-153">See also</span></span>

- [<span data-ttu-id="efe63-154">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="efe63-154">Configuration file schema for the .NET Framework</span></span>](index.md)
