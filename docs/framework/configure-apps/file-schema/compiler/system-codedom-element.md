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
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155389"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="950b4-102">\<要素>コードダム</span><span class="sxs-lookup"><span data-stu-id="950b4-102">\<system.codedom> Element</span></span>
<span data-ttu-id="950b4-103">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="950b4-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[<span data-ttu-id="950b4-104">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="950b4-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="950b4-105">&nbsp;&nbsp;**\<コードダム>**</span><span class="sxs-lookup"><span data-stu-id="950b4-105">&nbsp;&nbsp;**\<system.codedom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="950b4-106">構文</span><span class="sxs-lookup"><span data-stu-id="950b4-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="950b4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="950b4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="950b4-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="950b4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="950b4-109">属性</span><span class="sxs-lookup"><span data-stu-id="950b4-109">Attributes</span></span>  
 <span data-ttu-id="950b4-110">[なし] :</span><span class="sxs-lookup"><span data-stu-id="950b4-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="950b4-111">子要素</span><span class="sxs-lookup"><span data-stu-id="950b4-111">Child Elements</span></span>  
  
|<span data-ttu-id="950b4-112">要素</span><span class="sxs-lookup"><span data-stu-id="950b4-112">Element</span></span>|<span data-ttu-id="950b4-113">説明</span><span class="sxs-lookup"><span data-stu-id="950b4-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="950b4-114">\<コンパイラ></span><span class="sxs-lookup"><span data-stu-id="950b4-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="950b4-115">コンパイラ構成要素のコンテナ。コンパイラ[\<>](compiler-element.md)要素が 0 個以上含まれています。</span><span class="sxs-lookup"><span data-stu-id="950b4-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="950b4-116">親要素</span><span class="sxs-lookup"><span data-stu-id="950b4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="950b4-117">要素</span><span class="sxs-lookup"><span data-stu-id="950b4-117">Element</span></span>|<span data-ttu-id="950b4-118">説明</span><span class="sxs-lookup"><span data-stu-id="950b4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="950b4-119">\<構成></span><span class="sxs-lookup"><span data-stu-id="950b4-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="950b4-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="950b4-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="950b4-121">解説</span><span class="sxs-lookup"><span data-stu-id="950b4-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="950b4-122">.NET フレームワーク バージョン 2.0</span><span class="sxs-lookup"><span data-stu-id="950b4-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="950b4-123">[ \<system.codedom>](system-codedom-element.md)要素には、.NET Framework と共にインストールされる既定のプロバイダに加えて、<xref:Microsoft.CSharp.CSharpCodeProvider>コンピュータにインストールされている言語プロバイダのコンパイラ構成設定が<xref:Microsoft.VisualBasic.VBCodeProvider>含まれています。</span><span class="sxs-lookup"><span data-stu-id="950b4-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="950b4-124">[\<コンパイラ>](compilers-element.md)要素には、0 個以上[\<のコンパイラ>](compiler-element.md)要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="950b4-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="950b4-125">各[\<コンパイラ>要素は](compiler-element.md)、特定の言語プロバイダのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="950b4-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="950b4-126">開発者およびコンパイラ ベンダは、新しい<xref:System.CodeDom.Compiler.CodeDomProvider>実装用にマシン構成ファイル (Machine.config) に構成設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="950b4-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="950b4-127">このメソッド<xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>を使用して、既定の言語プロバイダーと、コンピューターのコンパイラ構成設定で識別される言語プロバイダーの両方をプログラムで列挙します。</span><span class="sxs-lookup"><span data-stu-id="950b4-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="950b4-128">.NET Framework バージョン 1.0 および 1.1 では、.NET Framework によって提供される既定の言語プロバイダーが[\<コンパイラ>](compilers-element.md)要素で識別されます。</span><span class="sxs-lookup"><span data-stu-id="950b4-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="950b4-129">.NET Framework Version 2.0 では、既定の言語プロバイダは[\<コンパイラ>](compilers-element.md)要素で識別されませんが、メソッドを<xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A>使用して列挙できます。</span><span class="sxs-lookup"><span data-stu-id="950b4-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="950b4-130">.NET フレームワーク バージョン 1.0 および 1.1</span><span class="sxs-lookup"><span data-stu-id="950b4-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="950b4-131">system.codedom>要素には、コンピューター上の言語プロバイダーのコンパイラ構成設定が含まれています。 [ \<](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="950b4-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="950b4-132">[\<コンパイラ>](compilers-element.md)要素には、0 個以上[\<のコンパイラ>](compiler-element.md)要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="950b4-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="950b4-133">各[\<コンパイラ>要素は](compiler-element.md)、特定の言語プロバイダのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="950b4-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="950b4-134">.NET Framework は、マシン構成ファイル (Machine.config) 内でコンパイラの初期設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="950b4-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="950b4-135">開発者やコンパイラ ベンダーは、新しい <xref:System.CodeDom.Compiler.CodeDomProvider> の実装のために構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="950b4-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="950b4-136"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> メソッドを使用して、プログラムによってコンピューターの言語プロバイダーとコンパイラ構成の設定を列挙します。</span><span class="sxs-lookup"><span data-stu-id="950b4-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="950b4-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="950b4-137">Configuration File</span></span>  
 <span data-ttu-id="950b4-138">この要素は、マシン構成ファイルおよびアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="950b4-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="950b4-139">例</span><span class="sxs-lookup"><span data-stu-id="950b4-139">Example</span></span>  
 <span data-ttu-id="950b4-140">次の例は、一般的なコンパイラ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="950b4-140">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="950b4-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="950b4-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="950b4-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="950b4-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="950b4-143">コンパイラおよび言語プロバイダー設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="950b4-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="950b4-144">\<コンパイラ>要素</span><span class="sxs-lookup"><span data-stu-id="950b4-144">\<compiler> Element</span></span>](compiler-element.md)
