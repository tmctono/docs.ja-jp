---
title: x:Type マークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: bf62987c61c1d4f6aefce515f79e997b41272b56
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622961"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="3436e-102">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="3436e-102">x:Type Markup Extension</span></span>
<span data-ttu-id="3436e-103">CLR の提供<xref:System.Type>指定の XAML 型の基になる型であるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3436e-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3436e-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="3436e-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="3436e-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="3436e-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3436e-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="3436e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="3436e-107">任意。</span><span class="sxs-lookup"><span data-stu-id="3436e-107">Optional.</span></span> <span data-ttu-id="3436e-108">既定以外の XAML 名前空間にマップされるプレフィックス。</span><span class="sxs-lookup"><span data-stu-id="3436e-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="3436e-109">プレフィックスを指定することは頻繁に必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3436e-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="3436e-110">「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3436e-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="3436e-111">必須。</span><span class="sxs-lookup"><span data-stu-id="3436e-111">Required.</span></span> <span data-ttu-id="3436e-112">現在既定の XAML 名前空間; に解決可能な型名指定した場合、マップのプレフィックスまたは`prefix`を指定します。</span><span class="sxs-lookup"><span data-stu-id="3436e-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3436e-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3436e-113">Remarks</span></span>  
 <span data-ttu-id="3436e-114">`x:Type`マークアップ拡張機能は同様の機能を`typeof()`演算子 (C#) または`GetType`Microsoft Visual Basic での演算子。</span><span class="sxs-lookup"><span data-stu-id="3436e-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>  
  
 <span data-ttu-id="3436e-115">`x:Type`マークアップ拡張機能は、型を使用するプロパティの文字列から変換動作を提供<xref:System.Type>します。</span><span class="sxs-lookup"><span data-stu-id="3436e-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="3436e-116">入力は、XAML の型です。</span><span class="sxs-lookup"><span data-stu-id="3436e-116">The input is a XAML type.</span></span> <span data-ttu-id="3436e-117">XAML の入力と出力の CLR 間のリレーションシップ<xref:System.Type>出力される<xref:System.Type>は、<xref:System.Xaml.XamlType.UnderlyingType%2A>入力の<xref:System.Xaml.XamlType>、ために必要なの検索後<xref:System.Xaml.XamlType>XAML スキーマ コンテキストと、に基づいて<xref:System.Windows.Markup.IXamlTypeResolver>サービス コンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="3436e-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="3436e-118">このマークアップ拡張機能の処理がによって定義されている .NET Framework XAML サービスを<xref:System.Windows.Markup.TypeExtension>クラス。</span><span class="sxs-lookup"><span data-stu-id="3436e-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="3436e-119">特定のフレームワークの実装でいくつかのプロパティを受け取る<xref:System.Type>ように、値は、型の名前を直接受け入れることができます (型の文字列値`Name`)。</span><span class="sxs-lookup"><span data-stu-id="3436e-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="3436e-120">ただし、この動作を実装するは複雑なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="3436e-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="3436e-121">例については、以下の「WPF の使用法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3436e-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="3436e-122">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="3436e-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="3436e-123">`x:Type` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 拡張クラスの <xref:System.Windows.Markup.TypeExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3436e-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="3436e-124">CLR 型に基づくは、.NET Framework XAML サービスの既定の XAML スキーマ コンテキストでこの属性の値は、いずれか、<xref:System.Reflection.MemberInfo.Name%2A>の目的の型を格納または<xref:System.Reflection.MemberInfo.Name%2A>前に既定以外の XAML 名前空間のプレフィックスマッピングします。</span><span class="sxs-lookup"><span data-stu-id="3436e-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="3436e-125">`x:Type`オブジェクト要素構文でマークアップ拡張機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3436e-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="3436e-126">この場合は、値を指定する、<xref:System.Windows.Markup.TypeExtension.TypeName%2A>拡張機能を適切に初期化するプロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="3436e-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="3436e-127">`x:Type`マークアップ拡張機能は、詳細属性としても使用できます。 ただしこのような使用は一般的なはありません。 `<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="3436e-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="3436e-128">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="3436e-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="3436e-129">既定の XAML Namespace と型マッピング</span><span class="sxs-lookup"><span data-stu-id="3436e-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="3436e-130">WPF プログラミングの既定の XAML 名前空間には、XAML の一般的なシナリオに必要な XAML 型の大部分が含まれています。そのため、XAML 型の値を参照するときに、多くの場合、プレフィックスを回避することができます。</span><span class="sxs-lookup"><span data-stu-id="3436e-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="3436e-131">カスタム アセンブリから、または既定の XAML 名前空間にマップされませんでした、CLR 名前空間からは WPF アセンブリ内に存在する型の型を参照している場合、プレフィックスをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3436e-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="3436e-132">プレフィックス、XAML 名前空間と CLR 名前空間のマッピングの詳細については、次を参照してください。 [XAML 名前空間および WPF XAML の Namespace マッピング](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="3436e-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="3436e-133">そのサポート Typename としての文字列のプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="3436e-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="3436e-134">WPF でサポートされる型の一部のプロパティの値を指定できるようにする手法<xref:System.Type>を必要とせず、`x:Type`マークアップ拡張機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="3436e-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="3436e-135">代わりに、型に名前を文字列として値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="3436e-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="3436e-136">この機能にはの例については<xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType>と<xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="3436e-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3436e-137">この動作のサポートは、型コンバーターまたはマークアップ拡張機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="3436e-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="3436e-138">代わりに、これは、遅延の動作を使用して実装を<xref:System.Windows.FrameworkElementFactory>します。</span><span class="sxs-lookup"><span data-stu-id="3436e-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="3436e-139">Silverlight には、同様の規則がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3436e-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="3436e-140">実際には、Silverlight はサポートされていない`{x:Type}`の XAML 言語のサポートでは受け付けられません`{x:Type}`WPF Silverlight XAML の移行をサポートするためのものでは、いくつかの状況の外部で使用します。</span><span class="sxs-lookup"><span data-stu-id="3436e-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="3436e-141">そのため、typename に文字列としての動作がすべての Silverlight ネイティブ プロパティの評価に組み込まれている、<xref:System.Type>値です。</span><span class="sxs-lookup"><span data-stu-id="3436e-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="3436e-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="3436e-142">XAML 2009</span></span>  
 <span data-ttu-id="3436e-143">XAML 2009 のジェネリック型し、の機能の動作を変更します。 その他のサポートを提供します`x:TypeArguments`と`x:Type`このサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="3436e-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
- <span data-ttu-id="3436e-144">`x:TypeArguments` ルート以外の要素に関連付けられたオブジェクト要素の汎用オブジェクトのインスタンス化ができます。</span><span class="sxs-lookup"><span data-stu-id="3436e-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="3436e-145">詳細については、の「XAML 2009」セクションを参照してください。 [X:typearguments ディレクティブ](x-typearguments-directive.md)します。</span><span class="sxs-lookup"><span data-stu-id="3436e-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](x-typearguments-directive.md).</span></span>  
  
- <span data-ttu-id="3436e-146">XAML 2009 は、マークアップでジェネリック型の制約を指定するための構文をサポートします。</span><span class="sxs-lookup"><span data-stu-id="3436e-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="3436e-147">これで使用できる`x:TypeArguments`により、 `x:Type`、または組み合わせでは、2 つの機能です。</span><span class="sxs-lookup"><span data-stu-id="3436e-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
- <span data-ttu-id="3436e-148">負荷は、型を使用する特定のフレームワーク プロパティに対して暗黙的な型変換の動作にこの機能を追加するもの XAML 2009 を処理するときに、WPF XAML 実装<xref:System.Type>します。</span><span class="sxs-lookup"><span data-stu-id="3436e-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="3436e-149">WPF では、loose XAML (XAML マークアップ コンパイルされていない) については、XAML 2009 の機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3436e-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="3436e-150">WPF 向けにマークアップ コンパイルされた XAML、および XAML の BAML 形式は、現在、XAML 2009 のキーワードと機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3436e-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3436e-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="3436e-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="3436e-152">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="3436e-152">Styling and Templating</span></span>](../wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="3436e-153">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="3436e-153">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="3436e-154">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="3436e-154">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
