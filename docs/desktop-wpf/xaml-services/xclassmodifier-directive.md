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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433272"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="eb802-102">x:ClassModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="eb802-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="eb802-103">XAML コンパイル動作を変更`x:Class`します。</span><span class="sxs-lookup"><span data-stu-id="eb802-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="eb802-104">具体的には、アクセス レベル`class`(既定)`Public`を持つ部分を作成する`x:Class`代わりに、提供`NotPublic`されるアクセス レベルを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="eb802-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="eb802-105">この動作は、生成されたアセンブリ内のクラスのアクセス レベルに影響します。</span><span class="sxs-lookup"><span data-stu-id="eb802-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="eb802-106">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="eb802-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="eb802-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="eb802-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="eb802-108">*公開されていない*</span><span class="sxs-lookup"><span data-stu-id="eb802-108">*NotPublic*</span></span>|<span data-ttu-id="eb802-109">指定する文字列と<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>指定する文字列は、使用する分離コード プログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="eb802-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="eb802-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb802-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="eb802-111">依存関係</span><span class="sxs-lookup"><span data-stu-id="eb802-111">Dependencies</span></span>

<span data-ttu-id="eb802-112">[x:Class](xclass-directive.md)も同じ要素に指定する必要があり、その要素はページのルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb802-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="eb802-113">詳細については、 [ \[MS-XAML\]セクション 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb802-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="eb802-114">解説</span><span class="sxs-lookup"><span data-stu-id="eb802-114">Remarks</span></span>

<span data-ttu-id="eb802-115">.NET `x:ClassModifier` XAML サービスの使用法の値は、プログラミング言語によって異なります。</span><span class="sxs-lookup"><span data-stu-id="eb802-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="eb802-116">使用する文字列は、各言語が実装<xref:System.CodeDom.Compiler.CodeDomProvider>する方法と、その言語が返す型コンバーターによって、 および<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>の意味を定義するかどうか、およびその言語で大文字と小文字が区別されるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="eb802-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="eb802-117">C# の場合、指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>に渡す文字列`internal`は です。</span><span class="sxs-lookup"><span data-stu-id="eb802-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="eb802-118">NET の場合、指定<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>に渡す文字列は`Friend`です。</span><span class="sxs-lookup"><span data-stu-id="eb802-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="eb802-119">C++/CLI の場合、XAML のコンパイルをサポートするターゲットは存在しません。したがって、渡す値は指定されません。</span><span class="sxs-lookup"><span data-stu-id="eb802-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="eb802-120">(C#<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>では`public`Visual `Public` Basic で) 指定することもできます。ただし、指定は<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>既にデフォルトの動作<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>であるため、あまり行われません。</span><span class="sxs-lookup"><span data-stu-id="eb802-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="eb802-121">C# など`private`、同等のユーザー コード アクセス レベル制限を持つ他の値は`x:ClassModifier`、入れ子になったクラス参照は XAML ではサポートされていないため、<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>修飾子の効果は同じであるため、関連しません。</span><span class="sxs-lookup"><span data-stu-id="eb802-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="eb802-122">セキュリティに関するメモ</span><span class="sxs-lookup"><span data-stu-id="eb802-122">Security Notes</span></span>

<span data-ttu-id="eb802-123">で宣言されたアクセス レベル`x:ClassModifier`は、特定のフレームワークとその機能による解釈の対象となります。</span><span class="sxs-lookup"><span data-stu-id="eb802-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="eb802-124">WPF には、pack URI 参照を`x:ClassModifier`通`internal`じて WPF リソースからクラスが参照されている場合に、 の型を読み込んでインスタンス化する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb802-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="eb802-125">このケースの結果として、他のフレームワークによって実装されたような潜在的に他の人は、すべての可能な`x:ClassModifier`インスタンス化の試みをブロックするために排他的に依存しないでください。</span><span class="sxs-lookup"><span data-stu-id="eb802-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb802-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb802-126">See also</span></span>

- [<span data-ttu-id="eb802-127">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="eb802-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="eb802-128">WPF における分離コードと XAML</span><span class="sxs-lookup"><span data-stu-id="eb802-128">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="eb802-129">x:FieldModifier ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="eb802-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="eb802-130">セキュリティ (WPF)</span><span class="sxs-lookup"><span data-stu-id="eb802-130">Security (WPF)</span></span>](../../framework/wpf/security-wpf.md)
- [<span data-ttu-id="eb802-131">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="eb802-131">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
