---
title: <system.codedom> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 19f37095bd01b76fda8b1e29423c413dbdb06a65
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168918"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="c1b85-102">\<system.string > 要素</span><span class="sxs-lookup"><span data-stu-id="c1b85-102">\<system.codedom> Element</span></span>
<span data-ttu-id="c1b85-103">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1b85-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[<span data-ttu-id="c1b85-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c1b85-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c1b85-105">&nbsp;&nbsp; **\<システムの codedom >**</span><span class="sxs-lookup"><span data-stu-id="c1b85-105">&nbsp;&nbsp;**\<system.codedom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1b85-106">構文</span><span class="sxs-lookup"><span data-stu-id="c1b85-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1b85-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c1b85-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c1b85-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1b85-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1b85-109">属性</span><span class="sxs-lookup"><span data-stu-id="c1b85-109">Attributes</span></span>  
 <span data-ttu-id="c1b85-110">なし。</span><span class="sxs-lookup"><span data-stu-id="c1b85-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1b85-111">子要素</span><span class="sxs-lookup"><span data-stu-id="c1b85-111">Child Elements</span></span>  
  
|<span data-ttu-id="c1b85-112">要素</span><span class="sxs-lookup"><span data-stu-id="c1b85-112">Element</span></span>|<span data-ttu-id="c1b85-113">説明</span><span class="sxs-lookup"><span data-stu-id="c1b85-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1b85-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="c1b85-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="c1b85-115">0 個以上の [\<compiler>](compiler-element.md) 要素を含むコンパイラ構成要素のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="c1b85-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1b85-116">親要素</span><span class="sxs-lookup"><span data-stu-id="c1b85-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c1b85-117">要素</span><span class="sxs-lookup"><span data-stu-id="c1b85-117">Element</span></span>|<span data-ttu-id="c1b85-118">説明</span><span class="sxs-lookup"><span data-stu-id="c1b85-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1b85-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c1b85-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="c1b85-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c1b85-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1b85-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="c1b85-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="c1b85-122">.NET Framework バージョン2.0</span><span class="sxs-lookup"><span data-stu-id="c1b85-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="c1b85-123">System.string > 要素には、コンピューターにインストールされている言語プロバイダーのコンパイラ構成設定<xref:Microsoft.CSharp.CSharpCodeProvider>と、.NET Framework と共にインストールされる既定のプロバイダー (やなど) が含まれ[ます。 \<](system-codedom-element.md)<xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="c1b85-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="c1b85-124">[ \<コンパイラの >](compilers-element.md)要素には、0個以上[ \<のコンパイラ >](compiler-element.md)要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1b85-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="c1b85-125">[各\<コンパイラ >](compiler-element.md)要素は、特定の言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1b85-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="c1b85-126">開発者やコンパイラベンダーは、新しい<xref:System.CodeDom.Compiler.CodeDomProvider>実装のために構成設定をマシン構成ファイル (machine.config) に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c1b85-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="c1b85-127"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>メソッドを使用して、コンピューター上のコンパイラ構成設定によって識別される既定の言語プロバイダーと言語プロバイダーの両方をプログラムによって列挙します。</span><span class="sxs-lookup"><span data-stu-id="c1b85-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1b85-128">.NET Framework バージョン1.0 および1.1 では、.NET Framework によって提供される既定の言語プロバイダーは、 [ \<コンパイラの >](compilers-element.md)要素で識別されます。</span><span class="sxs-lookup"><span data-stu-id="c1b85-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="c1b85-129">.NET Framework バージョン2.0 では、 [ \<コンパイラの >](compilers-element.md)要素で既定の言語プロバイダーは識別されませんが、 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A>メソッドを使用して列挙できます。</span><span class="sxs-lookup"><span data-stu-id="c1b85-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="c1b85-130">.NET Framework バージョン1.0 および1.1</span><span class="sxs-lookup"><span data-stu-id="c1b85-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="c1b85-131">System.string > 要素には、コンピューター上の言語プロバイダーのコンパイラ構成設定が含まれています。 [ \<](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="c1b85-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="c1b85-132">[ \<コンパイラの >](compilers-element.md)要素には、0個以上[ \<のコンパイラ >](compiler-element.md)要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1b85-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="c1b85-133">[各\<コンパイラ >](compiler-element.md)要素は、特定の言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1b85-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="c1b85-134">.NET Framework は、マシン構成ファイル (Machine.config) 内でコンパイラの初期設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c1b85-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="c1b85-135">開発者やコンパイラ ベンダーは、新しい <xref:System.CodeDom.Compiler.CodeDomProvider> の実装のために構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c1b85-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="c1b85-136"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> メソッドを使用して、プログラムによってコンピューターの言語プロバイダーとコンパイラ構成の設定を列挙します。</span><span class="sxs-lookup"><span data-stu-id="c1b85-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c1b85-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c1b85-137">Configuration File</span></span>  
 <span data-ttu-id="c1b85-138">この要素は、マシン構成ファイルおよびアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1b85-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1b85-139">例</span><span class="sxs-lookup"><span data-stu-id="c1b85-139">Example</span></span>  
 <span data-ttu-id="c1b85-140">次の例は、一般的なコンパイラ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="c1b85-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1b85-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1b85-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="c1b85-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1b85-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c1b85-143">コンパイラおよび言語プロバイダー設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="c1b85-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c1b85-144">\<compiler> 要素</span><span class="sxs-lookup"><span data-stu-id="c1b85-144">\<compiler> Element</span></span>](compiler-element.md)
