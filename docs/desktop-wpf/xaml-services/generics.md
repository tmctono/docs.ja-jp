---
title: XAML のジェネリック
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432960"
---
# <a name="generics-in-xaml"></a><span data-ttu-id="95662-102">XAML のジェネリック</span><span class="sxs-lookup"><span data-stu-id="95662-102">Generics in XAML</span></span>

<span data-ttu-id="95662-103">に実装されている .NET XAML<xref:System.Xaml?displayProperty=fullName>サービスは、ジェネリック CLR 型の使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="95662-103">.NET XAML Services as implemented in <xref:System.Xaml?displayProperty=fullName> provides support for using generic CLR types.</span></span> <span data-ttu-id="95662-104">このサポートには、ジェネリックの制約を型引数として指定し、ジェネリック コレクションのケースに対して`Add`適切なメソッドを呼び出して制約を適用する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95662-104">This support includes specifying the constraints of generics as a type argument and enforcing the constraint by calling the appropriate `Add` method for generic collection cases.</span></span> <span data-ttu-id="95662-105">このトピックでは、XAML でジェネリック型を使用および参照する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95662-105">This topic describes aspects of using and referencing generic types in XAML.</span></span>

## <a name="xtypearguments"></a><span data-ttu-id="95662-106">x:型引数</span><span class="sxs-lookup"><span data-stu-id="95662-106">x:TypeArguments</span></span>

<span data-ttu-id="95662-107">`x:TypeArguments`は、XAML 言語で定義されたディレクティブです。</span><span class="sxs-lookup"><span data-stu-id="95662-107">`x:TypeArguments` is a directive defined by the XAML language.</span></span> <span data-ttu-id="95662-108">ジェネリック型によってサポートされる XAML 型のメンバーとして使用する場合、`x:TypeArguments`ジェネリックの制約型引数をバッキング コンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="95662-108">When it is used as a member of a XAML type that is backed by a generic type, `x:TypeArguments` passes constraining type arguments of the generic to the backing constructor.</span></span> <span data-ttu-id="95662-109">の .NET XAML サービスの`x:TypeArguments`使用に関連する参照構文については[、「x:TypeArguments ディレクティブ](xtypearguments-directive.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95662-109">For reference syntax that pertains to .NET XAML Services use of `x:TypeArguments`, which includes syntax examples, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

<span data-ttu-id="95662-110">文字列`x:TypeArguments`を受け取り、型コンバーターのバッキングがあるため、通常は XAML で属性として宣言されます。</span><span class="sxs-lookup"><span data-stu-id="95662-110">Because `x:TypeArguments` takes a string, and has type converter backing, it is typically declared in XAML usage as an attribute.</span></span>

<span data-ttu-id="95662-111">XAML ノード ストリームでは、 によって`x:TypeArguments`宣言された情報は、<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>ノード`StartObject`ストリーム内の位置から取得できます。</span><span class="sxs-lookup"><span data-stu-id="95662-111">In the XAML node stream, the information declared by `x:TypeArguments` can be obtained from <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> at a `StartObject` position in the node stream.</span></span> <span data-ttu-id="95662-112">の戻り値<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>は、値の<xref:System.Xaml.XamlType>リストです。</span><span class="sxs-lookup"><span data-stu-id="95662-112">The return value of <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> is a list of <xref:System.Xaml.XamlType> values.</span></span> <span data-ttu-id="95662-113">XAML 型がジェネリック型を表すかどうかを確認するには、 を<xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>呼び出します。</span><span class="sxs-lookup"><span data-stu-id="95662-113">Determination of whether a XAML type represents a generic type can be made by calling <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.</span></span>

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a><span data-ttu-id="95662-114">XAML のジェネリックの規則と構文の規則</span><span class="sxs-lookup"><span data-stu-id="95662-114">Rules and Syntax Conventions for Generics in XAML</span></span>

<span data-ttu-id="95662-115">XAML では、ジェネリック型は常に制約付きジェネリックとして表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="95662-115">In XAML, a generic type must always be represented as a constrained generic.</span></span> <span data-ttu-id="95662-116">制約のないジェネリックは、XAML 型システムまたは XAML ノード ストリームには存在しません。</span><span class="sxs-lookup"><span data-stu-id="95662-116">An unconstrained generic is never present in the XAML type system or a XAML node stream and cannot be represented in XAML markup.</span></span> <span data-ttu-id="95662-117">ジェネリックは、XAML 属性構文内で参照できます。 `x:TypeArguments` `x:Type`</span><span class="sxs-lookup"><span data-stu-id="95662-117">A generic can be referenced within XAML attribute syntax for cases where it is a nested type constraint of a generic being referenced by `x:TypeArguments`, or for cases where `x:Type` supplies a CLR type reference for a generic type.</span></span> <span data-ttu-id="95662-118">ジェネリックの参照は、.NET <xref:System.Xaml.Schema.XamlTypeTypeConverter> XAML サービスで定義されたクラスを通じてサポートされます。</span><span class="sxs-lookup"><span data-stu-id="95662-118">Referencing generics is supported through the <xref:System.Xaml.Schema.XamlTypeTypeConverter> class defined by .NET XAML Services.</span></span>

<span data-ttu-id="95662-119">ジェネリックの型と制約に山<xref:System.Xaml.Schema.XamlTypeTypeConverter>かっこを使用し、代わりに制約コンテナーのかっこを置き換える、一般的な MSIL /CLR 構文規則を変更することによって有効にされた XAML 属性構文フォーム。</span><span class="sxs-lookup"><span data-stu-id="95662-119">The XAML attribute syntax form enabled by <xref:System.Xaml.Schema.XamlTypeTypeConverter> alters the typical MSIL / CLR syntax convention that uses angle brackets for types and constraints of generics, and instead substitutes parentheses for the constraint container.</span></span> <span data-ttu-id="95662-120">例については、「 [x:TypeArguments ディレクティブ](xtypearguments-directive.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95662-120">For an example, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

## <a name="generics-and-xaml-2009-features"></a><span data-ttu-id="95662-121">ジェネリックと XAML 2009 の機能</span><span class="sxs-lookup"><span data-stu-id="95662-121">Generics and XAML 2009 Features</span></span>

<span data-ttu-id="95662-122">共通言語プリミティブの XAML 型を取得するために CLR 基本型をマッピングする代わりに XAML 2009 を使用する場合は、 の`x:TypeArguments`情報項目として XAML [2009 の組み込み型を](types-for-primitives.md)使用できます。</span><span class="sxs-lookup"><span data-stu-id="95662-122">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [XAML 2009 built-in types](types-for-primitives.md) as information items in `x:TypeArguments`.</span></span> <span data-ttu-id="95662-123">たとえば、次のように宣言できます (プレフィックス マッピングは表示されませんが`x`、XAML 2009 の XAML 言語 XAML 名前空間です)。</span><span class="sxs-lookup"><span data-stu-id="95662-123">For example, you could declare the following (prefix mappings not shown, but `x` is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a><span data-ttu-id="95662-124">WPF でのジェネリックサポート</span><span class="sxs-lookup"><span data-stu-id="95662-124">Generics Support in WPF</span></span>

<span data-ttu-id="95662-125">特に WPF を対象とする XAML 2006 の使用法では[、x:](xclass-directive.md) `x:TypeArguments`Class は と同じ要素に対しても指定する必要があり、その要素は XAML ドキュメントのルート要素である必要があります。</span><span class="sxs-lookup"><span data-stu-id="95662-125">For XAML 2006 usage when specifically targeting WPF, [x:Class](xclass-directive.md) must also be provided on the same element as `x:TypeArguments`, and that element must be the root element in a XAML document.</span></span> <span data-ttu-id="95662-126">ルート要素は、少なくとも 1 つの型引数を持つジェネリック型にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95662-126">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="95662-127">たとえば <xref:System.Windows.Navigation.PageFunction%601> です。</span><span class="sxs-lookup"><span data-stu-id="95662-127">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

<span data-ttu-id="95662-128">ジェネリックの使用法をサポートする場合の回避策としては、ジェネリック型を返すことができるカスタム マークアップ拡張機能の定義や、ジェネリック型から派生するが、独自のクラス定義でジェネリック制約をフラット化するラップ クラス定義の提供などがあります。</span><span class="sxs-lookup"><span data-stu-id="95662-128">Possible workarounds to support generic usages include defining a custom markup extension that can return generic types, or providing a wrapping class definition that derives from a generic type but flattens the generic constraint in its own class definition.</span></span>

<span data-ttu-id="95662-129">WPF では、XAML 2009 機能を`x:TypeArguments`と共に使用できますが、緩い XAML (マークアップ コンパイルされていない XAML) に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="95662-129">In WPF you can use XAML 2009 features together with `x:TypeArguments`, but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="95662-130">WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="95662-130">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="95662-131">.NET Framework 3.5 の Windows ワークフロー基盤のカスタム ワークフローでは、一般的な XAML の使用法はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="95662-131">Custom workflows in Windows Workflow Foundation for .NET Framework 3.5 do not support generic XAML usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="95662-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="95662-132">See also</span></span>

- [<span data-ttu-id="95662-133">x:TypeArguments ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="95662-133">x:TypeArguments Directive</span></span>](xtypearguments-directive.md)
- [<span data-ttu-id="95662-134">x:Class ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="95662-134">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="95662-135">共通の XAML 言語プリミティブの組み込み型</span><span class="sxs-lookup"><span data-stu-id="95662-135">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
