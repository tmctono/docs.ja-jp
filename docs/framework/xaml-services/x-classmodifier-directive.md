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
ms.openlocfilehash: fdbc69634e86992e71cfccdc080829b6b45f963c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971900"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="f59eb-102">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f59eb-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="f59eb-103">XAML のコンパイルの動作を変更するときに`x:Class`も提供されます。</span><span class="sxs-lookup"><span data-stu-id="f59eb-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="f59eb-104">部分を作成する代わりに、具体的には、`class`を持つ、`Public`アクセス レベル (既定)、指定された`x:Class`で作成、`NotPublic`アクセス レベル。</span><span class="sxs-lookup"><span data-stu-id="f59eb-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="f59eb-105">この動作では、生成されたアセンブリ内のクラスのアクセス レベルに影響します。</span><span class="sxs-lookup"><span data-stu-id="f59eb-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="f59eb-106">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="f59eb-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f59eb-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="f59eb-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f59eb-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="f59eb-108">*NotPublic*</span></span>|<span data-ttu-id="f59eb-109">正確な文字列を指定して渡す<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>と<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>を使用する分離コードのプログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f59eb-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="f59eb-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f59eb-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="f59eb-111">依存関係</span><span class="sxs-lookup"><span data-stu-id="f59eb-111">Dependencies</span></span>  
 <span data-ttu-id="f59eb-112">[X:class](x-class-directive.md)も同じ要素に提供される必要があり、その要素は、ページのルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59eb-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="f59eb-113">詳細については、次を参照してください。 [ \[MS XAML\]セクション 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525)します。</span><span class="sxs-lookup"><span data-stu-id="f59eb-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f59eb-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="f59eb-114">Remarks</span></span>  
 <span data-ttu-id="f59eb-115">値`x:ClassModifier`.NET Framework XAML サービスの使用状況はプログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f59eb-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="f59eb-116">使用する文字列は、各言語の実装に依存、<xref:System.CodeDom.Compiler.CodeDomProvider>よぶ型コンバーターを返しますの意味を定義する<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>と<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>、その言語が、大文字小文字を区別するかどうか。</span><span class="sxs-lookup"><span data-stu-id="f59eb-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="f59eb-117">C# の場合、文字列を指定する渡す<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>は`internal`します。</span><span class="sxs-lookup"><span data-stu-id="f59eb-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="f59eb-118">Microsoft Visual Basic .net の指定に渡す文字列<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>は`Friend`します。</span><span class="sxs-lookup"><span data-stu-id="f59eb-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="f59eb-119">[!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]ターゲットをサポートする XAML をコンパイルするが存在しない; そのため、に渡す値は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f59eb-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="f59eb-120">指定することも<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>(`public` c# で`Public`Visual Basic で)。 ただし、を指定する<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>ために頻繁に行われます<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>が既に既定の動作。</span><span class="sxs-lookup"><span data-stu-id="f59eb-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="f59eb-121">対応するユーザー コードでは、その他の値へのアクセス レベルの制限など`private`c# では関連しない`x:ClassModifier`、XAML では、入れ子になったクラスの参照はサポートされていないため、それによって、<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>修飾子のと同じ効果します。</span><span class="sxs-lookup"><span data-stu-id="f59eb-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="f59eb-122">セキュリティに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="f59eb-122">Security Notes</span></span>  
 <span data-ttu-id="f59eb-123">アクセス レベルで宣言されている`x:ClassModifier`は特定のフレームワークとその機能によって解釈される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f59eb-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="f59eb-124">WPF に読み込むし、型のインスタンスを作成する機能が含まれています、`x:ClassModifier`は`internal`pack URI 参照を使用して、WPF リソースからそのクラスが参照されている場合、します。</span><span class="sxs-lookup"><span data-stu-id="f59eb-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="f59eb-125">この場合、可能性のある他のフレームワークによって実装されるような結果、管理者はで排他的に依存しない`x:ClassModifier`使用可能なすべてのインスタンス化をブロックしようとします。</span><span class="sxs-lookup"><span data-stu-id="f59eb-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f59eb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f59eb-126">See also</span></span>

- [<span data-ttu-id="f59eb-127">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f59eb-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="f59eb-128">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="f59eb-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="f59eb-129">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="f59eb-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="f59eb-130">セキュリティ (WPF)</span><span class="sxs-lookup"><span data-stu-id="f59eb-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="f59eb-131">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="f59eb-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
