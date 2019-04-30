---
title: TemplateBinding のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: c004560a0b7ab367fbf4fbb48b0e8d8b63f3d8f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053042"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="3f9c6-102">TemplateBinding のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="3f9c6-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="3f9c6-103">コントロール テンプレート内のプロパティの値を、template 宣言されたコントロールの別のプロパティの値にリンクします。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3f9c6-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="3f9c6-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="3f9c6-105">XAML 属性の使用方法 (テンプレートまたはスタイルの Setter プロパティの場合)</span><span class="sxs-lookup"><span data-stu-id="3f9c6-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3f9c6-106">XAML 値</span><span class="sxs-lookup"><span data-stu-id="3f9c6-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="3f9c6-107">Setter 構文で設定されるプロパティの <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="3f9c6-108">template 宣言された型に存在する、<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> によって指定された別の依存関係プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="3f9c6-109">または</span><span class="sxs-lookup"><span data-stu-id="3f9c6-109">- or -</span></span><br /><br /> <span data-ttu-id="3f9c6-110">template 宣言された対象の型とは異なる型で定義されている "ドットダウン" プロパティ名。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="3f9c6-111">これは、実際には <xref:System.Windows.PropertyPath> です。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="3f9c6-112">参照してください[PropertyPath の XAML 構文](propertypath-xaml-syntax.md)します。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-112">See [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f9c6-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3f9c6-113">Remarks</span></span>  
 <span data-ttu-id="3f9c6-114">A`TemplateBinding`の最適化された形には、[バインド](binding-markup-extension.md)テンプレート シナリオの場合に似ています、`Binding`を使用して構築`{Binding RelativeSource={RelativeSource TemplatedParent}}`します。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-114">A `TemplateBinding` is an optimized form of a [Binding](binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="3f9c6-115">関連するプロパティが既定で双方向のバインディングの場合でも、`TemplateBinding` は常に一方向のバインディングです。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="3f9c6-116">関連する両方のプロパティは、依存関係プロパティである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="3f9c6-117">実現するためにテンプレート化された親に双方向のバインドを使用して、次のバインド ステートメント代わりに`{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`します。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span> 
  
 <span data-ttu-id="3f9c6-118">[RelativeSource](relativesource-markupextension.md)と共に、またはの代わりにでも使用されている別のマークアップ拡張機能は、`TemplateBinding`テンプレート内で相対プロパティ バインディングを実行するためにします。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-118">[RelativeSource](relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="3f9c6-119">コントロール テンプレートを説明する概念としてはここでは説明がありません。詳細については、次を参照してください。[コントロールのスタイルとテンプレート](../controls/control-styles-and-templates.md)します。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="3f9c6-120">属性構文は、このマークアップ拡張機能で使用される最も一般的な構文です。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="3f9c6-121">`TemplateBinding` 識別子文字列の後に設定される文字列トークンは、基になる <xref:System.Windows.TemplateBindingExtension.Property%2A> 拡張クラスの <xref:System.Windows.TemplateBindingExtension> 値として割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="3f9c6-122">オブジェクト要素構文を使用することもできますが、現実的な用途がないためここでは触れません。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="3f9c6-123">`TemplateBinding` は、評価された式を使用して setter 内で値を埋め込むために使用され、`TemplateBinding` を使用する場合、TemplateBinding が `<Setter.Property>` プロパティ要素構文を埋め込むためのオブジェクト要素構文は、必要以上に詳細です。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="3f9c6-124">`TemplateBinding` は、<xref:System.Windows.TemplateBindingExtension.Property%2A> プロパティをプロパティおよび値のペアとして指定する詳細出力属性使用でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="3f9c6-125">詳細出力の使用は、複数の設定可能プロパティを持つ拡張機能や、一部のプロパティがオプションである場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="3f9c6-126">`TemplateBinding` には、必須の設定可能プロパティが 1 つしか存在しないため、このような詳細出力の使用は一般的ではありません。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="3f9c6-127">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML プロセッサ実装では、このマークアップ拡張機能の処理がによって定義されている、<xref:System.Windows.TemplateBindingExtension>クラス。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="3f9c6-128">`TemplateBinding` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="3f9c6-129">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="3f9c6-130">XAML の使用中のすべてのマークアップ拡張機能、`{`と`}`マークアップ拡張機能が、属性を処理する必要がありますを XAML プロセッサが認識する規則は、それぞれの属性構文内の文字。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="3f9c6-131">詳細については、次を参照してください。[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)します。</span><span class="sxs-lookup"><span data-stu-id="3f9c6-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f9c6-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f9c6-132">See also</span></span>

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3f9c6-133">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="3f9c6-133">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="3f9c6-134">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="3f9c6-134">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="3f9c6-135">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="3f9c6-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="3f9c6-136">RelativeSource のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="3f9c6-136">RelativeSource MarkupExtension</span></span>](relativesource-markupextension.md)
- [<span data-ttu-id="3f9c6-137">バインドのマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="3f9c6-137">Binding Markup Extension</span></span>](binding-markup-extension.md)
