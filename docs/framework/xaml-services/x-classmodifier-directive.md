---
title: x:ClassModifier ディレクティブ
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 5daff0567c1b1415fe994f6e39b4079cb2ab7346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053819"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="adc20-102">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="adc20-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="adc20-103">が指定されて`x:Class`いる場合に XAML のコンパイル動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="adc20-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="adc20-104">`class`具体的には、 `Public`アクセスレベル (既定値) を持つ部分を作成するのでは`x:Class`なく、 `NotPublic`指定されたがアクセスレベルで作成されます。</span><span class="sxs-lookup"><span data-stu-id="adc20-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="adc20-105">この動作は、生成されたアセンブリのクラスのアクセスレベルに影響します。</span><span class="sxs-lookup"><span data-stu-id="adc20-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="adc20-106">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="adc20-106">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="adc20-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="adc20-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="adc20-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="adc20-108">*NotPublic*</span></span>|<span data-ttu-id="adc20-109">を指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>するために渡す正確な文字列は、使用する分離コードプログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="adc20-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="adc20-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adc20-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="adc20-111">依存関係</span><span class="sxs-lookup"><span data-stu-id="adc20-111">Dependencies</span></span>  
 <span data-ttu-id="adc20-112">[x:Class](x-class-directive.md)も同じ要素に指定する必要があり、その要素はページのルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="adc20-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="adc20-113">詳細については、「 [ \[4.3.1.8\] 」セクション](https://go.microsoft.com/fwlink/?LinkId=114525)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adc20-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adc20-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="adc20-114">Remarks</span></span>  
 <span data-ttu-id="adc20-115">.NET Framework XAML サービス`x:ClassModifier`の使用におけるの値は、プログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="adc20-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="adc20-116">使用する文字列は、各言語がを実装<xref:System.CodeDom.Compiler.CodeDomProvider>する方法、およびが返す型コンバーターによって異なります。これにより、との<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>意味が定義され、その言語で大文字と<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>小文字が区別されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="adc20-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="adc20-117">C#では、を指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>するために渡す`internal`文字列はです。</span><span class="sxs-lookup"><span data-stu-id="adc20-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="adc20-118">Microsoft Visual Basic .net の場合、指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>するために渡す文字列は`Friend`です。</span><span class="sxs-lookup"><span data-stu-id="adc20-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="adc20-119">/Cli C++では、XAML のコンパイルをサポートするターゲットは存在しません。したがって、渡す値は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="adc20-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="adc20-120"><xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>を指定することも`public`できC#ます`Public` (in、Visual Basic)。ただし<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 、は、が<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>既に既定の動作であるため、を指定することはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="adc20-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="adc20-121">`private`でC#は、入れ子になったクラス参照が XAML `x:ClassModifier` <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>でサポートされていないため、修飾子は同じ効果を持つため、ユーザーコードのアクセスレベルに関する同じ制限を持つその他の値は、には関係ありません.</span><span class="sxs-lookup"><span data-stu-id="adc20-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="adc20-122">セキュリティに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="adc20-122">Security Notes</span></span>  
 <span data-ttu-id="adc20-123">で`x:ClassModifier`宣言されているアクセスレベルは、特定のフレームワークとその機能によって解釈されることもあります。</span><span class="sxs-lookup"><span data-stu-id="adc20-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="adc20-124">Wpf に`x:ClassModifier`は、の型を読み込んでインスタンス`internal`化する機能が含まれています。これは、そのクラスが、パッケージ URI 参照を通じて WPF リソースから参照されている場合です。</span><span class="sxs-lookup"><span data-stu-id="adc20-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="adc20-125">このケースの結果として、他のフレームワークによって実装されている可能性が`x:ClassModifier`ある場合は、を排他的に使用して、可能なすべてのインスタンス化試行をブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="adc20-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc20-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="adc20-126">See also</span></span>

- [<span data-ttu-id="adc20-127">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="adc20-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="adc20-128">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="adc20-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="adc20-129">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="adc20-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="adc20-130">セキュリティ (WPF)</span><span class="sxs-lookup"><span data-stu-id="adc20-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="adc20-131">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="adc20-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
