---
title: <providerOption> 要素
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 8d90364e34aa15bbd38e82ec70ec44616d7360f8
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70167668"
---
# <a name="provideroption-element"></a><span data-ttu-id="ac6c7-102">\<providerOption > 要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-102">\<providerOption> Element</span></span>
<span data-ttu-id="ac6c7-103">言語プロバイダーのコンパイラバージョン属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
[<span data-ttu-id="ac6c7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ac6c7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ac6c7-105">&nbsp;&nbsp;[ **\<システムの codedom >** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac6c7-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="ac6c7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<コンパイラの >** ](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac6c7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>  
<span data-ttu-id="ac6c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<コンパイラの >** ](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac6c7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>  
<span data-ttu-id="ac6c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<providerOption >**</span><span class="sxs-lookup"><span data-stu-id="ac6c7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac6c7-109">構文</span><span class="sxs-lookup"><span data-stu-id="ac6c7-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac6c7-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ac6c7-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac6c7-112">属性</span><span class="sxs-lookup"><span data-stu-id="ac6c7-112">Attributes</span></span>  
  
|<span data-ttu-id="ac6c7-113">属性</span><span class="sxs-lookup"><span data-stu-id="ac6c7-113">Attribute</span></span>|<span data-ttu-id="ac6c7-114">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c7-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ac6c7-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="ac6c7-116">オプションの名前を指定します。たとえば、"CompilerVersion" のようになります。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="ac6c7-117">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="ac6c7-118">オプションの値を指定します。たとえば、"v 3.5" のようになります。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac6c7-119">子要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-119">Child Elements</span></span>  
 <span data-ttu-id="ac6c7-120">なし。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac6c7-121">親要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ac6c7-122">要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-122">Element</span></span>|<span data-ttu-id="ac6c7-123">説明</span><span class="sxs-lookup"><span data-stu-id="ac6c7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac6c7-124">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="ac6c7-125">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="ac6c7-126">\<system.string > 要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="ac6c7-127">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="ac6c7-128">\<compilers> 要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="ac6c7-129">コンパイラ構成要素のコンテナー0 個以上含む`<compiler>`要素。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="ac6c7-130">\<compiler> 要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="ac6c7-131">言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac6c7-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac6c7-132">Remarks</span></span>  
 <span data-ttu-id="ac6c7-133">.NET Framework バージョン3.5 では、Code Document Object Model (CodeDOM) コードプロバイダーは、 `<providerOption>`要素を使用してプロバイダー固有のオプションをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="ac6c7-134">.NET Framework 3.5 には、更新された .NET Framework 2.0 アセンブリが含まれており、新しい型を含む新しいバージョンの3.5 アセンブリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="ac6c7-135">Microsoft C#および Visual Basic コードプロバイダーは .NET Framework 2.0 アセンブリに含まれていますが、バージョン3.5 コンパイラをサポートするように更新されています。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="ac6c7-136">既定では、更新されたコードプロバイダーはバージョン2.0 コンパイラのコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="ac6c7-137">`<providerOption>`要素を使用して、ターゲットコンパイラのバージョンを3.5 に変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="ac6c7-138">これを行うには、属性に "CompilerVersion `name` " を指定し、 `value`属性に「v 3.5」を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="ac6c7-139">バージョン番号の前には、小文字の "v" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="ac6c7-140">.NET Framework 2.0 machine.config またはルート web.config ファイルに`<providerOption>`要素を追加することで、バージョン指定をグローバルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="ac6c7-141">Machine.config ファイルで既定のコンパイラのバージョンを3.5 に更新した場合は、アプリケーション構成ファイルの`<providerOption>`要素を使用して、アプリケーションごとに2.0 に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="ac6c7-142">CodeDOM コードプロバイダーの実装者は、型`providerOptions` <xref:System.Collections.Generic.IDictionary%602>のパラメーターを受け取るコンストラクターを指定することによって、カスタムオプションを処理できます。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac6c7-143">例</span><span class="sxs-lookup"><span data-stu-id="ac6c7-143">Example</span></span>  
 <span data-ttu-id="ac6c7-144">次の例は、 C#コードプロバイダーのバージョン3.5 を使用するように指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac6c7-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac6c7-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac6c7-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="ac6c7-146">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="ac6c7-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ac6c7-147">\<compilers> 要素</span><span class="sxs-lookup"><span data-stu-id="ac6c7-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="ac6c7-148">完全修飾型名の指定</span><span class="sxs-lookup"><span data-stu-id="ac6c7-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="ac6c7-149">[コンパイル用コンパイラのコンパイラ要素 (ASP.NET Settings スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ac6c7-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
