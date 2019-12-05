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
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837234"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="f0670-102">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f0670-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="f0670-103">`x:Class` が指定されている場合に XAML のコンパイル動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="f0670-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="f0670-104">具体的には、`Public` アクセスレベル (既定値) を持つ部分 `class` を作成するのではなく、指定された `x:Class` が `NotPublic` アクセスレベルで作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0670-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="f0670-105">この動作は、生成されたアセンブリのクラスのアクセスレベルに影響します。</span><span class="sxs-lookup"><span data-stu-id="f0670-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="f0670-106">XAML 属性の使用</span><span class="sxs-lookup"><span data-stu-id="f0670-106">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f0670-107">XAML の値</span><span class="sxs-lookup"><span data-stu-id="f0670-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0670-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="f0670-108">*NotPublic*</span></span>|<span data-ttu-id="f0670-109"><xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> と <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> を指定するために渡す文字列は、使用する分離コードプログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f0670-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="f0670-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0670-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="f0670-111">の依存関係</span><span class="sxs-lookup"><span data-stu-id="f0670-111">Dependencies</span></span>  
 <span data-ttu-id="f0670-112">[x:Class](x-class-directive.md)も同じ要素に指定する必要があり、その要素はページのルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0670-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="f0670-113">詳細については、「 [\[\]」セクション 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0670-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0670-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0670-114">Remarks</span></span>  
 <span data-ttu-id="f0670-115">XAML サービスの使用 .NET Framework の `x:ClassModifier` の値は、プログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f0670-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="f0670-116">使用する文字列は、各言語が <xref:System.CodeDom.Compiler.CodeDomProvider> を実装する方法、および <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> と <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>の意味を定義するために返す型コンバーターと、その言語で大文字と小文字を区別するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f0670-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="f0670-117">のC#場合、<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> を指定するために渡す文字列は `internal`です。</span><span class="sxs-lookup"><span data-stu-id="f0670-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="f0670-118">Microsoft Visual Basic .NET の場合、<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> を指定するために渡す文字列は `Friend`です。</span><span class="sxs-lookup"><span data-stu-id="f0670-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="f0670-119">/Cli C++では、XAML のコンパイルをサポートするターゲットは存在しません。したがって、渡す値は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f0670-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="f0670-120"><xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> を指定することもできますC#(`public` では、`Public` Visual Basic)。ただし、<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> は既に既定の動作であるため、<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> の指定はほとんど行われません。</span><span class="sxs-lookup"><span data-stu-id="f0670-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="f0670-121">入れ子になったクラス参照は XAML でサポートされていないC#ため、<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 修飾子は同じ効果を持つため、ユーザーコードのアクセスレベル制限が同等の他の値 (`private` など) は `x:ClassModifier` には関係ありません。</span><span class="sxs-lookup"><span data-stu-id="f0670-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="f0670-122">セキュリティに関するメモ</span><span class="sxs-lookup"><span data-stu-id="f0670-122">Security Notes</span></span>  
 <span data-ttu-id="f0670-123">`x:ClassModifier` で宣言したアクセスレベルは、特定のフレームワークとその機能によって解釈されることもあります。</span><span class="sxs-lookup"><span data-stu-id="f0670-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="f0670-124">WPF には、`x:ClassModifier` が `internal`されている型を読み込んでインスタンス化する機能が含まれています。これは、そのクラスが、パッケージ URI 参照を通じて WPF リソースから参照されている場合です。</span><span class="sxs-lookup"><span data-stu-id="f0670-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="f0670-125">このケースの結果として、他のフレームワークによって実装されている可能性がある他の場合は、`x:ClassModifier` に排他的に依存して、可能性のあるすべてのインスタンス化試行をブロックすることは避けてください。</span><span class="sxs-lookup"><span data-stu-id="f0670-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0670-126">参照</span><span class="sxs-lookup"><span data-stu-id="f0670-126">See also</span></span>

- [<span data-ttu-id="f0670-127">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f0670-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="f0670-128">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="f0670-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="f0670-129">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f0670-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="f0670-130">セキュリティ (WPF)</span><span class="sxs-lookup"><span data-stu-id="f0670-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="f0670-131">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="f0670-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
