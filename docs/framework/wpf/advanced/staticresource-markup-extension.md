---
title: StaticResource のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 7392be182aedeeebe6b7092f9868c1fabfaafcb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963456"
---
# <a name="staticresource-markup-extension"></a><span data-ttu-id="958fb-102">StaticResource のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="958fb-102">StaticResource Markup Extension</span></span>
<span data-ttu-id="958fb-103">既に定義され[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ているリソースへの参照を検索することによって、任意のプロパティ属性の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="958fb-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="958fb-104">そのリソースの参照動作は、読み込み時の参照に似ています。これにより、現在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]のページのマークアップから以前に読み込まれたリソースと、その他のアプリケーションソースが検索され、そのリソース値が次のように生成されます。ランタイムオブジェクトのプロパティ値。</span><span class="sxs-lookup"><span data-stu-id="958fb-104">Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page as well as other application sources, and will generate that resource value as the property value in the run-time objects.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="958fb-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="958fb-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="958fb-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="958fb-106">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="958fb-107">XAML 値</span><span class="sxs-lookup"><span data-stu-id="958fb-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="958fb-108">要求されたリソースのキー。</span><span class="sxs-lookup"><span data-stu-id="958fb-108">The key for the requested resource.</span></span> <span data-ttu-id="958fb-109">このキーは、リソースがマークアップで作成された場合、またはコードでリソースが作成`key`された<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>場合にを呼び出すときにパラメーターとして指定された場合、最初に[x:Key ディレクティブ](../../xaml-services/x-key-directive.md)によって割り当てられました。</span><span class="sxs-lookup"><span data-stu-id="958fb-109">This key was initially assigned by the [x:Key Directive](../../xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="958fb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="958fb-110">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="958fb-111">は`StaticResource` 、 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ファイル内でさらに構文的に定義されているリソースへの前方参照を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="958fb-111">A `StaticResource` must not attempt to make a forward reference to a resource that is defined lexically further within the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="958fb-112">これを行うことはサポートされていません。このような参照が失敗しない場合でも、前方参照を試行すると、を<xref:System.Windows.ResourceDictionary>表す内部ハッシュテーブルが検索されるときに、読み込み時間のパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="958fb-112">Attempting to do so is not supported, and even if such a reference does not fail, attempting the forward reference will incur a load time performance penalty when the internal hash tables representing a <xref:System.Windows.ResourceDictionary> are searched.</span></span> <span data-ttu-id="958fb-113">最良の結果を得るには、前方参照を回避できるように、リソースディクショナリの構成を調整します。</span><span class="sxs-lookup"><span data-stu-id="958fb-113">For best results, adjust the composition of your resource dictionaries such that forward references can be avoided.</span></span> <span data-ttu-id="958fb-114">前方参照を回避できない場合は、代わりに[Dynamicresource マークアップ拡張機能](dynamicresource-markup-extension.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="958fb-114">If you cannot avoid a forward reference, use [DynamicResource Markup Extension](dynamicresource-markup-extension.md) instead.</span></span>  
  
 <span data-ttu-id="958fb-115">指定する<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>は、既存のリソースに対応する必要があります。これは、ページ、アプリケーション、使用可能なコントロールテーマと外部リソース、またはシステムリソースについて、 [x:Key ディレクティブ](../../xaml-services/x-key-directive.md)で識別されます。</span><span class="sxs-lookup"><span data-stu-id="958fb-115">The specified <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> should correspond to an existing resource, identified with an [x:Key Directive](../../xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources.</span></span> <span data-ttu-id="958fb-116">リソースルックアップは、この順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="958fb-116">The resource lookup occurs in that order.</span></span> <span data-ttu-id="958fb-117">静的リソースと動的リソースのリソース検索動作の詳細については、「 [XAML リソース](xaml-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958fb-117">For more information about resource lookup behavior for static and dynamic resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
 <span data-ttu-id="958fb-118">リソースキーは、 [XamlName 文法](../../xaml-services/xamlname-grammar.md)で定義されている任意の文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="958fb-118">A resource key can be any string defined in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="958fb-119">リソースキーは、など、他の種類<xref:System.Type>のオブジェクトにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="958fb-119">A resource key can also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="958fb-120"><xref:System.Type>キーは、暗黙的なスタイルキーを使用して、テーマによってコントロールをスタイル設定する方法の基本となります。</span><span class="sxs-lookup"><span data-stu-id="958fb-120">A <xref:System.Type> key is fundamental to how controls can be styled by themes, through an implicit style key.</span></span> <span data-ttu-id="958fb-121">詳しくは、「[コントロールの作成の概要](../controls/control-authoring-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958fb-121">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="958fb-122">リソースを参照する別の宣言的な方法は、 [Dynamicresource マークアップ拡張機能](dynamicresource-markup-extension.md)です。</span><span class="sxs-lookup"><span data-stu-id="958fb-122">The alternative declarative means of referencing a resource is as a [DynamicResource Markup Extension](dynamicresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="958fb-123">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="958fb-123">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="958fb-124">`StaticResource` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 拡張クラスの <xref:System.Windows.StaticResourceExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="958fb-124">The string token provided after the `StaticResource` identifier string is assigned as the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.StaticResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="958fb-125">`StaticResource`オブジェクト要素構文で使用できます。</span><span class="sxs-lookup"><span data-stu-id="958fb-125">`StaticResource` can be used in object element syntax.</span></span> <span data-ttu-id="958fb-126">この場合、 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>プロパティの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="958fb-126">In this case, specifying the value of the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="958fb-127">`StaticResource` は、<xref:System.Windows.StaticResourceExtension.ResourceKey%2A> プロパティをプロパティおよび値のペアとして指定する詳細出力属性使用でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="958fb-127">`StaticResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="958fb-128">詳細出力の使用は、複数の設定可能プロパティを持つ拡張機能や、一部のプロパティがオプションである場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="958fb-128">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="958fb-129">`StaticResource` には、必須の設定可能プロパティが 1 つしか存在しないため、このような詳細出力の使用は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="958fb-129">Because `StaticResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="958fb-130">プロセッサ実装では、このマークアップ<xref:System.Windows.StaticResourceExtension>拡張機能の処理はクラスによって定義されます。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="958fb-130">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.StaticResourceExtension> class.</span></span>  
  
 <span data-ttu-id="958fb-131">`StaticResource` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="958fb-131">`StaticResource` is a markup extension.</span></span> <span data-ttu-id="958fb-132">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="958fb-132">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="958fb-133">のすべての[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ拡張機能は、属性構文で {および} 文字を使用します。これ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]は、マークアップ拡張機能が属性を処理する必要があることをプロセッサが認識する規則です。</span><span class="sxs-lookup"><span data-stu-id="958fb-133">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="958fb-134">詳細については、「[マークアップ拡張機能」および「WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958fb-134">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958fb-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="958fb-135">See also</span></span>

- [<span data-ttu-id="958fb-136">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="958fb-136">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="958fb-137">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="958fb-137">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="958fb-138">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="958fb-138">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="958fb-139">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="958fb-139">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="958fb-140">リソースとコード</span><span class="sxs-lookup"><span data-stu-id="958fb-140">Resources and Code</span></span>](resources-and-code.md)
