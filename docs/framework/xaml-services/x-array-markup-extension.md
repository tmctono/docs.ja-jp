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
ms.openlocfilehash: 4f4e26eb3e5ccaf66b2173c7fc9952375c5f2a58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62025406"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="13556-102">x:Array のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="13556-102">x:Array Markup Extension</span></span>
<span data-ttu-id="13556-103">マークアップ拡張機能を XAML でのオブジェクトの配列には、一般的なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="13556-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="13556-104">これに対応して、 `x:ArrayExtension` XAML [XAML MS] を入力します。</span><span class="sxs-lookup"><span data-stu-id="13556-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="13556-105">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="13556-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="13556-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="13556-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="13556-107">型の名前を`x:Array`が含まれます。</span><span class="sxs-lookup"><span data-stu-id="13556-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="13556-108">`typeName` 可能性があります (および多くの場合は)、XAML を含む名前空間を XAML のプレフィックスとして定義を入力します。</span><span class="sxs-lookup"><span data-stu-id="13556-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="13556-109">組み込みに割り当てられている項目コンテンツ`ArrayExtension.Items`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="13556-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="13556-110">通常、これらの項目が内に含まれる 1 つまたは複数のオブジェクト要素として指定、`x:Array`開始タグと終了します。</span><span class="sxs-lookup"><span data-stu-id="13556-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="13556-111">指定されたオブジェクトは、ここで指定された XAML 型に代入する予想される`typeName`します。</span><span class="sxs-lookup"><span data-stu-id="13556-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13556-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="13556-112">Remarks</span></span>  
 <span data-ttu-id="13556-113">`Type` すべての必須の属性は、 `x:Array` object 要素。</span><span class="sxs-lookup"><span data-stu-id="13556-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="13556-114">A`Type`パラメーターの値が使用する必要はありません、`x:Type`マークアップ拡張機能は、短い型の名前は、XAML 型を文字列として指定できます。</span><span class="sxs-lookup"><span data-stu-id="13556-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="13556-115">入力 XAML の型と CLR の出力の間の関係、.NET Framework XAML サービス実装で<xref:System.Type>作成された配列は、サービス コンテキストのマークアップ拡張機能によって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="13556-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="13556-116">出力<xref:System.Type>は、<xref:System.Xaml.XamlType.UnderlyingType%2A>ために必要な検索した後、入力の XAML 型の<xref:System.Xaml.XamlType>XAML スキーマ コンテキストに基づいて、<xref:System.Windows.Markup.IXamlTypeResolver>サービス コンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="13556-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="13556-117">配列の内容に割り当てられている、処理されるときに、`ArrayExtension.Items`組み込みプロパティ。</span><span class="sxs-lookup"><span data-stu-id="13556-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="13556-118"><xref:System.Windows.Markup.ArrayExtension>実装では、これは、表さ<xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="13556-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="13556-119">このマークアップ拡張機能の処理がによって定義されている、.NET Framework XAML サービス実装、<xref:System.Windows.Markup.ArrayExtension>クラス。</span><span class="sxs-lookup"><span data-stu-id="13556-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="13556-120"><xref:System.Windows.Markup.ArrayExtension> シールされていないと、カスタムの配列型のマークアップ拡張機能の実装の基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="13556-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 <span data-ttu-id="13556-121">`x:Array` 以上の目的の一般的な XAML の言語の機能拡張です。</span><span class="sxs-lookup"><span data-stu-id="13556-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="13556-122">`x:Array`にも、構造化されたプロパティのコンテンツとして XAML でサポートされているコレクションを取得する特定のプロパティの XAML 値を指定するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="13556-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="13556-123">内容を指定するなど、<xref:System.Collections.IEnumerable>プロパティを`x:Array`使用量。</span><span class="sxs-lookup"><span data-stu-id="13556-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 <span data-ttu-id="13556-124">`x:Array` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="13556-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="13556-125">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="13556-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="13556-126">`x:Array` そのルールの例外では部分的に代替の属性値の処理を提供することではなく`x:Array`その内部テキ スト コンテンツの代替の処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="13556-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="13556-127">この動作により、型を配列にグループ化とは名前付きの配列にアクセスして、後で、分離コードで参照されている既存のコンテンツ モデルでサポートされていない可能性があります。呼び出すことができます<xref:System.Array>個々 の配列の項目を取得するメソッド。</span><span class="sxs-lookup"><span data-stu-id="13556-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="13556-128">中かっこを使用して、XAML 内のすべてのマークアップ拡張機能 ({,} `)`それぞれの属性構文では、マークアップ拡張機能が属性値を処理する必要がありますを XAML プロセッサが認識される規約。</span><span class="sxs-lookup"><span data-stu-id="13556-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="13556-129">一般にマークアップ拡張機能の詳細については、次を参照してください。[型コンバーターと XAML のマークアップ拡張機能](type-converters-and-markup-extensions-for-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="13556-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="13556-130">XAML 2009 で`x:Array`マークアップ拡張機能ではなくプリミティブ言語として定義されます。</span><span class="sxs-lookup"><span data-stu-id="13556-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="13556-131">詳細については、次を参照してください。[共通の XAML 言語プリミティブの組み込み型](built-in-types-for-common-xaml-language-primitives.md)します。</span><span class="sxs-lookup"><span data-stu-id="13556-131">For more information, see [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="13556-132">WPF の使用上の注意</span><span class="sxs-lookup"><span data-stu-id="13556-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="13556-133">設定するオブジェクト要素では通常、`x:Array`に存在する要素のない、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML 名前空間に既定以外の XAML 名前空間プレフィックス マッピングが必要とします。</span><span class="sxs-lookup"><span data-stu-id="13556-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="13556-134">たとえば、2 つの文字列の単純な配列では、次の`sys`プレフィックス (とも`x`)、配列のレベルで定義します。</span><span class="sxs-lookup"><span data-stu-id="13556-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="13556-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="13556-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="13556-136">配列要素として使用されるカスタムの型のクラスはオブジェクト要素としての XAML でインスタンス化するための要件もサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13556-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="13556-137">詳細については、次を参照してください。 [XAML とカスタム クラスの WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)します。</span><span class="sxs-lookup"><span data-stu-id="13556-137">For more information, see [XAML and Custom Classes for WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13556-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="13556-138">See also</span></span>

- [<span data-ttu-id="13556-139">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="13556-139">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="13556-140">WPF から System.Xaml に移行した型</span><span class="sxs-lookup"><span data-stu-id="13556-140">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
