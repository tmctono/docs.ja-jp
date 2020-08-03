---
title: RelativeSource のマークアップ拡張機能
description: Binding マークアップ拡張内か、または XAML で Binding の RelativeSource プロパティを設定するときに、RelativeSource バインディング ソースのプロパティを指定します。
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 2da702d23413651a85b45404e088f6708546cc25
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165939"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="36233-103">RelativeSource のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="36233-103">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="36233-104">[Binding マークアップ拡張](binding-markup-extension.md)内で使用されるか、または XAML で設定された <xref:System.Windows.Data.Binding> 要素の <xref:System.Windows.Data.Binding.RelativeSource%2A> プロパティの設定時に使用される、<xref:System.Windows.Data.RelativeSource> バインディング ソースのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="36233-104">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="36233-105">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="36233-105">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" ... />
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="36233-106">XAML 属性の使用方法 (バインディング拡張内で入れ子にした場合)</span><span class="sxs-lookup"><span data-stu-id="36233-106">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" ... />
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="36233-107">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="36233-107">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="36233-108">\- または -</span><span class="sxs-lookup"><span data-stu-id="36233-108">-or-</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a><span data-ttu-id="36233-109">XAML 値</span><span class="sxs-lookup"><span data-stu-id="36233-109">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="36233-110">次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="36233-110">One of the following:</span></span><br /><br /> <span data-ttu-id="36233-111">- 文字列トークン `Self`。<xref:System.Windows.Data.RelativeSource> に対応し、<xref:System.Windows.Data.RelativeSource.Mode%2A> プロパティは <xref:System.Windows.Data.RelativeSourceMode.Self> に設定されます。</span><span class="sxs-lookup"><span data-stu-id="36233-111">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="36233-112">- 文字列トークン `TemplatedParent`。<xref:System.Windows.Data.RelativeSource> に対応し、<xref:System.Windows.Data.RelativeSource.Mode%2A> プロパティは <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent> に設定されます。</span><span class="sxs-lookup"><span data-stu-id="36233-112">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="36233-113">- 文字列トークン `PreviousData`。<xref:System.Windows.Data.RelativeSource> に対応し、<xref:System.Windows.Data.RelativeSource.Mode%2A> プロパティは <xref:System.Windows.Data.RelativeSourceMode.PreviousData> に設定されます。</span><span class="sxs-lookup"><span data-stu-id="36233-113">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="36233-114">- `FindAncestor` モードについては後の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36233-114">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="36233-115">文字列トークン `FindAncestor`。</span><span class="sxs-lookup"><span data-stu-id="36233-115">The string token `FindAncestor`.</span></span> <span data-ttu-id="36233-116">このトークンを使用すると、`RelativeSource` によって先祖の型およびオプションで先祖レベルを指定するモードになります。</span><span class="sxs-lookup"><span data-stu-id="36233-116">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="36233-117">これは、<xref:System.Windows.Data.RelativeSource> プロパティが <xref:System.Windows.Data.RelativeSource.Mode%2A> に設定された状態で作成された <xref:System.Windows.Data.RelativeSourceMode.FindAncestor> に対応します。</span><span class="sxs-lookup"><span data-stu-id="36233-117">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="36233-118">`FindAncestor` モードで必要です。</span><span class="sxs-lookup"><span data-stu-id="36233-118">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="36233-119"><xref:System.Windows.Data.RelativeSource.AncestorType%2A> プロパティに指定する型の名前。</span><span class="sxs-lookup"><span data-stu-id="36233-119">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="36233-120">`FindAncestor` モードのオプションです。</span><span class="sxs-lookup"><span data-stu-id="36233-120">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="36233-121">論理ツリー内で親の方向に向けて数えた先祖レベル。</span><span class="sxs-lookup"><span data-stu-id="36233-121">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="36233-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="36233-122">Remarks</span></span>

<span data-ttu-id="36233-123">`{RelativeSource TemplatedParent}` バインディングの用法は、コントロールの UI とロジックを分離するという、より大きな構想を解決するための鍵となる手法です。</span><span class="sxs-lookup"><span data-stu-id="36233-123">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="36233-124">これによって、テンプレートが適用される親 (テンプレートが適用されるランタイム オブジェクト インスタンス) へのバインディングをテンプレート定義内から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="36233-124">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="36233-125">この場合、[TemplateBinding マークアップ拡張](templatebinding-markup-extension.md)は実際には、バインディング式 `{Binding RelativeSource={RelativeSource TemplatedParent}}` の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="36233-125">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="36233-126">`TemplateBinding` または `{RelativeSource TemplatedParent}` の使用方法はどちらも、テンプレートを定義する XAML 内でのみ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="36233-126">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="36233-127">詳細については、「[TemplateBinding のマークアップ拡張機能](templatebinding-markup-extension.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36233-127">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="36233-128">`{RelativeSource FindAncestor}` の主な用途は、コントロール テンプレート内または予測可能な独立した UI 合成です。特定の先祖の型のビジュアル ツリー内にコントロールが常に存在することがわかっているケースで使用されます。</span><span class="sxs-lookup"><span data-stu-id="36233-128">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="36233-129">たとえば、項目コントロールの各項目は `FindAncestor` を使用して、その項目コントロールの親先祖のプロパティにバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="36233-129">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="36233-130">または、テンプレート内のコントロール合成に参加している要素は、同じ合成体系の親要素に対して `FindAncestor` バインディングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="36233-130">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="36233-131">XAML 構文のセクションに示した `FindAncestor` モードのオブジェクト要素構文では、2 番目のオブジェクト要素構文は `FindAncestor` モード向けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="36233-131">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="36233-132">`FindAncestor` モードでは、<xref:System.Windows.Data.RelativeSource.AncestorType%2A> 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="36233-132">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="36233-133">検索する先祖の型への [x:Type マークアップ拡張](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)参照を使用して、<xref:System.Windows.Data.RelativeSource.AncestorType%2A> を属性として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36233-133">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="36233-134"><xref:System.Windows.Data.RelativeSource.AncestorType%2A> 値は、実行時にバインディング要求を処理する際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="36233-134">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="36233-135">`FindAncestor` モードでは、オプションの <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> プロパティは、要素ツリー内に型の先祖が複数存在する可能性がある場合に、先祖の検索のあいまいさを解消するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="36233-135">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="36233-136">`FindAncestor` モードの使用方法の詳細については、「<xref:System.Windows.Data.RelativeSource>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36233-136">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="36233-137">`{RelativeSource Self}` は、特定のインスタンスのプロパティが同じインスタンスの別のプロパティの値に依存しており、その 2 つのプロパティ間に通常の依存関係プロパティの関係 (強制変換など) が存在しない状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="36233-137">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="36233-138">まったく同じ値、まったく同じ型を持つ 2 つのプロパティが 1 つのオブジェクトに存在することはまれですが、`{RelativeSource Self}` を持つバインディングに `Converter` パラメーターを適用し、そのコンバーターを使用してソースとターゲットの型変換を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="36233-138">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="36233-139">`{RelativeSource Self}` は、<xref:System.Windows.MultiDataTrigger> の一部として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="36233-139">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="36233-140">たとえば、<xref:System.Windows.Shapes.Rectangle> という XAML は、<xref:System.Windows.FrameworkElement.Width%2A> 要素を定義します。<xref:System.Windows.Shapes.Rectangle> にどのような値が入力されても、`<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>` は常に正方形となります。</span><span class="sxs-lookup"><span data-stu-id="36233-140">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="36233-141">`{RelativeSource PreviousData}` は、データ テンプレートで使用できるほか、バインディングにデータ ソースのコレクションを使用する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="36233-141">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="36233-142">`{RelativeSource PreviousData}` を使用すると、コレクション内の隣接するデータ項目どうしの関係に注目することができます。</span><span class="sxs-lookup"><span data-stu-id="36233-142">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="36233-143">これと関連して、データ ソース内の現在の項目と直前の項目との間に <xref:System.Windows.Data.MultiBinding> を確立し、そのバインディング上のコンバーターを使用して、2 つの項目 (およびそれらのプロパティ) 間の相違を特定する手法もあります。</span><span class="sxs-lookup"><span data-stu-id="36233-143">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="36233-144">次の例の項目テンプレートに出現する 1 つ目の <xref:System.Windows.Controls.TextBlock> は、現在の数値を表示します。</span><span class="sxs-lookup"><span data-stu-id="36233-144">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="36233-145">2 つ目の <xref:System.Windows.Controls.TextBlock> バインディングは <xref:System.Windows.Data.MultiBinding> で、通常 2 つの <xref:System.Windows.Data.Binding> 構成要素を持ちます (現在のレコードと、`{RelativeSource PreviousData}` を使用して直前のデータ レコードを意図的に使用するバインディング)。</span><span class="sxs-lookup"><span data-stu-id="36233-145">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="36233-146"><xref:System.Windows.Data.MultiBinding> 上のコンバーターが、両者の差を計算し、バインディングに返します。</span><span class="sxs-lookup"><span data-stu-id="36233-146">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
</ListBox>
```

<span data-ttu-id="36233-147">ここで説明されていないデータ バインディングの概念については、[データ バインディングの概要](../../../desktop-wpf/data/data-binding-overview.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36233-147">Describing data binding as a concept is not covered here, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="36233-148">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の XAML プロセッサの実装では、このマークアップ拡張の処理は <xref:System.Windows.Data.RelativeSource> クラスによって定義されています。</span><span class="sxs-lookup"><span data-stu-id="36233-148">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="36233-149">`RelativeSource` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="36233-149">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="36233-150">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="36233-150">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="36233-151">XAML のすべてのマークアップ拡張では、それぞれの属性構文で `{` と `}` の 2 つの記号が使用されます。これは規約であり、これに従って XAML プロセッサでは、マークアップ拡張で属性を処理する必要があることが認識されます。</span><span class="sxs-lookup"><span data-stu-id="36233-151">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="36233-152">詳細については、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36233-152">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36233-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="36233-153">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="36233-154">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="36233-154">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="36233-155">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="36233-155">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="36233-156">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="36233-156">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="36233-157">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="36233-157">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="36233-158">バインディング宣言の概要</span><span class="sxs-lookup"><span data-stu-id="36233-158">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="36233-159">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="36233-159">x:Type Markup Extension</span></span>](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
