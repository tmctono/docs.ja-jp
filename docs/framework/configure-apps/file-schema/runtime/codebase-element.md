---
title: <codeBase> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: bd170b817c5ccc337711f8f79968653c29f3eda4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252745"
---
# <a name="codebase-element"></a><span data-ttu-id="a93a3-102">\<codeBase > 要素</span><span class="sxs-lookup"><span data-stu-id="a93a3-102">\<codeBase> Element</span></span>

<span data-ttu-id="a93a3-103">共通言語ランタイムがアセンブリを検索できる場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="a93a3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a93a3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a93a3-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a93a3-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a93a3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="a93a3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="a93a3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="a93a3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="a93a3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<codeBase>**</span><span class="sxs-lookup"><span data-stu-id="a93a3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a93a3-109">構文</span><span class="sxs-lookup"><span data-stu-id="a93a3-109">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a93a3-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a93a3-110">Attributes and Elements</span></span>

<span data-ttu-id="a93a3-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a93a3-112">属性</span><span class="sxs-lookup"><span data-stu-id="a93a3-112">Attributes</span></span>

|<span data-ttu-id="a93a3-113">属性</span><span class="sxs-lookup"><span data-stu-id="a93a3-113">Attribute</span></span>|<span data-ttu-id="a93a3-114">説明</span><span class="sxs-lookup"><span data-stu-id="a93a3-114">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="a93a3-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a93a3-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="a93a3-116">ランタイムが指定されたバージョンのアセンブリを検索できる URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="a93a3-117">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a93a3-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="a93a3-118">コードベースが適用されるアセンブリのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="a93a3-119">アセンブリバージョン番号の形式は major. *minor. build. revision*です。</span><span class="sxs-lookup"><span data-stu-id="a93a3-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="a93a3-120">version 属性</span><span class="sxs-lookup"><span data-stu-id="a93a3-120">version Attribute</span></span>

|<span data-ttu-id="a93a3-121">値</span><span class="sxs-lookup"><span data-stu-id="a93a3-121">Value</span></span>|<span data-ttu-id="a93a3-122">説明</span><span class="sxs-lookup"><span data-stu-id="a93a3-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="a93a3-123">バージョン番号の各部分の有効な値は 0 ~ 65535 です。</span><span class="sxs-lookup"><span data-stu-id="a93a3-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="a93a3-124">適用できません。</span><span class="sxs-lookup"><span data-stu-id="a93a3-124">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a93a3-125">子要素</span><span class="sxs-lookup"><span data-stu-id="a93a3-125">Child Elements</span></span>

<span data-ttu-id="a93a3-126">なし。</span><span class="sxs-lookup"><span data-stu-id="a93a3-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a93a3-127">親要素</span><span class="sxs-lookup"><span data-stu-id="a93a3-127">Parent Elements</span></span>

|<span data-ttu-id="a93a3-128">要素</span><span class="sxs-lookup"><span data-stu-id="a93a3-128">Element</span></span>|<span data-ttu-id="a93a3-129">説明</span><span class="sxs-lookup"><span data-stu-id="a93a3-129">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="a93a3-130">カスタム リソース ファイルをコンパイルするためのビルド プロバイダーのコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="a93a3-131">ビルド プロバイダーの数は任意です。</span><span class="sxs-lookup"><span data-stu-id="a93a3-131">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="a93a3-132">ASP.NET が使用するすべてのコンパイル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-132">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="a93a3-133">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a93a3-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="a93a3-134">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-134">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a93a3-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="a93a3-135">Remarks</span></span>

<span data-ttu-id="a93a3-136">ランタイムで、コンピューター構成ファイルまたは発行者ポリシーファイルの **\<コードベース >** 設定を使用するには、アセンブリのバージョンもリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a93a3-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="a93a3-137">アプリケーション構成ファイルには、アセンブリのバージョンをリダイレクトせずにコードベースを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a93a3-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="a93a3-138">使用するアセンブリバージョンを決定した後、ランタイムは、バージョンを決定するファイルのコードベース設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="a93a3-139">コードベースが指定されていない場合、ランタイムは通常の方法でアセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="a93a3-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="a93a3-140">アセンブリに厳密な名前が付いている場合、コードベースの設定は、ローカルイントラネットまたはインターネット上の任意の場所に置くことができます。</span><span class="sxs-lookup"><span data-stu-id="a93a3-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="a93a3-141">アセンブリがプライベートアセンブリの場合、コードベースの設定は、アプリケーションのディレクトリに対する相対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a93a3-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="a93a3-142">厳密な名前のないアセンブリの場合、バージョンは無視され、ローダーは dependentAssembly \<> 内部\<のコードベース > の最初の外観を使用します。</span><span class="sxs-lookup"><span data-stu-id="a93a3-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="a93a3-143">バインドを別のアセンブリにリダイレクトするエントリがアプリケーション構成ファイルにある場合、アセンブリのバージョンがバインド要求と一致しない場合でも、リダイレクトが優先されます。</span><span class="sxs-lookup"><span data-stu-id="a93a3-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="a93a3-144">例</span><span class="sxs-lookup"><span data-stu-id="a93a3-144">Example</span></span>

<span data-ttu-id="a93a3-145">次の例は、ランタイムがアセンブリを検索する場所を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a93a3-145">The following example shows how to specify where the runtime can find an assembly.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a93a3-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="a93a3-146">See also</span></span>

- [<span data-ttu-id="a93a3-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a93a3-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a93a3-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a93a3-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a93a3-149">アセンブリの場所の指定</span><span class="sxs-lookup"><span data-stu-id="a93a3-149">Specifying an Assembly's Location</span></span>](../../specify-assembly-location.md)
- [<span data-ttu-id="a93a3-150">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="a93a3-150">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
