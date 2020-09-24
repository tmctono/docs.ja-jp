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
ms.openlocfilehash: 6c35e24696be040788a0c44cbb100ebb35d37157
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149570"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="400bb-102">\<system.codedom> 要素</span><span class="sxs-lookup"><span data-stu-id="400bb-102">\<system.codedom> Element</span></span>

<span data-ttu-id="400bb-103">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="400bb-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
## <a name="syntax"></a><span data-ttu-id="400bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="400bb-104">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="400bb-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="400bb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="400bb-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="400bb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="400bb-107">属性</span><span class="sxs-lookup"><span data-stu-id="400bb-107">Attributes</span></span>  

 <span data-ttu-id="400bb-108">なし。</span><span class="sxs-lookup"><span data-stu-id="400bb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="400bb-109">子要素</span><span class="sxs-lookup"><span data-stu-id="400bb-109">Child Elements</span></span>  
  
|<span data-ttu-id="400bb-110">要素</span><span class="sxs-lookup"><span data-stu-id="400bb-110">Element</span></span>|<span data-ttu-id="400bb-111">説明</span><span class="sxs-lookup"><span data-stu-id="400bb-111">Description</span></span>|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|<span data-ttu-id="400bb-112">コンパイラ構成要素のコンテナー。0個以上の要素が含まれてい [\<compiler>](compiler-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="400bb-112">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="400bb-113">親要素</span><span class="sxs-lookup"><span data-stu-id="400bb-113">Parent Elements</span></span>  
  
|<span data-ttu-id="400bb-114">要素</span><span class="sxs-lookup"><span data-stu-id="400bb-114">Element</span></span>|<span data-ttu-id="400bb-115">説明</span><span class="sxs-lookup"><span data-stu-id="400bb-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="400bb-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="400bb-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="400bb-117">解説</span><span class="sxs-lookup"><span data-stu-id="400bb-117">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="400bb-118">.NET Framework バージョン2.0</span><span class="sxs-lookup"><span data-stu-id="400bb-118">.NET Framework Version 2.0</span></span>  

 <span data-ttu-id="400bb-119">要素には、およびなど、 [\<system.codedom>](system-codedom-element.md) .NET Framework と共にインストールされる既定のプロバイダーに加えて、コンピューターにインストールされている言語プロバイダーのコンパイラ構成設定が含まれてい <xref:Microsoft.CSharp.CSharpCodeProvider> <xref:Microsoft.VisualBasic.VBCodeProvider> ます。</span><span class="sxs-lookup"><span data-stu-id="400bb-119">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="400bb-120">[\<compilers>](compilers-element.md)要素に0個以上の要素が含まれてい [\<compiler>](compiler-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="400bb-120">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="400bb-121">各 [\<compiler>](compiler-element.md) 要素は、特定の言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="400bb-121">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="400bb-122">開発者やコンパイラベンダーは、新しい実装のために構成設定をマシン構成ファイル (Machine.config) に追加でき <xref:System.CodeDom.Compiler.CodeDomProvider> ます。</span><span class="sxs-lookup"><span data-stu-id="400bb-122">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="400bb-123">メソッドを使用して、 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> コンピューター上のコンパイラ構成設定によって識別される既定の言語プロバイダーと言語プロバイダーの両方をプログラムによって列挙します。</span><span class="sxs-lookup"><span data-stu-id="400bb-123">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="400bb-124">.NET Framework バージョン1.0 および1.1 では、.NET Framework によって提供される既定の言語プロバイダーが要素で識別され [\<compilers>](compilers-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="400bb-124">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="400bb-125">.NET Framework バージョン2.0 では、既定の言語プロバイダーは要素で識別されません [\<compilers>](compilers-element.md) が、メソッドを使用して列挙でき <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="400bb-125">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="400bb-126">.NET Framework バージョン1.0 および1.1</span><span class="sxs-lookup"><span data-stu-id="400bb-126">.NET Framework Versions 1.0 and 1.1</span></span>  

 <span data-ttu-id="400bb-127">要素には、 [\<system.codedom>](system-codedom-element.md) コンピューター上の言語プロバイダーのコンパイラ構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="400bb-127">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="400bb-128">[\<compilers>](compilers-element.md)要素に0個以上の要素が含まれてい [\<compiler>](compiler-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="400bb-128">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="400bb-129">各 [\<compiler>](compiler-element.md) 要素は、特定の言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="400bb-129">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="400bb-130">.NET Framework は、マシン構成ファイル (Machine.config) 内でコンパイラの初期設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="400bb-130">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="400bb-131">開発者やコンパイラ ベンダーは、新しい <xref:System.CodeDom.Compiler.CodeDomProvider> の実装のために構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="400bb-131">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="400bb-132"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> メソッドを使用して、プログラムによってコンピューターの言語プロバイダーとコンパイラ構成の設定を列挙します。</span><span class="sxs-lookup"><span data-stu-id="400bb-132">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="400bb-133">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="400bb-133">Configuration File</span></span>  

 <span data-ttu-id="400bb-134">この要素は、マシン構成ファイルおよびアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="400bb-134">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="400bb-135">例</span><span class="sxs-lookup"><span data-stu-id="400bb-135">Example</span></span>  

 <span data-ttu-id="400bb-136">次の例は、一般的なコンパイラ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="400bb-136">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="400bb-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="400bb-137">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="400bb-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="400bb-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="400bb-139">コンパイラおよび言語プロバイダー設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="400bb-139">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="400bb-140">\<compiler> 要素</span><span class="sxs-lookup"><span data-stu-id="400bb-140">\<compiler> Element</span></span>](compiler-element.md)
