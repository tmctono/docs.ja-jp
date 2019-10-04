---
title: RelativeSource のマークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 7a9c9fe379f361dec0d65b71c4d883958be9ed2f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834828"
---
# <a name="relativesource-markupextension"></a><span data-ttu-id="ef621-102">RelativeSource のマークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="ef621-102">RelativeSource MarkupExtension</span></span>

<span data-ttu-id="ef621-103">[バインドマークアップ拡張機能](binding-markup-extension.md)内で使用されるか、XAML で確立される <xref:System.Windows.Data.Binding> 要素の @no__t プロパティを設定するときに、@no__t 0 バインディングソースのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ef621-103">Specifies properties of a <xref:System.Windows.Data.RelativeSource> binding source, to be used within a [Binding Markup Extension](binding-markup-extension.md), or when setting the <xref:System.Windows.Data.Binding.RelativeSource%2A> property of a <xref:System.Windows.Data.Binding> element established in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="ef621-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="ef621-104">XAML Attribute Usage</span></span>

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a><span data-ttu-id="ef621-105">XAML 属性の使用方法 (バインディング拡張内で入れ子にした場合)</span><span class="sxs-lookup"><span data-stu-id="ef621-105">XAML Attribute Usage (nested within Binding extension)</span></span>

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="ef621-106">XAML オブジェクト要素の使用方法</span><span class="sxs-lookup"><span data-stu-id="ef621-106">XAML Object Element Usage</span></span>

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

<span data-ttu-id="ef621-107">\- または -</span><span class="sxs-lookup"><span data-stu-id="ef621-107">-or-</span></span>

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

## <a name="xaml-values"></a><span data-ttu-id="ef621-108">XAML 値</span><span class="sxs-lookup"><span data-stu-id="ef621-108">XAML Values</span></span>

|||
|-|-|
|`modeEnumValue`|<span data-ttu-id="ef621-109">次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ef621-109">One of the following:</span></span><br /><br /> <span data-ttu-id="ef621-110">-文字列トークン `Self`;@no__t の2つのプロパティを <xref:System.Windows.Data.RelativeSourceMode.Self> に設定して作成された <xref:System.Windows.Data.RelativeSource> に対応します。</span><span class="sxs-lookup"><span data-stu-id="ef621-110">-   The string token `Self`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.Self>.</span></span><br /><span data-ttu-id="ef621-111">-文字列トークン `TemplatedParent`;@no__t の2つのプロパティを <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent> に設定して作成された <xref:System.Windows.Data.RelativeSource> に対応します。</span><span class="sxs-lookup"><span data-stu-id="ef621-111">-   The string token `TemplatedParent`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.</span></span><br /><span data-ttu-id="ef621-112">-文字列トークン `PreviousData`;@no__t の2つのプロパティを <xref:System.Windows.Data.RelativeSourceMode.PreviousData> に設定して作成された <xref:System.Windows.Data.RelativeSource> に対応します。</span><span class="sxs-lookup"><span data-stu-id="ef621-112">-   The string token `PreviousData`; corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.</span></span><br /><span data-ttu-id="ef621-113">-@No__t 0 モードの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef621-113">-   See below for information on `FindAncestor` mode.</span></span>|
|`FindAncestor`|<span data-ttu-id="ef621-114">文字列トークン `FindAncestor`。</span><span class="sxs-lookup"><span data-stu-id="ef621-114">The string token `FindAncestor`.</span></span> <span data-ttu-id="ef621-115">このトークンを使用すると、`RelativeSource` によって先祖の型およびオプションで先祖レベルを指定するモードになります。</span><span class="sxs-lookup"><span data-stu-id="ef621-115">Using this token enters a mode whereby a `RelativeSource` specifies an ancestor type and optionally an ancestor level.</span></span> <span data-ttu-id="ef621-116">これは、<xref:System.Windows.Data.RelativeSource> プロパティが <xref:System.Windows.Data.RelativeSource.Mode%2A> に設定された状態で作成された <xref:System.Windows.Data.RelativeSourceMode.FindAncestor> に対応します。</span><span class="sxs-lookup"><span data-stu-id="ef621-116">This corresponds to a <xref:System.Windows.Data.RelativeSource> as created with its <xref:System.Windows.Data.RelativeSource.Mode%2A> property set to <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.</span></span>|
|`typeName`|<span data-ttu-id="ef621-117">`FindAncestor` モードで必要です。</span><span class="sxs-lookup"><span data-stu-id="ef621-117">Required for `FindAncestor` mode.</span></span> <span data-ttu-id="ef621-118"><xref:System.Windows.Data.RelativeSource.AncestorType%2A> プロパティに指定する型の名前。</span><span class="sxs-lookup"><span data-stu-id="ef621-118">The name of a type, which fills the <xref:System.Windows.Data.RelativeSource.AncestorType%2A> property.</span></span>|
|`intLevel`|<span data-ttu-id="ef621-119">`FindAncestor` モードのオプションです。</span><span class="sxs-lookup"><span data-stu-id="ef621-119">Optional for `FindAncestor` mode.</span></span> <span data-ttu-id="ef621-120">論理ツリー内で親の方向に向けて数えた先祖レベル。</span><span class="sxs-lookup"><span data-stu-id="ef621-120">An ancestor level (evaluated towards the parent direction in the logical tree).</span></span>|

## <a name="remarks"></a><span data-ttu-id="ef621-121">コメント</span><span class="sxs-lookup"><span data-stu-id="ef621-121">Remarks</span></span>

<span data-ttu-id="ef621-122">`{RelativeSource TemplatedParent}` バインディングの使用は、コントロールの UI とコントロールのロジックを分離するという大きな概念に対処する重要な手法です。</span><span class="sxs-lookup"><span data-stu-id="ef621-122">`{RelativeSource TemplatedParent}` binding usages are a key technique that addresses a larger concept of the separation of a control's UI and a control's logic.</span></span> <span data-ttu-id="ef621-123">これによって、テンプレートが適用される親 (テンプレートが適用されるランタイム オブジェクト インスタンス) へのバインディングをテンプレート定義内から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ef621-123">This enables binding from within the template definition to the templated parent (the run time object instance where the template is applied).</span></span> <span data-ttu-id="ef621-124">この場合、 [TemplateBinding マークアップ拡張機能](templatebinding-markup-extension.md)は、実際には次のバインド式の短縮形になります。 `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="ef621-124">For this case, the [TemplateBinding Markup Extension](templatebinding-markup-extension.md) is in fact a shorthand for the following binding expression: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="ef621-125">`TemplateBinding` または `{RelativeSource TemplatedParent}` の使用は、どちらもテンプレートを定義する XAML 内でのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="ef621-125">`TemplateBinding` or `{RelativeSource TemplatedParent}` usages are both only relevant within the XAML that defines a template.</span></span> <span data-ttu-id="ef621-126">詳細については、「 [TemplateBinding Markup Extension](templatebinding-markup-extension.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef621-126">For more information, see [TemplateBinding Markup Extension](templatebinding-markup-extension.md).</span></span>

<span data-ttu-id="ef621-127">@no__t 0 は、コントロールテンプレートまたは予測可能な自己完結型 UI コンポジションで主に使用されます。この場合、コントロールは常に特定の先祖タイプのビジュアルツリー内にあることが想定されます。</span><span class="sxs-lookup"><span data-stu-id="ef621-127">`{RelativeSource FindAncestor}` is mainly used in control templates or predictable self-contained UI compositions, for cases where a control is always expected to be in a visual tree of a certain ancestor type.</span></span> <span data-ttu-id="ef621-128">たとえば、項目コントロールの各項目は `FindAncestor` を使用して、その項目コントロールの親先祖のプロパティにバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="ef621-128">For example, items of an items control might use `FindAncestor` usages to bind to properties of their items control parent ancestor.</span></span> <span data-ttu-id="ef621-129">または、テンプレート内のコントロール合成に参加している要素は、同じ合成体系の親要素に対して `FindAncestor` バインディングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef621-129">Or, elements that are part of control composition in a template can use `FindAncestor` bindings to the parent elements in that same composition structure.</span></span>

<span data-ttu-id="ef621-130">XAML 構文のセクションに示した `FindAncestor` モードのオブジェクト要素構文では、2 番目のオブジェクト要素構文は `FindAncestor` モード向けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef621-130">In the object element syntax for `FindAncestor` mode shown in the XAML Syntax sections, the second object element syntax is used specifically for `FindAncestor` mode.</span></span> <span data-ttu-id="ef621-131">`FindAncestor` モードでは、<xref:System.Windows.Data.RelativeSource.AncestorType%2A> 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef621-131">`FindAncestor` mode requires an <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value.</span></span> <span data-ttu-id="ef621-132">検索する先祖の型への[X:Type マークアップ拡張機能](../../xaml-services/x-type-markup-extension.md)の参照を使用して、属性として <xref:System.Windows.Data.RelativeSource.AncestorType%2A> を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef621-132">You must set <xref:System.Windows.Data.RelativeSource.AncestorType%2A> as an attribute using an [x:Type Markup Extension](../../xaml-services/x-type-markup-extension.md) reference to the type of ancestor to look for.</span></span> <span data-ttu-id="ef621-133"><xref:System.Windows.Data.RelativeSource.AncestorType%2A> 値は、実行時にバインディング要求を処理する際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef621-133">The <xref:System.Windows.Data.RelativeSource.AncestorType%2A> value is used when the binding request is processed at run-time.</span></span>

<span data-ttu-id="ef621-134">`FindAncestor` モードでは、オプションの <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> プロパティは、要素ツリー内に型の先祖が複数存在する可能性がある場合に、先祖の検索のあいまいさを解消するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ef621-134">For `FindAncestor` mode, the optional property <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> can help disambiguate the ancestor lookup in cases where there is possibly more than one ancestor of that type existing in the element tree.</span></span>

<span data-ttu-id="ef621-135">`FindAncestor` モードの使用方法の詳細については、「<xref:System.Windows.Data.RelativeSource>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef621-135">For more information on how to use the `FindAncestor` mode, see <xref:System.Windows.Data.RelativeSource>.</span></span>

<span data-ttu-id="ef621-136">`{RelativeSource Self}` は、インスタンスの1つのプロパティが同じインスタンスの別のプロパティの値に依存する必要があり、これら2つのプロパティ間には、一般的な依存関係プロパティの関係 (強制型変換など) が既に存在する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ef621-136">`{RelativeSource Self}` is useful for scenarios where one property of an instance should depend on the value of another property of the same instance, and no general dependency property relationship (such as coercion) already exists between those two properties.</span></span> <span data-ttu-id="ef621-137">1つのオブジェクトに2つのプロパティが存在することはめったにありませんが、値が文字どおり同じであり、同じように型指定されている場合もありますが、`{RelativeSource Self}` を持つバインディングに @no__t 0 パラメーターを適用し、コンバーターを使用してソースとターゲットの型の間で変換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ef621-137">Although it is rare that two properties exist on an object such that the values are literally identical (and are identically typed), you can also apply a `Converter` parameter to a binding that has `{RelativeSource Self}`, and use the converter to convert between source and target types.</span></span> <span data-ttu-id="ef621-138">@No__t-0 のもう1つのシナリオは、<xref:System.Windows.MultiDataTrigger> の一部です。</span><span class="sxs-lookup"><span data-stu-id="ef621-138">Another scenario for `{RelativeSource Self}` is as part of a <xref:System.Windows.MultiDataTrigger>.</span></span>

<span data-ttu-id="ef621-139">たとえば、<xref:System.Windows.Shapes.Rectangle> という XAML は、<xref:System.Windows.FrameworkElement.Width%2A> 要素を定義します。<xref:System.Windows.Shapes.Rectangle> にどのような値が入力されても、`<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>` は常に正方形となります。</span><span class="sxs-lookup"><span data-stu-id="ef621-139">For example, the following XAML defines a <xref:System.Windows.Shapes.Rectangle> element such that no matter what value is entered for <xref:System.Windows.FrameworkElement.Width%2A>, the <xref:System.Windows.Shapes.Rectangle> is always a square: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`</span></span>

<span data-ttu-id="ef621-140">`{RelativeSource PreviousData}` は、データテンプレートで、またはバインディングがデータソースとしてコレクションを使用する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ef621-140">`{RelativeSource PreviousData}` is useful either in data templates, or in cases where bindings are using a collection as the data source.</span></span> <span data-ttu-id="ef621-141">@No__t-0 を使用すると、コレクション内の隣接するデータ項目間のリレーションシップを強調表示できます。</span><span class="sxs-lookup"><span data-stu-id="ef621-141">You can use `{RelativeSource PreviousData}` to highlight relationships between adjacent data items in the collection.</span></span> <span data-ttu-id="ef621-142">これと関連して、データ ソース内の現在の項目と直前の項目との間に <xref:System.Windows.Data.MultiBinding> を確立し、そのバインディング上のコンバーターを使用して、2 つの項目 (およびそれらのプロパティ) 間の相違を特定する手法もあります。</span><span class="sxs-lookup"><span data-stu-id="ef621-142">A related technique is to establish a <xref:System.Windows.Data.MultiBinding> between the current and previous items in the data source, and use a converter on that binding to determine the difference between the two items and their properties.</span></span>

<span data-ttu-id="ef621-143">次の例の項目テンプレートに出現する 1 つ目の <xref:System.Windows.Controls.TextBlock> は、現在の数値を表示します。</span><span class="sxs-lookup"><span data-stu-id="ef621-143">In the following example, the first <xref:System.Windows.Controls.TextBlock> in the items template displays the current number.</span></span> <span data-ttu-id="ef621-144">2番目の <xref:System.Windows.Controls.TextBlock> バインド @no__t は、とに @no__t 2 つの構成要素があることを示します。これは、現在のレコードと、前のデータレコードを意図的に `{RelativeSource PreviousData}` を使用して使用するバインドです。</span><span class="sxs-lookup"><span data-stu-id="ef621-144">The second <xref:System.Windows.Controls.TextBlock> binding is a <xref:System.Windows.Data.MultiBinding> that nominally has two <xref:System.Windows.Data.Binding> constituents: the current record, and a binding that deliberately uses the previous data record by using `{RelativeSource PreviousData}`.</span></span> <span data-ttu-id="ef621-145"><xref:System.Windows.Data.MultiBinding> 上のコンバーターが、両者の差を計算し、バインディングに返します。</span><span class="sxs-lookup"><span data-stu-id="ef621-145">Then, a converter on the <xref:System.Windows.Data.MultiBinding> calculates the difference and returns it to the binding.</span></span>

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
```

<span data-ttu-id="ef621-146">データバインディングの概念については、ここでは説明しません。「[データバインディングの概要](../data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef621-146">Describing data binding as a concept is not covered here, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="ef621-147">@No__t 0 の XAML プロセッサ実装では、このマークアップ拡張機能の処理は、<xref:System.Windows.Data.RelativeSource> クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="ef621-147">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.Data.RelativeSource> class.</span></span>

<span data-ttu-id="ef621-148">`RelativeSource` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="ef621-148">`RelativeSource` is a markup extension.</span></span> <span data-ttu-id="ef621-149">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="ef621-149">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="ef621-150">XAML のすべてのマークアップ拡張は、属性構文で `{` および `}` 文字を使用します。これは、マークアップ拡張機能が属性を処理する必要があることを XAML プロセッサが認識する規則です。</span><span class="sxs-lookup"><span data-stu-id="ef621-150">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="ef621-151">詳細については、「[マークアップ拡張機能」および「WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef621-151">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef621-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef621-152">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="ef621-153">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ef621-153">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="ef621-154">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ef621-154">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="ef621-155">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="ef621-155">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="ef621-156">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="ef621-156">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="ef621-157">バインディング宣言の概要</span><span class="sxs-lookup"><span data-stu-id="ef621-157">Binding Declarations Overview</span></span>](../data/binding-declarations-overview.md)
- [<span data-ttu-id="ef621-158">x:Type マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="ef621-158">x:Type Markup Extension</span></span>](../../xaml-services/x-type-markup-extension.md)
