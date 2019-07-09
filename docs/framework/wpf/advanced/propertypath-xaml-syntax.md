---
title: PropertyPath の XAML 構文
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 5dc8fc8c43e43691c46ad84379fe2bcb23987667
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660795"
---
# <a name="propertypath-xaml-syntax"></a><span data-ttu-id="6a06f-102">PropertyPath の XAML 構文</span><span class="sxs-lookup"><span data-stu-id="6a06f-102">PropertyPath XAML Syntax</span></span>

<span data-ttu-id="6a06f-103"><xref:System.Windows.PropertyPath>オブジェクトがサポートする、複雑なインライン[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]構文を使用するさまざまなプロパティを設定するため、<xref:System.Windows.PropertyPath>型を値として。</span><span class="sxs-lookup"><span data-stu-id="6a06f-103">The <xref:System.Windows.PropertyPath> object supports a complex inline [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] syntax for setting various properties that take the <xref:System.Windows.PropertyPath> type as their value.</span></span> <span data-ttu-id="6a06f-104">このトピックの「ドキュメント、<xref:System.Windows.PropertyPath>バインディングとアニメーション構文に適用される構文です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-104">This topic documents the <xref:System.Windows.PropertyPath> syntax as applied to binding and animation syntaxes.</span></span>

<a name="where"></a>

## <a name="where-propertypath-is-used"></a><span data-ttu-id="6a06f-105">PropertyPath を使用する場所</span><span class="sxs-lookup"><span data-stu-id="6a06f-105">Where PropertyPath Is Used</span></span>

<span data-ttu-id="6a06f-106"><xref:System.Windows.PropertyPath> いくつかで使用される共通オブジェクトは、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]機能します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-106"><xref:System.Windows.PropertyPath> is a common object that is used in several [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] features.</span></span> <span data-ttu-id="6a06f-107">一般的な使用に関係なく<xref:System.Windows.PropertyPath>プロパティ パス情報を伝達するために使用法は、各機能領域で<xref:System.Windows.PropertyPath>によって変化する型に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-107">Despite using the common <xref:System.Windows.PropertyPath> to convey property path information, the usages for each feature area where <xref:System.Windows.PropertyPath> is used as a type vary.</span></span> <span data-ttu-id="6a06f-108">そのため、機能ごとに構文を説明する方が実際的です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-108">Therefore, it is more practical to document the syntaxes on a per-feature basis.</span></span>

<span data-ttu-id="6a06f-109">主に、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用<xref:System.Windows.PropertyPath>オブジェクト モデルのオブジェクト データ ソースのプロパティを走査するパスを記述して、ターゲット アニメーションのターゲット パスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-109">Primarily, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uses <xref:System.Windows.PropertyPath> to describe object-model paths for traversing the properties of an object data source, and to describe the target path for targeted animations.</span></span>

<span data-ttu-id="6a06f-110">などのスタイルとテンプレート プロパティ<xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType>よう表面的なプロパティの修飾名を取得、<xref:System.Windows.PropertyPath>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-110">Some style and template properties such as <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> take a qualified property name that superficially resembles a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="6a06f-111">これは、true ではありませんが、 <xref:System.Windows.PropertyPath>; これは、修飾*owner.property*文字列の形式の使用法、WPF によって有効になっている[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサの型コンバーターと組み合わせて<xref:System.Windows.DependencyProperty>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-111">But this is not a true <xref:System.Windows.PropertyPath>; instead it is a qualified *owner.property* string format usage that is enabled by the WPF [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor in combination with the type converter for <xref:System.Windows.DependencyProperty>.</span></span>

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a><span data-ttu-id="6a06f-112">データ バインディングにおけるオブジェクトの PropertyPath</span><span class="sxs-lookup"><span data-stu-id="6a06f-112">PropertyPath for Objects in Data Binding</span></span>

<span data-ttu-id="6a06f-113">データ バインディングは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の機能であり、依存関係プロパティのターゲット値にバインドできます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-113">Data binding is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] feature whereby you can bind to the target value of any dependency property.</span></span> <span data-ttu-id="6a06f-114">ただし、このようなデータ バインディングのソースが依存関係プロパティである必要はなく、適切なデータ プロバイダーで認識される任意のプロパティ型でかまいません。</span><span class="sxs-lookup"><span data-stu-id="6a06f-114">However, the source of such a data binding need not be a dependency property; it can be any property type that is recognized by the applicable data provider.</span></span> <span data-ttu-id="6a06f-115">プロパティのパスは特にため、 <xref:System.Windows.Data.ObjectDataProvider>、バインディング ソースからの取得に使用される[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]オブジェクトとそのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="6a06f-115">Property paths are particularly used for the <xref:System.Windows.Data.ObjectDataProvider>, which is used for obtaining binding sources from [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects and their properties.</span></span>

<span data-ttu-id="6a06f-116">そのデータ バインディングに注意してください[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]は使いません<xref:System.Windows.PropertyPath>は使用されないため、<xref:System.Windows.Data.Binding.Path%2A>で、<xref:System.Windows.Data.Binding>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-116">Note that data binding to [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] does not use <xref:System.Windows.PropertyPath>, because it does not use <xref:System.Windows.Data.Binding.Path%2A> in the <xref:System.Windows.Data.Binding>.</span></span> <span data-ttu-id="6a06f-117">使用する代わりに、<xref:System.Windows.Data.Binding.XPath%2A>に有効な XPath 構文を指定し、[!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)]データ。</span><span class="sxs-lookup"><span data-stu-id="6a06f-117">Instead, you use <xref:System.Windows.Data.Binding.XPath%2A> and specify valid XPath syntax into the [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] of the data.</span></span> <span data-ttu-id="6a06f-118"><xref:System.Windows.Data.Binding.XPath%2A> 文字列としても指定されますが、ここでは文書化されていません。参照してください[XMLDataProvider と XPath クエリを使用して XML データにバインド](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-118"><xref:System.Windows.Data.Binding.XPath%2A> is also specified as a string, but is not documented here; see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span>

<span data-ttu-id="6a06f-119">データ バインディングにおけるプロパティ パスを理解するうえで鍵となるのは、個々のプロパティ値をバインドの対象にすることも、リストまたはコレクションを使用するターゲット プロパティにバインドすることもできるということです。</span><span class="sxs-lookup"><span data-stu-id="6a06f-119">A key to understanding property paths in data binding is that you can target the binding to an individual property value, or you can instead bind to target properties that take lists or collections.</span></span> <span data-ttu-id="6a06f-120">バインド インスタンスのコレクションをバインドする場合、<xref:System.Windows.Controls.ListBox>が、コレクション内にデータ項目の数によって拡張される、プロパティのパスは、個々 のコレクション アイテムのコレクション オブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-120">If you are binding collections, for instance binding a <xref:System.Windows.Controls.ListBox> that will expand depending on how many data items are in the collection, then your property path should reference the collection object, not individual collection items.</span></span> <span data-ttu-id="6a06f-121">データ バインディング エンジンは、データ ソースのバインディング ターゲットの型に自動的に、設定などの動作として使用されるコレクションに一致する<xref:System.Windows.Controls.ListBox>項目配列。</span><span class="sxs-lookup"><span data-stu-id="6a06f-121">The data binding engine will match the collection used as the data source to the type of the binding target automatically, resulting in behavior such as populating a <xref:System.Windows.Controls.ListBox> with an items array.</span></span>

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a><span data-ttu-id="6a06f-122">データ コンテキストとしての直接のオブジェクト上の単一のプロパティ</span><span class="sxs-lookup"><span data-stu-id="6a06f-122">Single Property on the Immediate Object as Data Context</span></span>

```xml
<Binding Path="propertyName" .../>
```

<span data-ttu-id="6a06f-123">*propertyName*現在内にあるプロパティの名前を解決する必要があります<xref:System.Windows.FrameworkElement.DataContext%2A>の<xref:System.Windows.Data.Binding.Path%2A>使用量。</span><span class="sxs-lookup"><span data-stu-id="6a06f-123">*propertyName* must resolve to be the name of a property that is in the current <xref:System.Windows.FrameworkElement.DataContext%2A> for a <xref:System.Windows.Data.Binding.Path%2A> usage.</span></span> <span data-ttu-id="6a06f-124">バインドがソースを更新する場合、そのプロパティは読み書き可能であり、ソース オブジェクトは変更可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-124">If your binding updates the source, that property must be read/write and the source object must be mutable.</span></span>

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a><span data-ttu-id="6a06f-125">データ コンテキストとしての直接のオブジェクト上の単一のインデクサー</span><span class="sxs-lookup"><span data-stu-id="6a06f-125">Single Indexer on the Immediate Object as Data Context</span></span>

```xml
<Binding Path="[key]" .../>
```

<span data-ttu-id="6a06f-126">`key` には、ディクショナリまたはハッシュ テーブルに対する型指定されたインデックス、または配列の整数インデックスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-126">`key` must be either the typed index to a dictionary or hash table, or the integer index of an array.</span></span> <span data-ttu-id="6a06f-127">また、キーの値は、適用先のプロパティに直接バインドできる型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-127">Also, the value of the key must be a type that is directly bindable to the property where it is applied.</span></span> <span data-ttu-id="6a06f-128">たとえば、文字列キーと文字列値を格納するハッシュ テーブルはこのように使用するのテキストにバインドする、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-128">For instance, a hash table that contains string keys and string values can be used this way to bind to Text for a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="6a06f-129">キーがコレクションまたはサブインデックスを指す場合は、この構文を使用して、ターゲット コレクション プロパティにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-129">Or, if the key points to a collection or subindex, you could use this syntax to bind to a target collection property.</span></span> <span data-ttu-id="6a06f-130">それ以外の場合は、`<Binding Path="[key].propertyName" .../>` などの構文を通じて、特定のプロパティを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-130">Otherwise, you need to reference a specific property, through a syntax such as `<Binding Path="[key].propertyName" .../>`.</span></span>

<span data-ttu-id="6a06f-131">必要に応じて、インデックスの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-131">You can specify the type of the index if necessary.</span></span> <span data-ttu-id="6a06f-132">詳細については、インデックス付きプロパティのパスのこの側面は、次を参照してください。<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-132">For details on this aspect of an indexed property path, see <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.</span></span>

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a><span data-ttu-id="6a06f-133">複数プロパティ (間接的なプロパティのターゲット設定)</span><span class="sxs-lookup"><span data-stu-id="6a06f-133">Multiple Property (Indirect Property Targeting)</span></span>

```xml
<Binding Path="propertyName.propertyName2" .../>
```

<span data-ttu-id="6a06f-134">`propertyName` 現在ではプロパティの名前を解決する必要があります<xref:System.Windows.FrameworkElement.DataContext%2A>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-134">`propertyName` must resolve to be the name of a property that is the current <xref:System.Windows.FrameworkElement.DataContext%2A>.</span></span> <span data-ttu-id="6a06f-135">パス プロパティ `propertyName` と `propertyName2` は、リレーションシップ内に存在する任意のプロパティにすることができます。`propertyName2` は、`propertyName` の値である型に存在するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="6a06f-135">The path properties `propertyName` and `propertyName2` can be any properties that exist in a relationship, where `propertyName2` is a property that exists on the type that is the value of `propertyName`.</span></span>

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a><span data-ttu-id="6a06f-136">添付または型修飾された単一のプロパティ</span><span class="sxs-lookup"><span data-stu-id="6a06f-136">Single Property, Attached or Otherwise Type-Qualified</span></span>

```xml
<object property="(ownerType.propertyName)" .../>
```

<span data-ttu-id="6a06f-137">いることを示す、かっこ内のこのプロパティを<xref:System.Windows.PropertyPath>部分修飾を使用して構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-137">The parentheses indicate that this property in a <xref:System.Windows.PropertyPath> should be constructed using a partial qualification.</span></span> <span data-ttu-id="6a06f-138">XML 名前空間を使用して、適切なマッピングを含む型を検出できます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-138">It can use an XML namespace to find the type with an appropriate mapping.</span></span> <span data-ttu-id="6a06f-139">`ownerType`型を検索、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサからへのアクセス、<xref:System.Windows.Markup.XmlnsDefinitionAttribute>各アセンブリで宣言します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-139">The `ownerType` searches types that a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor has access to, through the <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declarations in each assembly.</span></span> <span data-ttu-id="6a06f-140">ほとんどのアプリケーションは、[!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 名前空間にマップされた既定の XML 名前空間を持ちます。そのため、プレフィックスは通常、カスタム型や、名前空間の外部の型に限って必要です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-140">Most applications have the default XML namespace mapped to the [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] namespace, so a prefix is usually only necessary for custom types or types otherwise outside that namespace.</span></span>  <span data-ttu-id="6a06f-141">`propertyName` は、`ownerType` に存在するプロパティの名前に解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-141">`propertyName` must resolve to be the name of a property existing on the `ownerType`.</span></span> <span data-ttu-id="6a06f-142">この構文は、通常、次のいずれかの場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-142">This syntax is generally used for one of the following cases:</span></span>

- <span data-ttu-id="6a06f-143">指定されたターゲット型を持たないスタイルまたはテンプレート内の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] でパスが指定されている場合。</span><span class="sxs-lookup"><span data-stu-id="6a06f-143">The path is specified in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that is in a style or template that does not have a specified Target Type.</span></span> <span data-ttu-id="6a06f-144">通常、これ以外のケースでの修飾子の使用は無効です。スタイルやテンプレート以外のケースでは、プロパティは型ではなくインスタンス上に存在します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-144">A qualified usage is generally not valid for cases other than this, because in non-style, non-template cases, the property exists on an instance, not a type.</span></span>

- <span data-ttu-id="6a06f-145">プロパティが添付プロパティの場合。</span><span class="sxs-lookup"><span data-stu-id="6a06f-145">The property is an attached property.</span></span>

- <span data-ttu-id="6a06f-146">静的プロパティにバインドしている場合。</span><span class="sxs-lookup"><span data-stu-id="6a06f-146">You are binding to a static property.</span></span>

<span data-ttu-id="6a06f-147">として指定されるプロパティのストーリー ボード ターゲットとして使用して、`propertyName`必要があります、<xref:System.Windows.DependencyProperty>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-147">For use as storyboard target, the property specified as `propertyName` must be a <xref:System.Windows.DependencyProperty>.</span></span>

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a><span data-ttu-id="6a06f-148">ソースの走査 (コレクションの階層へのバインド)</span><span class="sxs-lookup"><span data-stu-id="6a06f-148">Source Traversal (Binding to Hierarchies of Collections)</span></span>

```xml
<object Path="propertyName/propertyNameX" .../>
```

<span data-ttu-id="6a06f-149">この構文で、/ は階層的なデータ ソース オブジェクト内を移動するために使用されます。また、/ 文字を連続で使用することによる階層内での複数ステップの移動がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6a06f-149">The / in this syntax is used to navigate within a hierarchical data source object, and multiple steps into the hierarchy with successive / characters are supported.</span></span> <span data-ttu-id="6a06f-150">ソースの走査は現在のレコード ポインター位置に対応しており、これはデータをビューの UI と同期することによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-150">The source traversal accounts for the current record pointer position, which is determined by synchronizing the data with the UI of its view.</span></span> <span data-ttu-id="6a06f-151">階層的なデータ ソース オブジェクトのバインドおよびデータ バインディングにおける現在のレコード ポインターの概念の詳細については、「[階層データでマスター詳細パターンを使用する](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)」または「[データ バインディングの概要](../data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a06f-151">For details on binding with hierarchical data source objects, and the concept of current record pointer in data binding, see [Use the Master-Detail Pattern with Hierarchical Data](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) or [Data Binding Overview](../data/data-binding-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a06f-152">この構文は、一見すると [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] に似ています。</span><span class="sxs-lookup"><span data-stu-id="6a06f-152">Superficially, this syntax resembles [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)].</span></span> <span data-ttu-id="6a06f-153">真の[!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]にバインドするための式、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]としてデータ ソースが使用されていない、<xref:System.Windows.Data.Binding.Path%2A>値し、相互に排他的に使用する代わりに<xref:System.Windows.Data.Binding.XPath%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6a06f-153">A true [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] expression for binding to an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data source is not used as a <xref:System.Windows.Data.Binding.Path%2A> value and should instead be used for the mutually exclusive <xref:System.Windows.Data.Binding.XPath%2A> property.</span></span>

### <a name="collection-views"></a><span data-ttu-id="6a06f-154">コレクション ビュー</span><span class="sxs-lookup"><span data-stu-id="6a06f-154">Collection Views</span></span>

<span data-ttu-id="6a06f-155">名前付きコレクション ビューを参照するには、コレクション ビュー名の前にハッシュ記号 (`#`) を付けます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-155">To reference a named collection view, prefix the collection view name with the hash character (`#`).</span></span>

### <a name="current-record-pointer"></a><span data-ttu-id="6a06f-156">現在のレコード ポインター</span><span class="sxs-lookup"><span data-stu-id="6a06f-156">Current Record Pointer</span></span>

<span data-ttu-id="6a06f-157">コレクション ビューまたはマスター詳細データ バインディング シナリオの現在のレコード ポインターを参照するには、パス文字列の先頭にスラッシュ (`/`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-157">To reference the current record pointer for a collection view or master detail data binding scenario, start the path string with a forward slash (`/`).</span></span> <span data-ttu-id="6a06f-158">スラッシュより後ろのパスは、現在のレコード ポインターから開始して走査されます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-158">Any path past the forward slash is traversed starting from the current record pointer.</span></span>

### <a name="multiple-indexers"></a><span data-ttu-id="6a06f-159">複数のインデクサー</span><span class="sxs-lookup"><span data-stu-id="6a06f-159">Multiple Indexers</span></span>

```xaml
<object Path="[index1,index2...]" .../>
```

<span data-ttu-id="6a06f-160">または</span><span class="sxs-lookup"><span data-stu-id="6a06f-160">or</span></span>

```xaml
<object Path="propertyName[index,index2...]" .../>
```

<span data-ttu-id="6a06f-161">あるオブジェクトが複数のインデクサーをサポートする場合、それらのインデクサーは、配列参照構文のように、順番に指定できます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-161">If a given object supports multiple indexers, those indexers can be specified in order, similar to an array referencing syntax.</span></span> <span data-ttu-id="6a06f-162">該当のオブジェクトは、現在のコンテキスト、または複数のインデックス オブジェクトが含まれるプロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-162">The object in question can be either the current context or the value of a property that contains a multiple index object.</span></span>

<span data-ttu-id="6a06f-163">既定では、インデクサー値は、基になるオブジェクトの特性を使用して型指定されます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-163">By default, the indexer values are typed by using the characteristics of the underlying object.</span></span> <span data-ttu-id="6a06f-164">必要に応じて、インデックスの型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-164">You can specify the type of the index if necessary.</span></span> <span data-ttu-id="6a06f-165">インデクサーの詳細については、「<xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-165">For details on typing the indexers, see <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.</span></span>

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a><span data-ttu-id="6a06f-166">構文の混合</span><span class="sxs-lookup"><span data-stu-id="6a06f-166">Mixing Syntaxes</span></span>

<span data-ttu-id="6a06f-167">上記の各構文は、混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-167">Each of the syntaxes shown above can be interspersed.</span></span> <span data-ttu-id="6a06f-168">特定の x、y の色にプロパティのパスを作成する例を次に、`ColorGrid`のピクセル グリッド配列を含むプロパティ<xref:System.Windows.Media.SolidColorBrush>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6a06f-168">For instance, the following is an example that creates a property path to the color at a particular x,y of a `ColorGrid` property that contains a pixel grid array of <xref:System.Windows.Media.SolidColorBrush> objects:</span></span>

```xml
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>
```

### <a name="escapes-for-property-path-strings"></a><span data-ttu-id="6a06f-169">プロパティ パス文字列のエスケープ</span><span class="sxs-lookup"><span data-stu-id="6a06f-169">Escapes for Property Path Strings</span></span>

<span data-ttu-id="6a06f-170">特定のビジネス オブジェクトでは、正しく解析するために、プロパティ パス文字列にエスケープ シーケンスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-170">For certain business objects, you might encounter a case where the property path string requires an escape sequence in order to parse correctly.</span></span> <span data-ttu-id="6a06f-171">このような文字の多くには、通常ビジネス オブジェクトを定義するために使用される言語において、名前付けの相互作用に関する同様の問題があるため、エスケープが必要になることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="6a06f-171">The need to escape should be rare, because many of these characters have similar naming-interaction issues in languages that would typically be used to define the business object.</span></span>

- <span data-ttu-id="6a06f-172">インデクサー ([ ]) 内では、キャレット文字 (^) は次の文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="6a06f-172">Inside indexers ([ ]), the caret character (^) escapes the next character.</span></span>

- <span data-ttu-id="6a06f-173">XML 言語定義で特別な意味を持つ特定の文字を (XML エンティティを使用して) エスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-173">You must escape (using XML entities) certain characters that are special to the XML language definition.</span></span> <span data-ttu-id="6a06f-174">文字 "&" をエスケープするには、`&` を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-174">Use `&` to escape the character "&".</span></span> <span data-ttu-id="6a06f-175">終了タグ ">" をエスケープするには、`>` を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-175">Use `>` to escape the end tag ">".</span></span>

- <span data-ttu-id="6a06f-176">マークアップ拡張機能の処理に関する WPF XAML パーサーの動作で特別な意味を持つ文字を、(バックスラッシュ `\` を使用して) エスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-176">You must escape (using backslash `\`) characters that are special to the WPF XAML parser behavior for processing a markup extension.</span></span>

  - <span data-ttu-id="6a06f-177">バックスラッシュ (`\`) は、それ自体がエスケープ文字です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-177">Backslash (`\`) is the escape character itself.</span></span>

  - <span data-ttu-id="6a06f-178">等号 (`=`) は、プロパティ名とプロパティ値を区切ります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-178">The equal sign (`=`) separates property name from property value.</span></span>

  - <span data-ttu-id="6a06f-179">コンマ (`,`) は、複数のプロパティを区切ります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-179">Comma (`,`) separates properties.</span></span>

  - <span data-ttu-id="6a06f-180">右中かっこ (`}`) は、マークアップ拡張機能の終了を示します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-180">The right curly brace (`}`) is the end of a markup extension.</span></span>

> [!NOTE]
> <span data-ttu-id="6a06f-181">厳密に言うと、これらのエスケープはストーリーボードのプロパティ パスに役立ちますが、通常は既存の WPF オブジェクトのオブジェクト モデルを走査するので、エスケープは不要です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-181">Technically, these escapes work for a storyboard property path also, but you are usually traversing object models for existing WPF objects, and escaping should be unnecessary.</span></span>

<a name="databinding_sa"></a>

## <a name="propertypath-for-animation-targets"></a><span data-ttu-id="6a06f-182">アニメーション ターゲットの PropertyPath</span><span class="sxs-lookup"><span data-stu-id="6a06f-182">PropertyPath for Animation Targets</span></span>

<span data-ttu-id="6a06f-183">アニメーションのターゲット プロパティは、依存関係プロパティを受け取るいずれかである必要があります、<xref:System.Windows.Freezable>またはプリミティブ型。</span><span class="sxs-lookup"><span data-stu-id="6a06f-183">The target property of an animation must be a dependency property that takes either a <xref:System.Windows.Freezable> or a primitive type.</span></span> <span data-ttu-id="6a06f-184">ただし、型のターゲット プロパティと最終的なアニメーション プロパティは異なるオブジェクト上に存在できます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-184">However, the targeted property on a type and the eventual animated property can exist on different objects.</span></span> <span data-ttu-id="6a06f-185">アニメーションの場合は、プロパティ パスを使用して、プロパティ値内のオブジェクトとプロパティのリレーションシップを走査することによって、名前付きのアニメーション ターゲット オブジェクトのプロパティと目的のターゲット アニメーション プロパティの間の接続が定義されます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-185">For animations, a property path is used to define the connection between the named animation target object's property and the intended target animation property, by traversing object-property relationships in the property values.</span></span>

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a><span data-ttu-id="6a06f-186">アニメーションに関するオブジェクトとプロパティの一般的な注意事項</span><span class="sxs-lookup"><span data-stu-id="6a06f-186">General Object-Property Considerations for Animations</span></span>

<span data-ttu-id="6a06f-187">一般的なアニメーションの概念の詳細については、「[ストーリーボードの概要](../graphics-multimedia/storyboards-overview.md)」および「[アニメーションの概要](../graphics-multimedia/animation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a06f-187">For more information on animation concepts in general, see [Storyboards Overview](../graphics-multimedia/storyboards-overview.md) and [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

<span data-ttu-id="6a06f-188">値型またはアニメーション化されているプロパティはいずれかである必要があります、<xref:System.Windows.Freezable>型またはプリミティブです。</span><span class="sxs-lookup"><span data-stu-id="6a06f-188">The value type or the property being animated must be either a <xref:System.Windows.Freezable> type or a primitive.</span></span> <span data-ttu-id="6a06f-189">パスを開始するプロパティは、指定した上に存在する依存関係プロパティの名前に解決する必要があります<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>型。</span><span class="sxs-lookup"><span data-stu-id="6a06f-189">The property that starts the path must resolve to be the name of a dependency property that exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<span data-ttu-id="6a06f-190">アニメーションの複製をサポートするために、<xref:System.Windows.Freezable>が既に固定されているで指定されたオブジェクト<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>必要があります、<xref:System.Windows.FrameworkElement>または<xref:System.Windows.FrameworkContentElement>クラスを派生します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-190">In order to support cloning for animating a <xref:System.Windows.Freezable> that is already frozen, the object specified by <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> must be a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class.</span></span>

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a><span data-ttu-id="6a06f-191">ターゲット オブジェクト上の単一プロパティ</span><span class="sxs-lookup"><span data-stu-id="6a06f-191">Single Property on the Target Object</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName" .../>
```

<span data-ttu-id="6a06f-192">`propertyName` 指定した上に存在する依存関係プロパティの名前を指定する必要があります<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>型。</span><span class="sxs-lookup"><span data-stu-id="6a06f-192">`propertyName` must resolve to be the name of a dependency property that exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a><span data-ttu-id="6a06f-193">間接的なプロパティのターゲット設定</span><span class="sxs-lookup"><span data-stu-id="6a06f-193">Indirect Property Targeting</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>
```

<span data-ttu-id="6a06f-194">`propertyName` いずれかであるプロパティにする必要があります、<xref:System.Windows.Freezable>値型または指定した上に存在するプリミティブ型<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>型。</span><span class="sxs-lookup"><span data-stu-id="6a06f-194">`propertyName` must be a property that is either a <xref:System.Windows.Freezable> value type or a primitive, which exists on the specified <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> type.</span></span>

<span data-ttu-id="6a06f-195">`propertyName2` は、`propertyName` の値であるオブジェクトに存在する依存関係プロパティの名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-195">`propertyName2` must be the name of a dependency property that exists on the object that is the value of `propertyName`.</span></span> <span data-ttu-id="6a06f-196">つまり、`propertyName2`である型の依存関係プロパティとして存在する必要があります、 `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-196">In other words, `propertyName2` must exist as a dependency property on the type that is the `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.</span></span>

<span data-ttu-id="6a06f-197">適用されるスタイルとテンプレートにより、アニメーションの間接的なターゲット設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-197">Indirect targeting of animations is necessary because of applied styles and templates.</span></span> <span data-ttu-id="6a06f-198">必要があるアニメーションを対象にするため、<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>によって、ターゲット オブジェクトに名前が確立されている[X:name](../../xaml-services/x-name-directive.md)または<xref:System.Windows.FrameworkElement.Name%2A>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-198">In order to target an animation, you need a <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> on a target object, and that name is established by [x:Name](../../xaml-services/x-name-directive.md) or <xref:System.Windows.FrameworkElement.Name%2A>.</span></span> <span data-ttu-id="6a06f-199">テンプレートとスタイルの要素が名前を設定するが、また、その名前は、スタイルとテンプレートの名前スコープ内で有効なだけです。</span><span class="sxs-lookup"><span data-stu-id="6a06f-199">Although template and style elements also can have names, those names are only valid within the namescope of the style and template.</span></span> <span data-ttu-id="6a06f-200">(テンプレートとスタイルは、アプリケーション マークアップと名前スコープを共有するが場合、名一意ではありません。</span><span class="sxs-lookup"><span data-stu-id="6a06f-200">(If templates and styles did share namescopes with application markup, names couldn't be unique.</span></span> <span data-ttu-id="6a06f-201">スタイルとテンプレートのインスタンス間で共有される文字どおりと重複する名前が永続化します。)このため、アニメーション化する要素の個々のプロパティがスタイルやテンプレートに基づく場合は、スタイル テンプレートに基づかない、名前付きの要素インスタンスで操作を開始し、スタイルまたはテンプレートのビジュアル ツリーに対象を移動し、アニメーション化する目的のプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6a06f-201">The styles and templates are literally shared between instances and would perpetuate duplicate names.) Thus, if the individual properties of an element that you might wish to animate came from a style or template, you need to start with a named element instance that is not from a style template, and then target into the style or template visual tree to arrive at the property you wish to animate.</span></span>

<span data-ttu-id="6a06f-202">たとえば、<xref:System.Windows.Controls.Panel.Background%2A>のプロパティを<xref:System.Windows.Controls.Panel>がすべてでは<xref:System.Windows.Media.Brush>(実際には、 <xref:System.Windows.Media.SolidColorBrush>)、テーマ テンプレートから付属しています。</span><span class="sxs-lookup"><span data-stu-id="6a06f-202">For instance, the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Panel> is a complete <xref:System.Windows.Media.Brush> (actually a <xref:System.Windows.Media.SolidColorBrush>) that came from a theme template.</span></span> <span data-ttu-id="6a06f-203">アニメーション化する、<xref:System.Windows.Media.Brush>完全には必要があります、BrushAnimation (おそらく 1 つのすべて<xref:System.Windows.Media.Brush>型)、そのような型はありません。</span><span class="sxs-lookup"><span data-stu-id="6a06f-203">To animate a <xref:System.Windows.Media.Brush> completely, there would need to be a BrushAnimation (probably one for every <xref:System.Windows.Media.Brush> type) and there is no such type.</span></span> <span data-ttu-id="6a06f-204">特定のプロパティのアニメーション代わりに、ブラシをアニメーション化する<xref:System.Windows.Media.Brush>型。</span><span class="sxs-lookup"><span data-stu-id="6a06f-204">To animate a Brush, you instead animate properties of a particular <xref:System.Windows.Media.Brush> type.</span></span> <span data-ttu-id="6a06f-205">取得する必要がある<xref:System.Windows.Media.SolidColorBrush>にその<xref:System.Windows.Media.SolidColorBrush.Color%2A>を適用する、<xref:System.Windows.Media.Animation.ColorAnimation>があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-205">You need to get from <xref:System.Windows.Media.SolidColorBrush> to its <xref:System.Windows.Media.SolidColorBrush.Color%2A> to apply a <xref:System.Windows.Media.Animation.ColorAnimation> there.</span></span> <span data-ttu-id="6a06f-206">この例のプロパティ パスは `Background.Color` です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-206">The property path for this example would be `Background.Color`.</span></span>

<a name="attachedanim"></a>

### <a name="attached-properties"></a><span data-ttu-id="6a06f-207">アタッチされるプロパティ</span><span class="sxs-lookup"><span data-stu-id="6a06f-207">Attached Properties</span></span>

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>
```

<span data-ttu-id="6a06f-208">いることを示す、かっこ内のこのプロパティを<xref:System.Windows.PropertyPath>部分修飾を使用して構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-208">The parentheses indicate that this property in a <xref:System.Windows.PropertyPath> should be constructed using a partial qualification.</span></span> <span data-ttu-id="6a06f-209">XML 名前空間を使用して型を検出できます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-209">It can use an XML namespace to find the type.</span></span> <span data-ttu-id="6a06f-210">`ownerType`型を検索、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロセッサからへのアクセス、<xref:System.Windows.Markup.XmlnsDefinitionAttribute>各アセンブリで宣言します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-210">The `ownerType` searches types that a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor has access to, through the <xref:System.Windows.Markup.XmlnsDefinitionAttribute> declarations in each assembly.</span></span> <span data-ttu-id="6a06f-211">ほとんどのアプリケーションは、[!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] 名前空間にマップされた既定の XML 名前空間を持ちます。そのため、プレフィックスは通常、カスタム型や、名前空間の外部の型に限って必要です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-211">Most applications have the default XML namespace mapped to the [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] namespace, so a prefix is usually only necessary for custom types or types otherwise outside that namespace.</span></span> <span data-ttu-id="6a06f-212">`propertyName` は、`ownerType` に存在するプロパティの名前に解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a06f-212">`propertyName` must resolve to be the name of a property existing on the `ownerType`.</span></span> <span data-ttu-id="6a06f-213">として指定されたプロパティ`propertyName`必要があります、<xref:System.Windows.DependencyProperty>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-213">The property specified as `propertyName` must be a <xref:System.Windows.DependencyProperty>.</span></span> <span data-ttu-id="6a06f-214">(すべて[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]添付プロパティは、依存関係プロパティとして実装されるので、この問題は、カスタム添付プロパティの問題になるだけです)。</span><span class="sxs-lookup"><span data-stu-id="6a06f-214">(All [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attached properties are implemented as dependency properties, so this issue is only of concern for custom attached properties.)</span></span>

<a name="indexanim"></a>

### <a name="indexers"></a><span data-ttu-id="6a06f-215">インデクサー</span><span class="sxs-lookup"><span data-stu-id="6a06f-215">Indexers</span></span>

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>
```

<span data-ttu-id="6a06f-216">ほとんどの依存関係プロパティまたは<xref:System.Windows.Freezable>型はインデクサーをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6a06f-216">Most dependency properties or <xref:System.Windows.Freezable> types do not support an indexer.</span></span> <span data-ttu-id="6a06f-217">そのため、アニメーション パス内でインデクサーを使用するのは、名前付きターゲット上でチェーンを開始するプロパティと、最終的にアニメーション化されるプロパティの間の中間位置に限られます。</span><span class="sxs-lookup"><span data-stu-id="6a06f-217">Therefore, the only usage for an indexer in an animation path is at an intermediate position between the property that starts the chain on the named target and the eventual animated property.</span></span> <span data-ttu-id="6a06f-218">提供される構文の中で、これは `propertyName2` です。</span><span class="sxs-lookup"><span data-stu-id="6a06f-218">In the provided syntax, that is `propertyName2`.</span></span> <span data-ttu-id="6a06f-219">インデクサーの使用を中間プロパティがコレクションなどの場合必要あります、<xref:System.Windows.Media.TransformGroup>などのプロパティのパスで`RenderTransform.Children[1].Angle`します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-219">For instance, an indexer usage might be necessary if the intermediate property is a collection such as <xref:System.Windows.Media.TransformGroup>, in a property path such as `RenderTransform.Children[1].Angle`.</span></span>

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a><span data-ttu-id="6a06f-220">コード内の PropertyPath</span><span class="sxs-lookup"><span data-stu-id="6a06f-220">PropertyPath in Code</span></span>

<span data-ttu-id="6a06f-221">コードの使用量<xref:System.Windows.PropertyPath>、構築する方法など、<xref:System.Windows.PropertyPath>のリファレンス トピックに記載されています<xref:System.Windows.PropertyPath>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-221">Code usage for <xref:System.Windows.PropertyPath>, including how to construct a <xref:System.Windows.PropertyPath>, is documented in the reference topic for <xref:System.Windows.PropertyPath>.</span></span>

<span data-ttu-id="6a06f-222">一般に、<xref:System.Windows.PropertyPath>バインディングでの使用と最も単純なアニメーションと複雑なアニメーションでの使用の 2 つの異なるコンス トラクターを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6a06f-222">In general, <xref:System.Windows.PropertyPath> is designed to use two different constructors, one for the binding usages and simplest animation usages, and one for the complex animation usages.</span></span> <span data-ttu-id="6a06f-223">使用して、<xref:System.Windows.PropertyPath.%23ctor%28System.Object%29>オブジェクトが文字列の使用状況をバインドするための署名。</span><span class="sxs-lookup"><span data-stu-id="6a06f-223">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> signature for binding usages, where the object is a string.</span></span> <span data-ttu-id="6a06f-224">使用して、<xref:System.Windows.PropertyPath.%23ctor%28System.Object%29>ワンステップ アニメーション パスでオブジェクトが署名、<xref:System.Windows.DependencyProperty>します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-224">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> signature for one-step animation paths, where the object is a <xref:System.Windows.DependencyProperty>.</span></span> <span data-ttu-id="6a06f-225">使用して、<xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29>複雑なアニメーションの署名。</span><span class="sxs-lookup"><span data-stu-id="6a06f-225">Use the <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> signature for complex animations.</span></span> <span data-ttu-id="6a06f-226">後者のコンストラクターでは、先頭のパラメーター用のトークン文字列と、トークン文字列内の位置に設定されるオブジェクトの配列を使用して、プロパティ パスのリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="6a06f-226">This latter constructor uses a token string for the first parameter and an array of objects that fill positions in the token string to define a property path relationship.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a06f-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a06f-227">See also</span></span>

- <xref:System.Windows.PropertyPath>
- [<span data-ttu-id="6a06f-228">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="6a06f-228">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="6a06f-229">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="6a06f-229">Storyboards Overview</span></span>](../graphics-multimedia/storyboards-overview.md)
