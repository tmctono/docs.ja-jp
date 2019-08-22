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
ms.openlocfilehash: 815e1c26a328d986f91992a1e67e438a563ffea6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663887"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="bc7ff-102">\<runtime> の \<assemblyIdentity> 要素</span><span class="sxs-lookup"><span data-stu-id="bc7ff-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="bc7ff-103">アセンブリに関する識別情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="bc7ff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bc7ff-104">\<configuration></span></span>  
<span data-ttu-id="bc7ff-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="bc7ff-105">\<runtime></span></span>  
<span data-ttu-id="bc7ff-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="bc7ff-106">\<assemblyBinding></span></span>  
<span data-ttu-id="bc7ff-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="bc7ff-107">\<dependentAssembly></span></span>  
<span data-ttu-id="bc7ff-108">\<assemblyIdentity ></span><span class="sxs-lookup"><span data-stu-id="bc7ff-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc7ff-109">構文</span><span class="sxs-lookup"><span data-stu-id="bc7ff-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc7ff-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bc7ff-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bc7ff-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc7ff-112">属性</span><span class="sxs-lookup"><span data-stu-id="bc7ff-112">Attributes</span></span>  
  
|<span data-ttu-id="bc7ff-113">属性</span><span class="sxs-lookup"><span data-stu-id="bc7ff-113">Attribute</span></span>|<span data-ttu-id="bc7ff-114">説明</span><span class="sxs-lookup"><span data-stu-id="bc7ff-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bc7ff-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc7ff-116">アセンブリの名前</span><span class="sxs-lookup"><span data-stu-id="bc7ff-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="bc7ff-117">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc7ff-118">アセンブリの言語と国/地域を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="bc7ff-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc7ff-120">アセンブリの厳密な名前を指定する16進値。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="bc7ff-121">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc7ff-122">プロセッサ固有のコードを含むアセンブリのプロセッサアーキテクチャを指定する、"x86"、"amd64"、"msil"、または "ia64" のいずれかの値。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="bc7ff-123">値の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-123">The values are not case-sensitive.</span></span> <span data-ttu-id="bc7ff-124">属性に他の値が割り当てられている`<assemblyIdentity>`場合は、要素全体が無視されます。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="bc7ff-125">以下を参照してください。<xref:System.Reflection.ProcessorArchitecture></span><span class="sxs-lookup"><span data-stu-id="bc7ff-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="bc7ff-126">processorArchitecture 属性</span><span class="sxs-lookup"><span data-stu-id="bc7ff-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="bc7ff-127">値</span><span class="sxs-lookup"><span data-stu-id="bc7ff-127">Value</span></span>|<span data-ttu-id="bc7ff-128">説明</span><span class="sxs-lookup"><span data-stu-id="bc7ff-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="bc7ff-129">AMD x86-64 アーキテクチャのみ。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="bc7ff-130">Intel Itanium アーキテクチャのみ。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="bc7ff-131">プロセッサとワードあたりのビット数に関して中立的です。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="bc7ff-132">64ビットプラットフォーム上のネイティブまたは Windows on Windows (WOW) 環境の32ビット x86 プロセッサ。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc7ff-133">子要素</span><span class="sxs-lookup"><span data-stu-id="bc7ff-133">Child Elements</span></span>  
 <span data-ttu-id="bc7ff-134">なし。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc7ff-135">親要素</span><span class="sxs-lookup"><span data-stu-id="bc7ff-135">Parent Elements</span></span>  
  
|<span data-ttu-id="bc7ff-136">要素</span><span class="sxs-lookup"><span data-stu-id="bc7ff-136">Element</span></span>|<span data-ttu-id="bc7ff-137">説明</span><span class="sxs-lookup"><span data-stu-id="bc7ff-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="bc7ff-138">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="bc7ff-139">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="bc7ff-140">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="bc7ff-141">アセンブリごと`<dependentAssembly>`に1つの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="bc7ff-142">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc7ff-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc7ff-143">Remarks</span></span>  
 <span data-ttu-id="bc7ff-144">**すべて\<の dependentAssembly >** 要素には、1つ **\<の assemblyIdentity >** 子要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="bc7ff-145">属性が存在する場合、要素`<assemblyIdentity>`は、対応するプロセッサアーキテクチャを持つアセンブリにのみ適用されます。 `processorArchitecture`</span><span class="sxs-lookup"><span data-stu-id="bc7ff-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="bc7ff-146">属性が存在しない場合、要素`<assemblyIdentity>`は、任意のプロセッサアーキテクチャを持つアセンブリに適用できます。 `processorArchitecture`</span><span class="sxs-lookup"><span data-stu-id="bc7ff-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="bc7ff-147">次の例では、2つの異なる2つのプロセッサアーキテクチャを対象とする同じ名前の2つのアセンブリの構成ファイルを示しています。これらのバージョンは、同期中に保持されていません。X86 プラットフォームでアプリケーションを実行すると、最初`<assemblyIdentity>`の要素が適用され、もう一方の要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="bc7ff-148">アプリケーションが x86 または ia64 以外のプラットフォームで実行されている場合は、両方とも無視されます。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="bc7ff-149">属性のない`processorArchitecture`要素が構成`<assemblyIdentity>`ファイルに含まれており、プラットフォームに一致する要素が含まれていない場合、 `processorArchitecture`属性のない要素が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc7ff-150">例</span><span class="sxs-lookup"><span data-stu-id="bc7ff-150">Example</span></span>  
 <span data-ttu-id="bc7ff-151">次の例は、アセンブリに関する情報を提供する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bc7ff-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc7ff-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc7ff-152">See also</span></span>

- [<span data-ttu-id="bc7ff-153">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="bc7ff-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bc7ff-154">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="bc7ff-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bc7ff-155">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="bc7ff-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
