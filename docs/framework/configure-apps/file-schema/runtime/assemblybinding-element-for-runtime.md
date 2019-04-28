---
title: <runtime> の <assemblyBinding> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eec77d4dd42a7b95d1e2cd0e353e2e54746676b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704883"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="8c867-102">\<assemblyBinding > 要素の\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="8c867-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="8c867-103">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c867-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
 <span data-ttu-id="8c867-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8c867-104">\<configuration></span></span>  
<span data-ttu-id="8c867-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="8c867-105">\<runtime></span></span>  
<span data-ttu-id="8c867-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="8c867-106">\<assemblyBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c867-107">構文</span><span class="sxs-lookup"><span data-stu-id="8c867-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c867-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8c867-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8c867-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c867-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c867-110">属性</span><span class="sxs-lookup"><span data-stu-id="8c867-110">Attributes</span></span>  
  
|<span data-ttu-id="8c867-111">属性</span><span class="sxs-lookup"><span data-stu-id="8c867-111">Attribute</span></span>|<span data-ttu-id="8c867-112">説明</span><span class="sxs-lookup"><span data-stu-id="8c867-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c867-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="8c867-113">**xmlns**</span></span>|<span data-ttu-id="8c867-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="8c867-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="8c867-115">アセンブリのバインディングに必要な XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c867-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="8c867-116">値として、文字列 "urn:schemas-microsoft-com:asm.v1" を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c867-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="8c867-117">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="8c867-117">**appliesTo**</span></span>|<span data-ttu-id="8c867-118">.NET Framework アセンブリのリダイレクトを適用するランタイムのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c867-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="8c867-119">このオプションの属性では、.NET Framework バージョン番号を使用して、適用するバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c867-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="8c867-120">**appliesTo** 属性が指定されていない場合、**\<assemblyBinding>** 要素は、.NET Framework のすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c867-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="8c867-121">**AppliesTo**属性は、.NET Framework version 1.1 で導入されたは、.NET Framework version 1.0 で無視されます。</span><span class="sxs-lookup"><span data-stu-id="8c867-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="8c867-122">これは **appliesTo** 属性が指定されている場合でも、.NET Framework version 1.0 を使用している場合 **\<assemblyBinding>** のすべての要素が適用されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8c867-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c867-123">子要素</span><span class="sxs-lookup"><span data-stu-id="8c867-123">Child Elements</span></span>  
  
|<span data-ttu-id="8c867-124">要素</span><span class="sxs-lookup"><span data-stu-id="8c867-124">Element</span></span>|<span data-ttu-id="8c867-125">説明</span><span class="sxs-lookup"><span data-stu-id="8c867-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c867-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="8c867-126">\<dependentAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|<span data-ttu-id="8c867-127">アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="8c867-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="8c867-128">1 つを使用して、  **\<dependentAssembly >** 各アセンブリのタグ。</span><span class="sxs-lookup"><span data-stu-id="8c867-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="8c867-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="8c867-129">\<probing></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|<span data-ttu-id="8c867-130">アセンブリの読み込み時に共通言語ランタイムが検索するサブディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c867-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="8c867-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="8c867-131">\<publisherPolicy></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|<span data-ttu-id="8c867-132">ランタイムが発行元ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8c867-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="8c867-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="8c867-133">\<qualifyAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|<span data-ttu-id="8c867-134">部分名が使用された場合に動的に読み込む必要があるアセンブリの完全名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c867-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c867-135">親要素</span><span class="sxs-lookup"><span data-stu-id="8c867-135">Parent Elements</span></span>  
  
|<span data-ttu-id="8c867-136">要素</span><span class="sxs-lookup"><span data-stu-id="8c867-136">Element</span></span>|<span data-ttu-id="8c867-137">説明</span><span class="sxs-lookup"><span data-stu-id="8c867-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8c867-138">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="8c867-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8c867-139">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c867-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c867-140">例</span><span class="sxs-lookup"><span data-stu-id="8c867-140">Example</span></span>  
 <span data-ttu-id="8c867-141">あるアセンブリ バージョンを別のバージョンにリダイレクトし、コードベースを提供する例を示します。</span><span class="sxs-lookup"><span data-stu-id="8c867-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="8c867-142">次の例は、使用する方法を示します、 **appliesTo** .NET Framework アセンブリのバインディングをリダイレクトする属性。</span><span class="sxs-lookup"><span data-stu-id="8c867-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c867-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c867-143">See also</span></span>

- [<span data-ttu-id="8c867-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="8c867-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="8c867-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="8c867-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="8c867-146">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="8c867-146">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
