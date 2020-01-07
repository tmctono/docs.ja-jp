---
title: DynamicResource のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: f8b05f314be84e6104f1a9c7fe2edfdf826e51da
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559449"
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="3b22b-102">DynamicResource のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="3b22b-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="3b22b-103">定義されたリソースへの参照としてその値を延期することによって、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property 属性の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="3b22b-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="3b22b-104">このリソースの参照動作は、ランタイム参照に似ています。</span><span class="sxs-lookup"><span data-stu-id="3b22b-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3b22b-105">XAML 属性の使用</span><span class="sxs-lookup"><span data-stu-id="3b22b-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="3b22b-106">XAML プロパティ要素の使用</span><span class="sxs-lookup"><span data-stu-id="3b22b-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3b22b-107">XAML の値</span><span class="sxs-lookup"><span data-stu-id="3b22b-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="3b22b-108">要求されたリソースのキー。</span><span class="sxs-lookup"><span data-stu-id="3b22b-108">The key for the requested resource.</span></span> <span data-ttu-id="3b22b-109">このキーは、リソースがマークアップで作成された場合は[X:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)によって最初に割り当てられたか、またはリソースがコードで作成された場合に <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> を呼び出すときに `key` パラメーターとして指定されました。</span><span class="sxs-lookup"><span data-stu-id="3b22b-109">This key was initially assigned by the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b22b-110">コメント</span><span class="sxs-lookup"><span data-stu-id="3b22b-110">Remarks</span></span>  
 <span data-ttu-id="3b22b-111">`DynamicResource` は、初期コンパイル中に一時式を作成するため、オブジェクトを構築するために要求されたリソース値が実際に必要になるまで、リソースの参照を延期します。</span><span class="sxs-lookup"><span data-stu-id="3b22b-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="3b22b-112">これは、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページが読み込まれた後に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b22b-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="3b22b-113">リソース値は、現在のページスコープから始まるすべてのアクティブなリソースディクショナリに対するキー検索に基づいて検出され、コンパイルからのプレースホルダー式の代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3b22b-114">依存関係プロパティの優先順位に関しては、`DynamicResource` 式は動的リソース参照が適用される位置と同じです。</span><span class="sxs-lookup"><span data-stu-id="3b22b-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="3b22b-115">以前にローカル値として `DynamicResource` 式を持つプロパティのローカル値を設定した場合、`DynamicResource` は完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="3b22b-116">詳細については、「[依存関係プロパティ値の優先順位](dependency-property-value-precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b22b-116">For details, see [Dependency Property Value Precedence](dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="3b22b-117">特定のリソースアクセスシナリオは、 [StaticResource のマークアップ拡張機能](staticresource-markup-extension.md)ではなく `DynamicResource` に特に適しています。</span><span class="sxs-lookup"><span data-stu-id="3b22b-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span> <span data-ttu-id="3b22b-118">`DynamicResource`との相対的な利点とパフォーマンスへの影響については、「[XAML リソース](xaml-resources.md)」を参照して`StaticResource`ください。</span><span class="sxs-lookup"><span data-stu-id="3b22b-118">See [XAML Resources](xaml-resources.md) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="3b22b-119">指定された <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> は、ページ、アプリケーション、使用可能なコントロールのテーマと外部リソース、またはシステムリソースについて、 [X:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)によって決定された既存のリソースに対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b22b-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="3b22b-120">静的リソースと動的リソースのリソース検索の詳細については、「 [XAML リソース](xaml-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b22b-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
 <span data-ttu-id="3b22b-121">リソースキーは、 [XamlName 文法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)で定義されている任意の文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-121">A resource key may be any string defined in the [XamlName Grammar](../../../desktop-wpf/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="3b22b-122">リソースキーは、<xref:System.Type>など、他の種類のオブジェクトである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3b22b-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="3b22b-123"><xref:System.Type> キーは、テーマによってコントロールをスタイル設定する方法の基本となります。</span><span class="sxs-lookup"><span data-stu-id="3b22b-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="3b22b-124">詳細については、「[コントロールの作成の概要](../controls/control-authoring-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b22b-124">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="3b22b-125"><xref:System.Windows.FrameworkElement.FindResource%2A>などのリソース値を参照するための Api は、`DynamicResource`によって使用されるのと同じリソース参照ロジックに従います。</span><span class="sxs-lookup"><span data-stu-id="3b22b-125">APIs for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="3b22b-126">リソースを参照する別の宣言的な方法は、 [StaticResource マークアップ拡張機能](staticresource-markup-extension.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b22b-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="3b22b-127">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="3b22b-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="3b22b-128">`DynamicResource` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 拡張クラスの <xref:System.Windows.DynamicResourceExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="3b22b-129">`DynamicResource` は、オブジェクト要素構文で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-129">`DynamicResource` can be used in object element syntax.</span></span> <span data-ttu-id="3b22b-130">この場合は、<xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> プロパティの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b22b-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="3b22b-131">`DynamicResource` は、<xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> プロパティをプロパティおよび値のペアとして指定する詳細出力属性使用でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-131">`DynamicResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="3b22b-132">詳細出力の使用は、複数の設定可能プロパティを持つ拡張機能や、一部のプロパティがオプションである場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="3b22b-133">`DynamicResource` には、必須の設定可能プロパティが 1 つしか存在しないため、このような詳細出力の使用は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="3b22b-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="3b22b-134">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサの実装では、このマークアップ拡張機能の処理は <xref:System.Windows.DynamicResourceExtension> クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="3b22b-134">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 <span data-ttu-id="3b22b-135">`DynamicResource` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="3b22b-135">`DynamicResource` is a markup extension.</span></span> <span data-ttu-id="3b22b-136">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="3b22b-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="3b22b-137">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 内のすべてのマークアップ拡張機能は、属性構文で {および} 文字を使用します。これは、マークアップ拡張機能が属性を処理する必要があることを [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサが認識する規則です。</span><span class="sxs-lookup"><span data-stu-id="3b22b-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="3b22b-138">詳細については、「[マークアップ拡張機能」および「WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b22b-138">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b22b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b22b-139">See also</span></span>

- [<span data-ttu-id="3b22b-140">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="3b22b-140">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="3b22b-141">リソースとコード</span><span class="sxs-lookup"><span data-stu-id="3b22b-141">Resources and Code</span></span>](resources-and-code.md)
- [<span data-ttu-id="3b22b-142">x:Key ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3b22b-142">x:Key Directive</span></span>](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [<span data-ttu-id="3b22b-143">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="3b22b-143">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="3b22b-144">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="3b22b-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="3b22b-145">StaticResource のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="3b22b-145">StaticResource Markup Extension</span></span>](staticresource-markup-extension.md)
- [<span data-ttu-id="3b22b-146">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="3b22b-146">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
