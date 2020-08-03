---
title: StaticResource のマークアップ拡張機能
description: 既に定義されているリソースへの参照を検索することによって、任意の XAML プロパティ属性の値を提供します。
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 77396c1867dcbe279d7ba158ed9e6f5f833f17b5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164674"
---
# <a name="staticresource-markup-extension"></a><span data-ttu-id="1cd56-103">StaticResource のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="1cd56-103">StaticResource Markup Extension</span></span>
<span data-ttu-id="1cd56-104">既に定義されているリソースへの参照を検索することによって、任意の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロパティ属性の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="1cd56-104">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="1cd56-105">そのリソースに対する検索動作は、読み込み時の検索に似ています。これにより、現在の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページおよび他のアプリケーション ソースのマークアップから以前に読み込まれたリソースが検索され、実行時オブジェクトのプロパティ値としてそのリソース値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1cd56-105">Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page as well as other application sources, and will generate that resource value as the property value in the run-time objects.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="1cd56-106">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="1cd56-106">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{StaticResource key}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="1cd56-107">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="1cd56-107">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" ... />  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="1cd56-108">XAML 値</span><span class="sxs-lookup"><span data-stu-id="1cd56-108">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="1cd56-109">要求されたリソースのキー。</span><span class="sxs-lookup"><span data-stu-id="1cd56-109">The key for the requested resource.</span></span> <span data-ttu-id="1cd56-110">このキーは、リソースがマークアップで作成された場合は [x:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)によって最初に割り当てられ、リソースがコードで作成された場合は <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> を呼び出すときに `key` パラメーターとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="1cd56-110">This key was initially assigned by the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cd56-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1cd56-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1cd56-112">`StaticResource` では、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイル内で構文的にさらに定義されているリソースへの前方参照を試行することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cd56-112">A `StaticResource` must not attempt to make a forward reference to a resource that is defined lexically further within the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="1cd56-113">それを試みることはサポートされておらず、このような参照が失敗しない場合でも、前方参照を試行すると、<xref:System.Windows.ResourceDictionary> を表す内部ハッシュ テーブルが検索されるときに、読み込み時間のパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="1cd56-113">Attempting to do so is not supported, and even if such a reference does not fail, attempting the forward reference will incur a load time performance penalty when the internal hash tables representing a <xref:System.Windows.ResourceDictionary> are searched.</span></span> <span data-ttu-id="1cd56-114">最良の結果を得るには、前方参照を回避できるように、リソース ディクショナリの構成を調整します。</span><span class="sxs-lookup"><span data-stu-id="1cd56-114">For best results, adjust the composition of your resource dictionaries such that forward references can be avoided.</span></span> <span data-ttu-id="1cd56-115">前方参照を回避できない場合は、代わりに [DynamicResource マークアップ拡張](dynamicresource-markup-extension.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1cd56-115">If you cannot avoid a forward reference, use [DynamicResource Markup Extension](dynamicresource-markup-extension.md) instead.</span></span>  
  
 <span data-ttu-id="1cd56-116">指定する <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> は、ページ、アプリケーション、使用可能なコントロール テーマと外部リソース、またはシステム リソースのいずれかのレベルで [x:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)によって示される既存のリソースに対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd56-116">The specified <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> should correspond to an existing resource, identified with an [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) at some level in your page, application, the available control themes and external resources, or system resources.</span></span> <span data-ttu-id="1cd56-117">リソースの検索は、その順序で行われます。</span><span class="sxs-lookup"><span data-stu-id="1cd56-117">The resource lookup occurs in that order.</span></span> <span data-ttu-id="1cd56-118">静的リソースと動的リソースのリソース検索動作の詳細については、[XAML のリソース](../../../desktop-wpf/fundamentals/xaml-resources-define.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd56-118">For more information about resource lookup behavior for static and dynamic resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
 <span data-ttu-id="1cd56-119">リソース キーは、[XamlName 文法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)で定義されている任意の文字列の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1cd56-119">A resource key can be any string defined in the [XamlName Grammar](../../../desktop-wpf/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="1cd56-120">リソース キーは、<xref:System.Type> などの他のオブジェクト型の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1cd56-120">A resource key can also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="1cd56-121"><xref:System.Type> キーは、暗黙的なスタイル キーにより、テーマによってコントロールのスタイルを設定する方法の基礎になります。</span><span class="sxs-lookup"><span data-stu-id="1cd56-121">A <xref:System.Type> key is fundamental to how controls can be styled by themes, through an implicit style key.</span></span> <span data-ttu-id="1cd56-122">詳しくは、「[コントロールの作成の概要](../controls/control-authoring-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd56-122">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="1cd56-123">リソースを参照する別の宣言的な方法は、[DynamicResource マークアップ拡張](dynamicresource-markup-extension.md)として機能します。</span><span class="sxs-lookup"><span data-stu-id="1cd56-123">The alternative declarative means of referencing a resource is as a [DynamicResource Markup Extension](dynamicresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="1cd56-124">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="1cd56-124">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="1cd56-125">`StaticResource` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 拡張クラスの <xref:System.Windows.StaticResourceExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1cd56-125">The string token provided after the `StaticResource` identifier string is assigned as the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.StaticResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="1cd56-126">`StaticResource` は、オブジェクト要素構文で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cd56-126">`StaticResource` can be used in object element syntax.</span></span> <span data-ttu-id="1cd56-127">この場合は、<xref:System.Windows.StaticResourceExtension.ResourceKey%2A> プロパティの値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd56-127">In this case, specifying the value of the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="1cd56-128">`StaticResource` は、<xref:System.Windows.StaticResourceExtension.ResourceKey%2A> プロパティをプロパティおよび値のペアとして指定する詳細出力属性使用でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cd56-128">`StaticResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{StaticResource ResourceKey=key}" ... />  
```  
  
 <span data-ttu-id="1cd56-129">詳細出力の使用は、複数の設定可能プロパティを持つ拡張機能や、一部のプロパティがオプションである場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1cd56-129">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="1cd56-130">`StaticResource` には、必須の設定可能プロパティが 1 つしか存在しないため、このような詳細出力の使用は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="1cd56-130">Because `StaticResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="1cd56-131">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサの実装では、このマークアップ拡張の処理は <xref:System.Windows.StaticResourceExtension> クラスによって定義されています。</span><span class="sxs-lookup"><span data-stu-id="1cd56-131">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.StaticResourceExtension> class.</span></span>  
  
 <span data-ttu-id="1cd56-132">`StaticResource` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="1cd56-132">`StaticResource` is a markup extension.</span></span> <span data-ttu-id="1cd56-133">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="1cd56-133">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="1cd56-134">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のすべてのマークアップ拡張では、それぞれの属性構文で { と } の 2 つの記号が使用されます。これは規約であり、これに従って [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサでは、マークアップ拡張で属性を処理する必要があることが認識されます。</span><span class="sxs-lookup"><span data-stu-id="1cd56-134">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="1cd56-135">詳細については、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd56-135">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd56-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cd56-136">See also</span></span>

- [<span data-ttu-id="1cd56-137">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="1cd56-137">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="1cd56-138">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="1cd56-138">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="1cd56-139">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="1cd56-139">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="1cd56-140">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="1cd56-140">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="1cd56-141">リソースとコード</span><span class="sxs-lookup"><span data-stu-id="1cd56-141">Resources and Code</span></span>](resources-and-code.md)
