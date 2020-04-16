---
title: x:Array のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433284"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="cf572-102">x:Array のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="cf572-102">x:Array Markup Extension</span></span>

<span data-ttu-id="cf572-103">マークアップ拡張機能を使用して、XAML のオブジェクトの配列に対する一般的なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf572-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="cf572-104">これは [MS-XAML] の`x:ArrayExtension`XAML 型に対応します。</span><span class="sxs-lookup"><span data-stu-id="cf572-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="cf572-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="cf572-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="cf572-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="cf572-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="cf572-107">含`x:Array`める型の名前。</span><span class="sxs-lookup"><span data-stu-id="cf572-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="cf572-108">`typeName`XAML 型定義を含む XAML 名前空間のプレフィックスが付くこともあります (多くの場合、</span><span class="sxs-lookup"><span data-stu-id="cf572-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="cf572-109">組み込み`ArrayExtension.Items`プロパティに割り当てられている項目のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="cf572-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="cf572-110">通常、これらの項目は、開始タグと終了タグに含まれる`x:Array`1 つ以上のオブジェクト要素として指定されます。</span><span class="sxs-lookup"><span data-stu-id="cf572-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="cf572-111">ここで指定したオブジェクトは、 で`typeName`指定された XAML 型に割り当て可能であると想定されます。</span><span class="sxs-lookup"><span data-stu-id="cf572-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cf572-112">解説</span><span class="sxs-lookup"><span data-stu-id="cf572-112">Remarks</span></span>

<span data-ttu-id="cf572-113">`Type`は、すべての`x:Array`オブジェクト要素に必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="cf572-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="cf572-114">`Type`パラメーター値は`x:Type`マークアップ拡張機能を使用する必要はありません。型の短い名前は XAML 型で、文字列として指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf572-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="cf572-115">NET XAML サービスの実装では、入力 XAML 型と作成された配列<xref:System.Type>の出力 CLR の関係は、マークアップ拡張機能のサービス コンテキストによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="cf572-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="cf572-116">出力<xref:System.Type>は、XAML<xref:System.Xaml.XamlType.UnderlyingType%2A>スキーマ コンテキストとコンテキストが提供するサービスに<xref:System.Xaml.XamlType>基づいて必要な検索を行<xref:System.Windows.Markup.IXamlTypeResolver>った後の入力 XAML 型です。</span><span class="sxs-lookup"><span data-stu-id="cf572-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="cf572-117">処理されると、配列の内容は組み込`ArrayExtension.Items`みプロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cf572-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="cf572-118">実装では<xref:System.Windows.Markup.ArrayExtension>、これは<xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>で表されます。</span><span class="sxs-lookup"><span data-stu-id="cf572-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="cf572-119">NET XAML サービスの実装では、このマークアップ拡張機能の処理は、クラスによって<xref:System.Windows.Markup.ArrayExtension>定義されます。</span><span class="sxs-lookup"><span data-stu-id="cf572-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="cf572-120"><xref:System.Windows.Markup.ArrayExtension>はシールされておらず、カスタム配列型のマークアップ拡張機能の実装の基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf572-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="cf572-121">`x:Array`XAML の一般的な言語拡張機能を目的としています。</span><span class="sxs-lookup"><span data-stu-id="cf572-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="cf572-122">ただし`x:Array`、構造化されたプロパティ コンテンツとして XAML でサポートされているコレクションを受け取る特定のプロパティの XAML 値を指定する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf572-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="cf572-123">たとえば、<xref:System.Collections.IEnumerable>`x:Array`プロパティの内容を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf572-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="cf572-124">`x:Array` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="cf572-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="cf572-125">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="cf572-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="cf572-126">`x:Array`は、代替の属性値の処理を提供する代わりに、その内部テキスト`x:Array`コンテンツの代替処理を提供するため、そのルールの部分的な例外です。</span><span class="sxs-lookup"><span data-stu-id="cf572-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="cf572-127">この動作により、既存のコンテンツ モデルでサポートされていない型を配列にグループ化し、名前付き配列にアクセスして分離コード内で参照できます。メソッドを呼<xref:System.Array>び出して、個々の配列項目を取得できます。</span><span class="sxs-lookup"><span data-stu-id="cf572-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="cf572-128">XAML のすべてのマークアップ拡張機能では、中かっこ{,}`)`(属性構文で、XAML プロセッサがマークアップ拡張機能が属性値を処理する必要があることを認識する規則) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf572-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="cf572-129">マークアップ拡張機能全般の詳細については、「 XAML の[型コンバーターとマークアップ拡張機能](type-converters-and-markup-extensions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf572-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="cf572-130">XAML 2009`x:Array`では、マークアップ拡張機能ではなく言語プリミティブとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="cf572-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="cf572-131">詳細については、「[共通言語 XAML 言語プリミティブの組み込み型](types-for-primitives.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf572-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="cf572-132">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="cf572-132">WPF Usage Notes</span></span>

<span data-ttu-id="cf572-133">通常、値を設定するオブジェクト要素`x:Array`は[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]XAML 名前空間に存在する要素ではなく、既定以外の XAML 名前空間へのプレフィックス マッピングを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cf572-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="cf572-134">たとえば、次の例は`sys`、2 つの文字列の単純な配列で、プレフィックス`x`(および) が配列のレベルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="cf572-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="cf572-135">配列要素として使用されるカスタム型の場合、クラスは XAML でオブジェクト要素としてインスタンス化するための要件もサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf572-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="cf572-136">詳細については、「 [WPF の XAML とカスタム クラス](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf572-136">For more information, see [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf572-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf572-137">See also</span></span>

- [<span data-ttu-id="cf572-138">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="cf572-138">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="cf572-139">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="cf572-139">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
