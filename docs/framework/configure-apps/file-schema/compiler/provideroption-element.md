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
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155402"
---
# <a name="provideroption-element"></a><span data-ttu-id="33f4b-102">\<providerOption> 要素</span><span class="sxs-lookup"><span data-stu-id="33f4b-102">\<providerOption> Element</span></span>
<span data-ttu-id="33f4b-103">言語プロバイダーのコンパイラバージョン属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="33f4b-103">Specifies the compiler version attributes for a language provider.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a><span data-ttu-id="33f4b-104">構文</span><span class="sxs-lookup"><span data-stu-id="33f4b-104">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33f4b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="33f4b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="33f4b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="33f4b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33f4b-107">属性</span><span class="sxs-lookup"><span data-stu-id="33f4b-107">Attributes</span></span>  
  
|<span data-ttu-id="33f4b-108">属性</span><span class="sxs-lookup"><span data-stu-id="33f4b-108">Attribute</span></span>|<span data-ttu-id="33f4b-109">説明</span><span class="sxs-lookup"><span data-stu-id="33f4b-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="33f4b-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="33f4b-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="33f4b-111">オプションの名前を指定します。たとえば、"CompilerVersion" のようになります。</span><span class="sxs-lookup"><span data-stu-id="33f4b-111">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="33f4b-112">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="33f4b-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="33f4b-113">オプションの値を指定します。たとえば、"v 3.5" のようになります。</span><span class="sxs-lookup"><span data-stu-id="33f4b-113">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33f4b-114">子要素</span><span class="sxs-lookup"><span data-stu-id="33f4b-114">Child Elements</span></span>  
 <span data-ttu-id="33f4b-115">なし。</span><span class="sxs-lookup"><span data-stu-id="33f4b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33f4b-116">親要素</span><span class="sxs-lookup"><span data-stu-id="33f4b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="33f4b-117">要素</span><span class="sxs-lookup"><span data-stu-id="33f4b-117">Element</span></span>|<span data-ttu-id="33f4b-118">Description</span><span class="sxs-lookup"><span data-stu-id="33f4b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33f4b-119">\<configuration>Element</span><span class="sxs-lookup"><span data-stu-id="33f4b-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="33f4b-120">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="33f4b-120">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="33f4b-121">\<system.codedom>Element</span><span class="sxs-lookup"><span data-stu-id="33f4b-121">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="33f4b-122">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="33f4b-122">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="33f4b-123">\<compilers>Element</span><span class="sxs-lookup"><span data-stu-id="33f4b-123">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="33f4b-124">コンパイラ構成要素のコンテナー。0個以上の要素が含まれてい `<compiler>` ます。</span><span class="sxs-lookup"><span data-stu-id="33f4b-124">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="33f4b-125">\<compiler>Element</span><span class="sxs-lookup"><span data-stu-id="33f4b-125">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="33f4b-126">言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="33f4b-126">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33f4b-127">解説</span><span class="sxs-lookup"><span data-stu-id="33f4b-127">Remarks</span></span>  
 <span data-ttu-id="33f4b-128">.NET Framework バージョン3.5 では、Code Document Object Model (CodeDOM) コードプロバイダーは、要素を使用してプロバイダー固有のオプションをサポートでき `<providerOption>` ます。</span><span class="sxs-lookup"><span data-stu-id="33f4b-128">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="33f4b-129">.NET Framework 3.5 には、更新された .NET Framework 2.0 アセンブリが含まれており、新しい型を含む新しいバージョンの3.5 アセンブリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="33f4b-129">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="33f4b-130">Microsoft C# および Visual Basic コードプロバイダーは .NET Framework 2.0 アセンブリに含まれていますが、バージョン3.5 コンパイラをサポートするように更新されています。</span><span class="sxs-lookup"><span data-stu-id="33f4b-130">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="33f4b-131">既定では、更新されたコードプロバイダーはバージョン2.0 コンパイラのコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="33f4b-131">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="33f4b-132">要素を使用し `<providerOption>` て、ターゲットコンパイラのバージョンを3.5 に変更できます。</span><span class="sxs-lookup"><span data-stu-id="33f4b-132">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="33f4b-133">これを行うには、属性に "CompilerVersion" を指定し、 `name` 属性に「v 3.5」を指定し `value` ます。</span><span class="sxs-lookup"><span data-stu-id="33f4b-133">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="33f4b-134">バージョン番号の前には、小文字の "v" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33f4b-134">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="33f4b-135">`<providerOption>`.NET Framework 2.0 machine.config またはルート web.config ファイルに要素を追加することで、バージョン指定をグローバルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="33f4b-135">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="33f4b-136">Machine.config ファイルで既定のコンパイラのバージョンを3.5 に更新した場合は、アプリケーション構成ファイルの要素を使用して、アプリケーションごとに2.0 に戻すことができ `<providerOption>` ます。</span><span class="sxs-lookup"><span data-stu-id="33f4b-136">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="33f4b-137">CodeDOM コードプロバイダーの実装者は、型のパラメーターを受け取るコンストラクターを指定することによって、カスタムオプションを処理でき `providerOptions` <xref:System.Collections.Generic.IDictionary%602> ます。</span><span class="sxs-lookup"><span data-stu-id="33f4b-137">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33f4b-138">例</span><span class="sxs-lookup"><span data-stu-id="33f4b-138">Example</span></span>  
 <span data-ttu-id="33f4b-139">次の例は、C# コードプロバイダーのバージョン3.5 を使用するように指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="33f4b-139">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="33f4b-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="33f4b-140">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="33f4b-141">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="33f4b-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="33f4b-142">\<compilers>Element</span><span class="sxs-lookup"><span data-stu-id="33f4b-142">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="33f4b-143">完全修飾型名の指定</span><span class="sxs-lookup"><span data-stu-id="33f4b-143">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="33f4b-144">[compilation の compilers の compiler 要素 (ASP.NET 設定スキーマ)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="33f4b-144">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
