---
title: <compilers> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 1aa096e185ae7f5957f173c03e221a31f30d5200
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172945"
---
# <a name="compilers-element"></a><span data-ttu-id="6e641-102">\<compilers> 要素</span><span class="sxs-lookup"><span data-stu-id="6e641-102">\<compilers> Element</span></span>

<span data-ttu-id="6e641-103">コンパイラ構成要素のコンテナー。0個以上の要素が含まれてい [\<compiler>](compiler-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="6e641-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**

## <a name="syntax"></a><span data-ttu-id="6e641-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e641-104">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e641-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6e641-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6e641-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e641-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e641-107">属性</span><span class="sxs-lookup"><span data-stu-id="6e641-107">Attributes</span></span>  

 <span data-ttu-id="6e641-108">なし。</span><span class="sxs-lookup"><span data-stu-id="6e641-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e641-109">子要素</span><span class="sxs-lookup"><span data-stu-id="6e641-109">Child Elements</span></span>  
  
|<span data-ttu-id="6e641-110">要素</span><span class="sxs-lookup"><span data-stu-id="6e641-110">Element</span></span>|<span data-ttu-id="6e641-111">説明</span><span class="sxs-lookup"><span data-stu-id="6e641-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e641-112">\<compiler> 要素</span><span class="sxs-lookup"><span data-stu-id="6e641-112">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="6e641-113">言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e641-113">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e641-114">親要素</span><span class="sxs-lookup"><span data-stu-id="6e641-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6e641-115">要素</span><span class="sxs-lookup"><span data-stu-id="6e641-115">Element</span></span>|<span data-ttu-id="6e641-116">説明</span><span class="sxs-lookup"><span data-stu-id="6e641-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e641-117">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="6e641-117">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="6e641-118">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6e641-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="6e641-119">\<system.codedom> 要素</span><span class="sxs-lookup"><span data-stu-id="6e641-119">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="6e641-120">使用可能な言語プロバイダーのコンパイラ構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e641-120">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e641-121">解説</span><span class="sxs-lookup"><span data-stu-id="6e641-121">Remarks</span></span>  

 <span data-ttu-id="6e641-122">要素には、 [\<compilers>](compilers-element.md) コンピューター上の言語プロバイダーのコンパイラ構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e641-122">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="6e641-123">各 [\<compiler>](compiler-element.md) 要素は、特定の言語プロバイダーのコンパイラ構成属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e641-123">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="6e641-124">.NET Framework は、マシン構成ファイル (Machine.config) の初期コンパイラおよび言語プロバイダー設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6e641-124">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="6e641-125">開発者やコンパイラ ベンダーは、新しい <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> の実装のために構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6e641-125">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="6e641-126"><xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> メソッドを使用して、プログラムによってコンピューターの言語プロバイダーとコンパイラ構成の設定を列挙します。</span><span class="sxs-lookup"><span data-stu-id="6e641-126">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="6e641-127">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="6e641-127">Configuration File</span></span>  

 <span data-ttu-id="6e641-128">この要素は、マシン構成ファイルおよびアプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e641-128">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e641-129">例</span><span class="sxs-lookup"><span data-stu-id="6e641-129">Example</span></span>  

 <span data-ttu-id="6e641-130">次の例は、一般的なコンパイラ構成要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="6e641-130">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e641-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e641-131">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="6e641-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6e641-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6e641-133">コンパイラおよび言語プロバイダー設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="6e641-133">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6e641-134">\<compiler> 要素</span><span class="sxs-lookup"><span data-stu-id="6e641-134">\<compiler> Element</span></span>](compiler-element.md)
