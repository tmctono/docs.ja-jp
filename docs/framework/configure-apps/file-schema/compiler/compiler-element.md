---
title: <compiler> 要素
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: a19cf8182cdb338fd8596ef38311916de0daae37
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168942"
---
# <a name="compiler-element"></a><span data-ttu-id="e50cc-102">\<compiler> 要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-102">\<compiler> Element</span></span>

<span data-ttu-id="e50cc-103">言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[<span data-ttu-id="e50cc-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e50cc-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e50cc-105">&nbsp;&nbsp;[ **\<システムの codedom >** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="e50cc-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="e50cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<コンパイラの >** ](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="e50cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>  
<span data-ttu-id="e50cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<コンパイラの >**</span><span class="sxs-lookup"><span data-stu-id="e50cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="e50cc-108">構文</span><span class="sxs-lookup"><span data-stu-id="e50cc-108">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e50cc-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-109">Attributes and Elements</span></span>

<span data-ttu-id="e50cc-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e50cc-111">属性</span><span class="sxs-lookup"><span data-stu-id="e50cc-111">Attributes</span></span>

|<span data-ttu-id="e50cc-112">属性</span><span class="sxs-lookup"><span data-stu-id="e50cc-112">Attribute</span></span>|<span data-ttu-id="e50cc-113">説明</span><span class="sxs-lookup"><span data-stu-id="e50cc-113">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="e50cc-114">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e50cc-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e50cc-115">コンパイル用の追加のコンパイラ固有の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="e50cc-116">`compilerOptions`属性の値は、通常、コンパイラのコンパイラオプションのトピックに示されています。</span><span class="sxs-lookup"><span data-stu-id="e50cc-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="e50cc-117">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e50cc-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="e50cc-118">言語プロバイダーのソースファイルで使用されるファイル名拡張子のセミコロン区切りのリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-118">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="e50cc-119">たとえば、".cs" のようになります。</span><span class="sxs-lookup"><span data-stu-id="e50cc-119">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="e50cc-120">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e50cc-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="e50cc-121">言語プロバイダーでサポートされている言語名のセミコロン区切りのリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-121">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="e50cc-122">たとえば、"c#; cs; csharp" のようになります。</span><span class="sxs-lookup"><span data-stu-id="e50cc-122">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="e50cc-123">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="e50cc-123">Required attribute.</span></span><br /><br /> <span data-ttu-id="e50cc-124">プロバイダーの実装を含むアセンブリの名前を含む、言語プロバイダーの型名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-124">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="e50cc-125">型名は、 [「完全修飾型名の指定](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)」で定義されている要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e50cc-125">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="e50cc-126">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="e50cc-126">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e50cc-127">既定のコンパイラの警告レベルを指定します。言語プロバイダーがコンパイル警告をエラーとして扱うレベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-127">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e50cc-128">子要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-128">Child Elements</span></span>

|<span data-ttu-id="e50cc-129">要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-129">Element</span></span>|<span data-ttu-id="e50cc-130">説明</span><span class="sxs-lookup"><span data-stu-id="e50cc-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e50cc-131">\<providerOption > 要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-131">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="e50cc-132">言語プロバイダーのコンパイラバージョン属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-132">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e50cc-133">親要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-133">Parent Elements</span></span>

|<span data-ttu-id="e50cc-134">要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-134">Element</span></span>|<span data-ttu-id="e50cc-135">説明</span><span class="sxs-lookup"><span data-stu-id="e50cc-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e50cc-136">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-136">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="e50cc-137">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e50cc-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="e50cc-138">\<system.string > 要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-138">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="e50cc-139">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-139">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="e50cc-140">\<compilers> 要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-140">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="e50cc-141">コンパイラ構成要素のコンテナー0 個以上含む`<compiler>`要素。</span><span class="sxs-lookup"><span data-stu-id="e50cc-141">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e50cc-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="e50cc-142">Remarks</span></span>

<span data-ttu-id="e50cc-143">各`<compiler>`要素は、特定の言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-143">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="e50cc-144">プロバイダーは、特定<xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>の言語のクラスを拡張し`<compiler>`ます。要素は、言語プロバイダーのコンパイラとコードジェネレーターの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-144">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="e50cc-145">.NET Framework は、マシン構成ファイル (Machine.config) 内でコンパイラの初期設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-145">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="e50cc-146">開発者やコンパイラ ベンダーは、新しい <xref:System.CodeDom.Compiler.CodeDomProvider> の実装のために構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e50cc-146">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="e50cc-147"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> メソッドを使用して、プログラムによってコンピューターの言語プロバイダーとコンパイラ構成の設定を列挙します。</span><span class="sxs-lookup"><span data-stu-id="e50cc-147">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="e50cc-148">アプリケーションまたは Web 構成ファイル内のコンパイラ要素は、マシン構成ファイル内の設定を補完またはオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="e50cc-148">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="e50cc-149">同じ言語名または同じファイル拡張子に対して複数のプロバイダー実装が構成されている場合、最後に一致した構成によって、その言語名またはファイル拡張子に対して以前に構成されたすべてのプロバイダーがオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="e50cc-149">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="e50cc-150">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="e50cc-150">Configuration File</span></span>

<span data-ttu-id="e50cc-151">この要素は、マシン構成ファイルおよびアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e50cc-151">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="e50cc-152">例</span><span class="sxs-lookup"><span data-stu-id="e50cc-152">Example</span></span>

<span data-ttu-id="e50cc-153">次の例は、一般的なコンパイラ構成要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="e50cc-153">The following example illustrates a typical compiler configuration element:</span></span>

```xml
<configuration>
  <system.codedom>
    <compilers>
      <!-- zero or more compiler elements -->
      <compiler
        language="c#;cs;csharp"
        extension=".cs"
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"
        compilerOptions="/optimize"
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e50cc-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="e50cc-154">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="e50cc-155">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="e50cc-155">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e50cc-156">\<compilers> 要素</span><span class="sxs-lookup"><span data-stu-id="e50cc-156">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="e50cc-157">完全修飾型名の指定</span><span class="sxs-lookup"><span data-stu-id="e50cc-157">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="e50cc-158">[コンパイル用コンパイラのコンパイラ要素 (ASP.NET Settings スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e50cc-158">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
