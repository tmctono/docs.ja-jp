---
title: <runtime> の <assemblyIdentity> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154310"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="bd34f-102">\<ランタイム>の\<アセンブリID>要素</span><span class="sxs-lookup"><span data-stu-id="bd34f-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="bd34f-103">アセンブリに関する識別情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="bd34f-103">Contains identifying information about the assembly.</span></span>  
  
<span data-ttu-id="bd34f-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd34f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bd34f-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd34f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="bd34f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<アセンブリバインディング>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="bd34f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="bd34f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<従属アセンブリ>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd34f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="bd34f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<アセンブリ識別>**</span><span class="sxs-lookup"><span data-stu-id="bd34f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd34f-109">構文</span><span class="sxs-lookup"><span data-stu-id="bd34f-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd34f-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bd34f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bd34f-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd34f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd34f-112">属性</span><span class="sxs-lookup"><span data-stu-id="bd34f-112">Attributes</span></span>  
  
|<span data-ttu-id="bd34f-113">属性</span><span class="sxs-lookup"><span data-stu-id="bd34f-113">Attribute</span></span>|<span data-ttu-id="bd34f-114">説明</span><span class="sxs-lookup"><span data-stu-id="bd34f-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bd34f-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="bd34f-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="bd34f-116">アセンブリの名前</span><span class="sxs-lookup"><span data-stu-id="bd34f-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="bd34f-117">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="bd34f-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bd34f-118">アセンブリの言語と国/地域を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bd34f-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="bd34f-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="bd34f-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bd34f-120">アセンブリの厳密な名前を指定する 16 進値。</span><span class="sxs-lookup"><span data-stu-id="bd34f-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="bd34f-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="bd34f-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bd34f-122">"x86"、"amd64"、"msil"、または "ia64"の値の 1 つで、プロセッサ固有のコードを含むアセンブリのプロセッサ アーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd34f-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="bd34f-123">値は大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="bd34f-123">The values are not case-sensitive.</span></span> <span data-ttu-id="bd34f-124">属性に他の値が割り当てられている場合`<assemblyIdentity>`、要素全体は無視されます。</span><span class="sxs-lookup"><span data-stu-id="bd34f-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="bd34f-125">[https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:System.Reflection.ProcessorArchitecture>) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd34f-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="bd34f-126">プロセッサアーキテクチャ属性</span><span class="sxs-lookup"><span data-stu-id="bd34f-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="bd34f-127">Value</span><span class="sxs-lookup"><span data-stu-id="bd34f-127">Value</span></span>|<span data-ttu-id="bd34f-128">説明</span><span class="sxs-lookup"><span data-stu-id="bd34f-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="bd34f-129">AMD x86-64 アーキテクチャのみ。</span><span class="sxs-lookup"><span data-stu-id="bd34f-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="bd34f-130">インテル・イタニウム・アーキテクチャーのみ。</span><span class="sxs-lookup"><span data-stu-id="bd34f-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="bd34f-131">プロセッサおよびワードあたりのビット数に関して中立</span><span class="sxs-lookup"><span data-stu-id="bd34f-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="bd34f-132">ネイティブまたは Windows on Windows (WOW) 環境で、64 ビット プラットフォーム上の 32 ビット x86 プロセッサ。</span><span class="sxs-lookup"><span data-stu-id="bd34f-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd34f-133">子要素</span><span class="sxs-lookup"><span data-stu-id="bd34f-133">Child Elements</span></span>  
 <span data-ttu-id="bd34f-134">[なし] :</span><span class="sxs-lookup"><span data-stu-id="bd34f-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd34f-135">親要素</span><span class="sxs-lookup"><span data-stu-id="bd34f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="bd34f-136">要素</span><span class="sxs-lookup"><span data-stu-id="bd34f-136">Element</span></span>|<span data-ttu-id="bd34f-137">説明</span><span class="sxs-lookup"><span data-stu-id="bd34f-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="bd34f-138">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd34f-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="bd34f-139">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="bd34f-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="bd34f-140">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="bd34f-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="bd34f-141">各アセンブリ`<dependentAssembly>`に 1 つの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd34f-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="bd34f-142">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd34f-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd34f-143">解説</span><span class="sxs-lookup"><span data-stu-id="bd34f-143">Remarks</span></span>  
 <span data-ttu-id="bd34f-144">すべての**\<従属アセンブリアセンブリ>** 要素は、子要素**\<>アセンブリを**1 つ持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd34f-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="bd34f-145">属性が`processorArchitecture`存在する`<assemblyIdentity>`場合、要素は対応するプロセッサ アーキテクチャを持つアセンブリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="bd34f-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="bd34f-146">属性が`processorArchitecture`存在しない場合、要素は`<assemblyIdentity>`、任意のプロセッサ アーキテクチャを持つアセンブリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd34f-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="bd34f-147">次の例は、2 つの異なる 2 つのプロセッサ アーキテクチャを対象とし、バージョンが同期して維持されていない同じ名前の 2 つのアセンブリの構成ファイルを示しています。アプリケーションが x86 プラットフォームで実行されると、`<assemblyIdentity>`最初の要素が適用され、もう一方の要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="bd34f-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="bd34f-148">アプリケーションが x86 または ia64 以外のプラットフォームで実行される場合、両方が無視されます。</span><span class="sxs-lookup"><span data-stu-id="bd34f-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="bd34f-149">構成ファイルに属性のない`<assemblyIdentity>``processorArchitecture`要素が含まれ、プラットフォームに一致する要素が含まれていない場合は、`processorArchitecture`属性のない要素が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd34f-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd34f-150">例</span><span class="sxs-lookup"><span data-stu-id="bd34f-150">Example</span></span>  
 <span data-ttu-id="bd34f-151">アセンブリに関する情報を提供する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="bd34f-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd34f-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd34f-152">See also</span></span>

- [<span data-ttu-id="bd34f-153">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="bd34f-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bd34f-154">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="bd34f-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bd34f-155">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="bd34f-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
