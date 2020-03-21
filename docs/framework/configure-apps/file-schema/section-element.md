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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153732"
---
# <a name="section-element"></a><span data-ttu-id="b42aa-102">\<セクション>要素</span><span class="sxs-lookup"><span data-stu-id="b42aa-102">\<section> element</span></span>

<span data-ttu-id="b42aa-103">構成セクションの宣言を含みます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="b42aa-104">[**\<構成>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b42aa-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="b42aa-105">&nbsp;&nbsp;[**\<構成セクション>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b42aa-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="b42aa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<セクション>**</span><span class="sxs-lookup"><span data-stu-id="b42aa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="b42aa-107">[**\<構成>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b42aa-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="b42aa-108">&nbsp;&nbsp;[**\<構成セクション>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b42aa-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="b42aa-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<セクショングループ>**](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="b42aa-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="b42aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<セクション>**</span><span class="sxs-lookup"><span data-stu-id="b42aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b42aa-111">構文</span><span class="sxs-lookup"><span data-stu-id="b42aa-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="b42aa-112">必須属性</span><span class="sxs-lookup"><span data-stu-id="b42aa-112">Required attributes</span></span>

|           | <span data-ttu-id="b42aa-113">説明</span><span class="sxs-lookup"><span data-stu-id="b42aa-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b42aa-114">**name**</span><span class="sxs-lookup"><span data-stu-id="b42aa-114">**name**</span></span>  | <span data-ttu-id="b42aa-115">構成セクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="b42aa-116">**型**</span><span class="sxs-lookup"><span data-stu-id="b42aa-116">**type**</span></span>  | <span data-ttu-id="b42aa-117">構成ファイルからセクションを読み取る構成セクション ハンドラー クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="b42aa-118">型の値は、"完全修飾セクション ハンドラー クラス名、単純アセンブリ名" という構文を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="b42aa-119">簡易アセンブリ名は *、.dll*ファイル拡張子を持たないルート ファイル名です。</span><span class="sxs-lookup"><span data-stu-id="b42aa-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="b42aa-120">省略可能な属性</span><span class="sxs-lookup"><span data-stu-id="b42aa-120">Optional attributes</span></span>

<span data-ttu-id="b42aa-121">次の属性は、ASP.NETアプリケーションにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="b42aa-122">構成システムは、他のアプリケーション・タイプのこれらの属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="b42aa-123">説明</span><span class="sxs-lookup"><span data-stu-id="b42aa-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="b42aa-124">**定義を許可する**</span><span class="sxs-lookup"><span data-stu-id="b42aa-124">**allowDefinition**</span></span> | <span data-ttu-id="b42aa-125">セクションを使用できる構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="b42aa-126">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-126">Use one of the following values:</span></span><br><br><span data-ttu-id="b42aa-127">**すべての場所**</span><span class="sxs-lookup"><span data-stu-id="b42aa-127">**Everywhere**</span></span><br><span data-ttu-id="b42aa-128">任意の構成ファイルでセクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="b42aa-129">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b42aa-129">This is the default.</span></span><br><span data-ttu-id="b42aa-130">**マシンのみ**</span><span class="sxs-lookup"><span data-stu-id="b42aa-130">**MachineOnly**</span></span><br><span data-ttu-id="b42aa-131">このセクションは、マシン構成ファイル (*Machine.config*) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="b42aa-132">**マシンからアプリケーションへ**</span><span class="sxs-lookup"><span data-stu-id="b42aa-132">**MachineToApplication**</span></span><br><span data-ttu-id="b42aa-133">マシン構成ファイルまたはアプリケーション構成ファイルでセクションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b42aa-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="b42aa-134">**場所を許可します。**</span><span class="sxs-lookup"><span data-stu-id="b42aa-134">**allowLocation**</span></span>   | <span data-ttu-id="b42aa-135">要素の場所内でセクション**\<>** 使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="b42aa-136">次のいずれかの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-136">Use one of the following values:</span></span><br><br><span data-ttu-id="b42aa-137">**true**</span><span class="sxs-lookup"><span data-stu-id="b42aa-137">**true**</span></span><br><span data-ttu-id="b42aa-138">要素の位置内でセクション**\<>** 使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b42aa-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="b42aa-139">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b42aa-139">This is the default.</span></span><br><span data-ttu-id="b42aa-140">**false**</span><span class="sxs-lookup"><span data-stu-id="b42aa-140">**false**</span></span><br><span data-ttu-id="b42aa-141">要素の**\<場所**内でセクションを使用>許可しません。</span><span class="sxs-lookup"><span data-stu-id="b42aa-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="b42aa-142">親要素</span><span class="sxs-lookup"><span data-stu-id="b42aa-142">Parent elements</span></span>

|     | <span data-ttu-id="b42aa-143">説明</span><span class="sxs-lookup"><span data-stu-id="b42aa-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b42aa-144">**\<構成セクション>** 要素</span><span class="sxs-lookup"><span data-stu-id="b42aa-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="b42aa-145">構成セクションと名前空間の宣言が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="b42aa-146">**\<セクショングループ>** 要素</span><span class="sxs-lookup"><span data-stu-id="b42aa-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="b42aa-147">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="b42aa-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="b42aa-148">要素>**\<セクションは、configSection>** または**\<セクショングループ>** の子要素ですが、両方ではありません。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="b42aa-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="b42aa-149">子要素</span><span class="sxs-lookup"><span data-stu-id="b42aa-149">Child elements</span></span>

<span data-ttu-id="b42aa-150">なし</span><span class="sxs-lookup"><span data-stu-id="b42aa-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="b42aa-151">解説</span><span class="sxs-lookup"><span data-stu-id="b42aa-151">Remarks</span></span>

<span data-ttu-id="b42aa-152">構成セクションを宣言すると、基本的に構成ファイルの新しい要素が定義されます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="b42aa-153">新しい要素には、構成セクション ハンドラー (つまり、インターフェイスを実装するクラス)<xref:System.Configuration.IConfigurationSectionHandler>が読み取る設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b42aa-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="b42aa-154">定義するセクションの属性と子要素は、設定の読み取りに使用するセクション ハンドラーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b42aa-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="b42aa-155">*Machine.config*ファイルで構成セクション ハンドラーを宣言すると **、allowDefinition**属性で指定されていない限り、そのコンピューター上のアプリケーション構成ファイルで構成セクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="b42aa-156">例</span><span class="sxs-lookup"><span data-stu-id="b42aa-156">Example</span></span>

<span data-ttu-id="b42aa-157">次の例は、構成セクションを定義し、そのセクションの設定を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b42aa-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="b42aa-158">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b42aa-158">Configuration file</span></span>

<span data-ttu-id="b42aa-159">この要素は、アプリケーションディレクトリレベルではないアプリケーション構成ファイル、マシン構成ファイル (*Machine.config*) および*Web.config*ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b42aa-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b42aa-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="b42aa-160">See also</span></span>

- [<span data-ttu-id="b42aa-161">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b42aa-161">Configuration file schema for the .NET Framework</span></span>](index.md)
