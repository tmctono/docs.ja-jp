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
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674195"
---
# <a name="codebase-element"></a><span data-ttu-id="4ad00-102">\<codeBase > 要素</span><span class="sxs-lookup"><span data-stu-id="4ad00-102">\<codeBase> Element</span></span>

<span data-ttu-id="4ad00-103">共通言語ランタイムがアセンブリを検索する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="4ad00-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span><span class="sxs-lookup"><span data-stu-id="4ad00-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="4ad00-105">構文</span><span class="sxs-lookup"><span data-stu-id="4ad00-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4ad00-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4ad00-106">Attributes and Elements</span></span>

<span data-ttu-id="4ad00-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4ad00-108">属性</span><span class="sxs-lookup"><span data-stu-id="4ad00-108">Attributes</span></span>

|<span data-ttu-id="4ad00-109">属性</span><span class="sxs-lookup"><span data-stu-id="4ad00-109">Attribute</span></span>|<span data-ttu-id="4ad00-110">説明</span><span class="sxs-lookup"><span data-stu-id="4ad00-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="4ad00-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4ad00-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ad00-112">ランタイムがアセンブリの指定したバージョンを検索できる URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="4ad00-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="4ad00-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ad00-114">コードベースを適用するアセンブリのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="4ad00-115">アセンブリのバージョン番号の形式が*major.minor.build.revision*します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="4ad00-116">バージョン属性</span><span class="sxs-lookup"><span data-stu-id="4ad00-116">version Attribute</span></span>

|<span data-ttu-id="4ad00-117">[値]</span><span class="sxs-lookup"><span data-stu-id="4ad00-117">Value</span></span>|<span data-ttu-id="4ad00-118">説明</span><span class="sxs-lookup"><span data-stu-id="4ad00-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="4ad00-119">バージョン番号の各部分の有効な値は、0 ~ 65535 です。</span><span class="sxs-lookup"><span data-stu-id="4ad00-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="4ad00-120">該当なし。</span><span class="sxs-lookup"><span data-stu-id="4ad00-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4ad00-121">子要素</span><span class="sxs-lookup"><span data-stu-id="4ad00-121">Child Elements</span></span>

<span data-ttu-id="4ad00-122">なし。</span><span class="sxs-lookup"><span data-stu-id="4ad00-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4ad00-123">親要素</span><span class="sxs-lookup"><span data-stu-id="4ad00-123">Parent Elements</span></span>

|<span data-ttu-id="4ad00-124">要素</span><span class="sxs-lookup"><span data-stu-id="4ad00-124">Element</span></span>|<span data-ttu-id="4ad00-125">説明</span><span class="sxs-lookup"><span data-stu-id="4ad00-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="4ad00-126">カスタム リソース ファイルをコンパイルするためのビルド プロバイダーのコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="4ad00-127">ビルド プロバイダーの数は任意です。</span><span class="sxs-lookup"><span data-stu-id="4ad00-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="4ad00-128">ASP.NET で使用されるすべてのコンパイルの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="4ad00-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="4ad00-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="4ad00-130">ASP.NET 構成セクションのルート要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4ad00-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ad00-131">Remarks</span></span>

<span data-ttu-id="4ad00-132">ランタイムを使用するため、  **\<codeBase >** マシン構成ファイルまたは発行者ポリシー ファイルで設定をファイルする必要がありますも、アセンブリ バージョンをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="4ad00-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="4ad00-133">アプリケーション構成ファイルでは、アセンブリのバージョンをリダイレクトせずコードベースの設定を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="4ad00-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="4ad00-134">使用するアセンブリ バージョンを決定した後は、ランタイムは、バージョンを決定するファイルのコードベースの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="4ad00-135">コードベースが示されていない場合、ランタイムは、通常の方法でアセンブリをプローブします。</span><span class="sxs-lookup"><span data-stu-id="4ad00-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="4ad00-136">アセンブリに厳密な名前がある場合は、コードベースの設定はローカル イントラネットまたはインターネットの任意の場所します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="4ad00-137">アセンブリがプライベート アセンブリの場合は、コードベースの設定は、アプリケーションのディレクトリの相対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ad00-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="4ad00-138">厳密な名前のないアセンブリでは、バージョンは無視され、ローダーは最初の外観\<codebase > 内で\<dependentAssembly >。</span><span class="sxs-lookup"><span data-stu-id="4ad00-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="4ad00-139">別のアセンブリへのバインディングをリダイレクトするアプリケーション構成ファイルにエントリがある場合、アセンブリのバージョンは、バインド要求と一致しない場合でもはリダイレクトが優先されます。</span><span class="sxs-lookup"><span data-stu-id="4ad00-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="4ad00-140">例</span><span class="sxs-lookup"><span data-stu-id="4ad00-140">Example</span></span>

<span data-ttu-id="4ad00-141">次の例では、ランタイムがアセンブリを検索する場所を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4ad00-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4ad00-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ad00-142">See also</span></span>

- [<span data-ttu-id="4ad00-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="4ad00-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="4ad00-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4ad00-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4ad00-145">アセンブリの場所の指定</span><span class="sxs-lookup"><span data-stu-id="4ad00-145">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="4ad00-146">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="4ad00-146">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
