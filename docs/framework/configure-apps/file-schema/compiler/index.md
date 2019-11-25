---
title: コンパイラおよび言語プロバイダー設定のスキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: 5b1f9684ad26d4a03769af287fc8b0c0c7c4cc1a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088682"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="4d960-102">コンパイラおよび言語プロバイダー設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="4d960-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="4d960-103">コンパイラおよび言語プロバイダー設定は、使用可能な言語プロバイダーのコンパイラ構成要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d960-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="4d960-104">各コンパイラ構成要素は、コード プロバイダーの型名、コンパイラ パラメーター、サポートされる言語名、およびサポートされるファイル拡張子を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d960-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
<span data-ttu-id="4d960-105">.NET Framework は、マシン構成ファイル (Machine.config) 内でコンパイラの初期設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d960-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="4d960-106">開発者やコンパイラ ベンダーは、新しい <xref:System.CodeDom.Compiler.CodeDomProvider> の実装のために構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4d960-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="4d960-107"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> メソッドを使用して、プログラムによってコンピューターの言語プロバイダーとコンパイラ構成の設定を列挙します。</span><span class="sxs-lookup"><span data-stu-id="4d960-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
<span data-ttu-id="4d960-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d960-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4d960-109">&nbsp;&nbsp;[ **\<システムの >** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d960-109">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="4d960-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<コンパイラ**](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d960-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="4d960-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**コンパイラ >** ](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d960-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>
  
|<span data-ttu-id="4d960-112">要素</span><span class="sxs-lookup"><span data-stu-id="4d960-112">Element</span></span>|<span data-ttu-id="4d960-113">説明</span><span class="sxs-lookup"><span data-stu-id="4d960-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d960-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="4d960-114">\<system.codedom></span></span>](system-codedom-element.md)|<span data-ttu-id="4d960-115">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d960-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="4d960-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="4d960-116">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="4d960-117">0 個以上の [\<compiler>](compiler-element.md) 要素を含むコンパイラ構成要素のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="4d960-117">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="4d960-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="4d960-118">\<compiler></span></span>](compiler-element.md)|<span data-ttu-id="4d960-119">言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d960-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4d960-120">例</span><span class="sxs-lookup"><span data-stu-id="4d960-120">Example</span></span>  
 <span data-ttu-id="4d960-121">次の例は、一般的なコンパイラ構成要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d960-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d960-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d960-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="4d960-123">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="4d960-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4d960-124">\<compiler> 要素</span><span class="sxs-lookup"><span data-stu-id="4d960-124">\<compiler> Element</span></span>](compiler-element.md)
