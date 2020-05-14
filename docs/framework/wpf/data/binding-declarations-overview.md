---
title: バインディング宣言の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
ms.openlocfilehash: 8fea61c463928ee69ef5dd0dfbf107f89c5384ff
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544466"
---
# <a name="binding-declarations-overview"></a><span data-ttu-id="3b5f3-102">バインディング宣言の概要</span><span class="sxs-lookup"><span data-stu-id="3b5f3-102">Binding Declarations Overview</span></span>

<span data-ttu-id="3b5f3-103">このトピックでは、バインディングを宣言するさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-103">This topic discusses the different ways you can declare a binding.</span></span>

<a name="Prereq"></a>

## <a name="prerequisites"></a><span data-ttu-id="3b5f3-104">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3b5f3-104">Prerequisites</span></span>

<span data-ttu-id="3b5f3-105">このトピックを読む前に、マークアップ拡張機能の概念と使用方法について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-105">Before reading this topic, it is important that you are familiar with the concept and usage of markup extensions.</span></span> <span data-ttu-id="3b5f3-106">マークアップ拡張機能の詳細については、 「[マークアップ拡張機能と WPF XAML](../advanced/markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-106">For more information about markup extensions, see [Markup Extensions and WPF XAML](../advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="3b5f3-107">このトピックでは、データ バインディングの概念については説明しません。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-107">This topic does not cover data binding concepts.</span></span> <span data-ttu-id="3b5f3-108">データ バインディングの概念の詳細については、「[Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-108">For a discussion of data binding concepts, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<a name="BindinginXAML"></a>

## <a name="declaring-a-binding-in-xaml"></a><span data-ttu-id="3b5f3-109">XAML でのバインディングの宣言</span><span class="sxs-lookup"><span data-stu-id="3b5f3-109">Declaring a Binding in XAML</span></span>

<span data-ttu-id="3b5f3-110">このセクションでは、XAML でバインディングを宣言する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-110">This section discusses how to declare a binding in XAML.</span></span>

<a name="MarkupExtensionSyntax"></a>

### <a name="markup-extension-usage"></a><span data-ttu-id="3b5f3-111">マークアップ拡張機能の使用方法</span><span class="sxs-lookup"><span data-stu-id="3b5f3-111">Markup Extension Usage</span></span>

<span data-ttu-id="3b5f3-112"><xref:System.Windows.Data.Binding> はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-112"><xref:System.Windows.Data.Binding> is a markup extension.</span></span> <span data-ttu-id="3b5f3-113">バインディング拡張機能を使用してバインディングを宣言するとき、この宣言は、`Binding` キーワードに続く一連の句で構成され、コンマ (,) で区切られます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-113">When you use the binding extension to declare a binding, the declaration consists of a series of clauses following the `Binding` keyword and separated by commas (,).</span></span> <span data-ttu-id="3b5f3-114">バインディング宣言内の句の順序は任意で、多数の組み合わせが可能です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-114">The clauses in the binding declaration can be in any order and there are many possible combinations.</span></span> <span data-ttu-id="3b5f3-115">句は*名前*=*値*のペアで、"*名前*" は <xref:System.Windows.Data.Binding> プロパティの名前、"*値*" はこのプロパティに設定する値です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-115">The clauses are *Name*=*Value* pairs where *Name* is the name of the <xref:System.Windows.Data.Binding> property and *Value* is the value you are setting for the property.</span></span>

<span data-ttu-id="3b5f3-116">マークアップでバインディング宣言文字列を作成する場合、この文字列はターゲット オブジェクトの特定の依存関係プロパティにアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-116">When creating binding declaration strings in markup, they must be attached to the specific dependency property of a target object.</span></span> <span data-ttu-id="3b5f3-117">次の例では、バインディング拡張機能を使用して <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> プロパティをバインドし、<xref:System.Windows.Data.Binding.Source%2A> プロパティと <xref:System.Windows.Data.Binding.Path%2A> プロパティを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-117">The following example shows how to bind the <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property using the binding extension, specifying the <xref:System.Windows.Data.Binding.Source%2A> and <xref:System.Windows.Data.Binding.Path%2A> properties.</span></span>

[!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]

<span data-ttu-id="3b5f3-118"><xref:System.Windows.Data.Binding> クラスのプロパティのほとんどをこの方法で指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-118">You can specify most of the properties of the <xref:System.Windows.Data.Binding> class this way.</span></span> <span data-ttu-id="3b5f3-119">バインディング拡張機能およびバインディング拡張機能を使用して設定できない <xref:System.Windows.Data.Binding> プロパティの一覧については、「[バインドのマークアップ拡張機能](../advanced/binding-markup-extension.md)」の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-119">For more information about the binding extension as well as for a list of <xref:System.Windows.Data.Binding> properties that cannot be set using the binding extension, see the [Binding Markup Extension](../advanced/binding-markup-extension.md) overview.</span></span>

<a name="ObjectElementSyntax"></a>

### <a name="object-element-syntax"></a><span data-ttu-id="3b5f3-120">オブジェクト要素構文</span><span class="sxs-lookup"><span data-stu-id="3b5f3-120">Object Element Syntax</span></span>

<span data-ttu-id="3b5f3-121">オブジェクト要素構文は、バインディング宣言を作成する代替の方法です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-121">Object element syntax is an alternative to creating the binding declaration.</span></span> <span data-ttu-id="3b5f3-122">ほとんどの場合は、マークアップ拡張機能の使用とオブジェクト要素構文の使用のどちらにも特別な利点はありません。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-122">In most cases, there is no particular advantage to using either the markup extension or the object element syntax.</span></span> <span data-ttu-id="3b5f3-123">ただし、マークアップ拡張機能がサポートしないシナリオでは (プロパティ値が文字列タイプではなく、このタイプの変換が存在しない場合)、オブジェクト要素構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-123">However, in cases which the markup extension does not support your scenario, such as when your property value is of a non-string type for which no type conversion exists, you need to use the object element syntax.</span></span>

<span data-ttu-id="3b5f3-124">オブジェクト要素構文とマークアップ拡張機能の使用の両方の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-124">The following is an example of both the object element syntax and the markup extension usage:</span></span>

[!code-xaml[BindConversionMarkup#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]

<span data-ttu-id="3b5f3-125">この例では、拡張構文を使用してバインディングを宣言することによって <xref:System.Windows.Controls.TextBlock.Foreground%2A> プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-125">The example binds the <xref:System.Windows.Controls.TextBlock.Foreground%2A> property by declaring a binding using the extension syntax.</span></span> <span data-ttu-id="3b5f3-126"><xref:System.Windows.Controls.TextBlock.Text%2A> プロパティのバインディング宣言では、オブジェクト要素構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-126">The binding declaration for the <xref:System.Windows.Controls.TextBlock.Text%2A> property uses the object element syntax.</span></span>

<span data-ttu-id="3b5f3-127">別の用語の詳細については、「[XAML Syntax の詳細](../advanced/xaml-syntax-in-detail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-127">For more information about the different terms, see [XAML Syntax In Detail](../advanced/xaml-syntax-in-detail.md).</span></span>

<a name="MBandPB"></a>

### <a name="multibinding-and-prioritybinding"></a><span data-ttu-id="3b5f3-128">MultiBinding と PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="3b5f3-128">MultiBinding and PriorityBinding</span></span>

<span data-ttu-id="3b5f3-129"><xref:System.Windows.Data.MultiBinding> と <xref:System.Windows.Data.PriorityBinding> では、XAML 拡張構文はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-129"><xref:System.Windows.Data.MultiBinding> and <xref:System.Windows.Data.PriorityBinding> do not support the XAML extension syntax.</span></span> <span data-ttu-id="3b5f3-130">したがって、XAML で <xref:System.Windows.Data.MultiBinding> または <xref:System.Windows.Data.PriorityBinding> を宣言する場合は、オブジェクト要素構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-130">Therefore, you must use the object element syntax if you are declaring a <xref:System.Windows.Data.MultiBinding> or a <xref:System.Windows.Data.PriorityBinding> in XAML.</span></span>

<a name="BindinginCode"></a>

## <a name="creating-a-binding-in-code"></a><span data-ttu-id="3b5f3-131">コードでバインディングを作成する方法</span><span class="sxs-lookup"><span data-stu-id="3b5f3-131">Creating a Binding in Code</span></span>

<span data-ttu-id="3b5f3-132">バインディングを指定する別の方法は、コードで <xref:System.Windows.Data.Binding> オブジェクトにプロパティを直接設定する方法です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-132">Another way to specify a binding is to set properties directly on a <xref:System.Windows.Data.Binding> object in code.</span></span> <span data-ttu-id="3b5f3-133">次の例では、<xref:System.Windows.Data.Binding> オブジェクトを作成し、コードでプロパティを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-133">The following example shows how to create a <xref:System.Windows.Data.Binding> object and specify the properties in code.</span></span>  <span data-ttu-id="3b5f3-134">この例では、`TheConverter` は <xref:System.Windows.Data.IValueConverter> インターフェイスを実装するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-134">In this example, `TheConverter` is an object that implements the <xref:System.Windows.Data.IValueConverter> interface.</span></span>

[!code-csharp[BindConversion#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
[!code-vb[BindConversion#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]

<span data-ttu-id="3b5f3-135">バインディングしているオブジェクトが <xref:System.Windows.FrameworkElement> または <xref:System.Windows.FrameworkContentElement> の場合、<xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> を使用する代わりに、オブジェクトで `SetBinding` メソッドを直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-135">If the object you are binding is a <xref:System.Windows.FrameworkElement> or a <xref:System.Windows.FrameworkContentElement> you can call the `SetBinding` method on your object directly instead of using <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3b5f3-136">例については、「[Create a Binding in Code](how-to-create-a-binding-in-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-136">For an example, see [Create a Binding in Code](how-to-create-a-binding-in-code.md).</span></span>

<a name="Path_Syntax"></a>

## <a name="binding-path-syntax"></a><span data-ttu-id="3b5f3-137">バインディング パス構文</span><span class="sxs-lookup"><span data-stu-id="3b5f3-137">Binding Path Syntax</span></span>

<span data-ttu-id="3b5f3-138"><xref:System.Windows.Data.Binding.Path%2A> プロパティを使用して、バインドするソース値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-138">Use the <xref:System.Windows.Data.Binding.Path%2A> property to specify the source value you want to bind to:</span></span>

- <span data-ttu-id="3b5f3-139">最も簡単なケースでは、<xref:System.Windows.Data.Binding.Path%2A> プロパティの値は、バインディングに使用するソース オブジェクトのプロパティの名前です (`Path=PropertyName` など)。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-139">In the simplest case, the <xref:System.Windows.Data.Binding.Path%2A> property value is the name of the property of the source object to use for the binding, such as `Path=PropertyName`.</span></span>

- <span data-ttu-id="3b5f3-140">プロパティのサブプロパティは、C# と同様の構文で指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-140">Subproperties of a property can be specified by a similar syntax as in C#.</span></span> <span data-ttu-id="3b5f3-141">たとえば、句 `Path=ShoppingCart.Order` は、バインディングをオブジェクトのサブプロパティ `Order` またはプロパティ `ShoppingCart` に設定します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-141">For instance, the clause `Path=ShoppingCart.Order` sets the binding to the subproperty `Order` of the object or property `ShoppingCart`.</span></span>

- <span data-ttu-id="3b5f3-142">添付プロパティにバインドするには、添付プロパティをかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-142">To bind to an attached property, place parentheses around the attached property.</span></span> <span data-ttu-id="3b5f3-143">たとえば、添付プロパティ <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> にバインドする構文は `Path=(DockPanel.Dock)` です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-143">For example, to bind to the attached property <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, the syntax is `Path=(DockPanel.Dock)`.</span></span>

- <span data-ttu-id="3b5f3-144">プロパティのインデクサーは、インデクサーが適用されているプロパティ名の後ろの角かっこ内に指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-144">Indexers of a property can be specified within square brackets following the property name where the indexer is applied.</span></span> <span data-ttu-id="3b5f3-145">たとえば、句 `Path=ShoppingCart[0]` は、プロパティの内部インデックスがリテラル文字列「0」を処理する方法に対応するインデックスへのバインディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-145">For instance, the clause `Path=ShoppingCart[0]` sets the binding to the index that corresponds to how your property's internal indexing handles the literal string "0".</span></span> <span data-ttu-id="3b5f3-146">入れ子になったインデクサーもサポートします。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-146">Nested indexers are also supported.</span></span>

- <span data-ttu-id="3b5f3-147">`Path` 句ではインデクサーとサブプロパティを混在させることができます。例: `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`</span><span class="sxs-lookup"><span data-stu-id="3b5f3-147">Indexers and subproperties can be mixed in a `Path` clause; for example, `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`</span></span>

- <span data-ttu-id="3b5f3-148">インデクサー内では、コンマ (,) で区切って複数のインデクサー パラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-148">Inside indexers you can have multiple indexer parameters separated by commas (,).</span></span> <span data-ttu-id="3b5f3-149">各パラメーターの型は、かっこで指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-149">The type of each parameter can be specified with parentheses.</span></span> <span data-ttu-id="3b5f3-150">たとえば、`Path="[(sys:Int32)42,(sys:Int32)24]"` などと指定できます。この場合、`sys` は `System` 名前空間にマップされます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-150">For example, you can have `Path="[(sys:Int32)42,(sys:Int32)24]"`, where `sys` is mapped to the `System` namespace.</span></span>

- <span data-ttu-id="3b5f3-151">ソースがコレクション ビューの場合は、現在の項目をスラッシュ (/) で指定できます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-151">When the source is a collection view, the current item can be specified with a slash (/).</span></span> <span data-ttu-id="3b5f3-152">たとえば、句 `Path=/` では、ビューの現在の項目に対するバインディングが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-152">For example, the clause `Path=/` sets the binding to the current item in the view.</span></span> <span data-ttu-id="3b5f3-153">ソースがコレクションの場合、この構文では、既定のコレクション ビューの現在の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-153">When the source is a collection, this syntax specifies the current item of the default collection view.</span></span>

- <span data-ttu-id="3b5f3-154">プロパティ名とスラッシュを組み合わせて、コレクションであるプロパティを走査することができます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-154">Property names and slashes can be combined to traverse properties that are collections.</span></span> <span data-ttu-id="3b5f3-155">たとえば、`Path=/Offices/ManagerName` では、それもコレクションである `Offices` プロパティが含まれるソース コレクションの現在の項目が指定されます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-155">For example, `Path=/Offices/ManagerName` specifies the current item of the source collection, which contains an `Offices` property that is also a collection.</span></span> <span data-ttu-id="3b5f3-156">現在の項目は、`ManagerName` プロパティを含むオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-156">Its current item is an object that contains a `ManagerName` property.</span></span>

- <span data-ttu-id="3b5f3-157">必要に応じて、ピリオド (.) のパスを使用して、現在のソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-157">Optionally, a period (.) path can be used to bind to the current source.</span></span> <span data-ttu-id="3b5f3-158">たとえば、`Text="{Binding}"` は、`Text="{Binding Path=.}"` と同じです。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-158">For example, `Text="{Binding}"` is equivalent to `Text="{Binding Path=.}"`.</span></span>

### <a name="escaping-mechanism"></a><span data-ttu-id="3b5f3-159">エスケープのしくみ</span><span class="sxs-lookup"><span data-stu-id="3b5f3-159">Escaping Mechanism</span></span>

- <span data-ttu-id="3b5f3-160">インデクサー ([ ]) 内では、キャレット文字 (^) は次の文字をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-160">Inside indexers ([ ]), the caret character (^) escapes the next character.</span></span>

- <span data-ttu-id="3b5f3-161">XAML で <xref:System.Windows.Data.Binding.Path%2A> を設定した場合、XML 言語定義で特別な意味を持つ特定の文字も (XML エンティティを使用して) エスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-161">If you set <xref:System.Windows.Data.Binding.Path%2A> in XAML, you also need to escape (using XML entities) certain characters that are special to the XML language definition:</span></span>

  - <span data-ttu-id="3b5f3-162">文字 "&" をエスケープするには、`&amp;` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-162">Use `&amp;` to escape the character "&".</span></span>

  - <span data-ttu-id="3b5f3-163">使用する`&gt;`終了タグをエスケープする">"です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-163">Use `&gt;` to escape the end tag ">".</span></span>

- <span data-ttu-id="3b5f3-164">さらに、マークアップ拡張構文を使用して属性のバインディング全体を記述する場合、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] マークアップ拡張機能パーサーで特別な意味を持つ文字を (円記号 \\ を使用して) エスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-164">Additionally, if you describe the entire binding in an attribute using the markup extension syntax, you need to escape (using backslash \\) characters that are special to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] markup extension parser:</span></span>

  - <span data-ttu-id="3b5f3-165">円記号 (\\) はエスケープ文字そのものです。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-165">Backslash (\\) is the escape character itself.</span></span>

  - <span data-ttu-id="3b5f3-166">等号 (=) は、プロパティ名とプロパティの値を区切ります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-166">The equal sign (=) separates property name from property value.</span></span>

  - <span data-ttu-id="3b5f3-167">コンマ (,) はプロパティを区切ります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-167">Comma (,) separates properties.</span></span>

  - <span data-ttu-id="3b5f3-168">右中かっこ (}) は、マークアップ拡張機能の終わりです。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-168">The right curly brace (}) is the end of a markup extension.</span></span>

<a name="Default"></a>

## <a name="default-behaviors"></a><span data-ttu-id="3b5f3-169">既定の動作</span><span class="sxs-lookup"><span data-stu-id="3b5f3-169">Default Behaviors</span></span>

<span data-ttu-id="3b5f3-170">既定の動作は、宣言で指定されていない場合には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-170">The default behavior is as follows if not specified in the declaration.</span></span>

- <span data-ttu-id="3b5f3-171">バインディング ソースの値とバインディング ターゲットの値の型変換を実行しようとする既定のコンバーターが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-171">A default converter is created that tries to do a type conversion between the binding source value and the binding target value.</span></span> <span data-ttu-id="3b5f3-172">変換を実行できない場合、既定のコンバーターは `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-172">If a conversion cannot be made, the default converter returns `null`.</span></span>

- <span data-ttu-id="3b5f3-173"><xref:System.Windows.Data.Binding.ConverterCulture%2A> を設定しない場合、バインディング エンジンではバインディング ターゲット オブジェクトの `Language` プロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-173">If you do not set <xref:System.Windows.Data.Binding.ConverterCulture%2A>, the binding engine uses the `Language` property of the binding target object.</span></span> <span data-ttu-id="3b5f3-174">XAML では、既定で "en-US" になるか、または明示的に設定されている場合にはページのルート要素 (または任意の要素) から値を継承します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-174">In XAML, this defaults to "en-US" or inherits the value from the root element (or any element) of the page, if one has been explicitly set.</span></span>

- <span data-ttu-id="3b5f3-175">バインディングに既にデータ コンテキスト (たとえば、親要素から継承したデータ コンテキスト) があり、そのコンテキストによって返される項目またはコンテキストが何であれ、さらなるパスの変更を必要とせずにバインディングに対して適切である限り、バインディング宣言に句がまったくなくてもかまいません: `{Binding}`。これは、多くの場合、データのスタイルに対してバインディングを指定する方法で、バインディングはコレクションに基づいて動作します。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-175">As long as the binding already has a data context (for instance, the inherited data context coming from a parent element), and whatever item or collection being returned by that context is appropriate for binding without requiring further path modification, a binding declaration can have no clauses at all: `{Binding}` This is often the way a binding is specified for data styling, where the binding acts upon a collection.</span></span> <span data-ttu-id="3b5f3-176">詳細については、「[バインディング ソースの概要](binding-sources-overview.md)」の「バインディング ソースとして使用する全体オブジェクト」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-176">For more information, see the "Entire Objects Used as a Binding Source" section in the [Binding Sources Overview](binding-sources-overview.md).</span></span>

- <span data-ttu-id="3b5f3-177">既定の <xref:System.Windows.Data.Binding.Mode%2A> は、バインドされている依存関係プロパティによって一方向と双方向で異なります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-177">The default <xref:System.Windows.Data.Binding.Mode%2A> varies between one-way and two-way depending on the dependency property that is being bound.</span></span> <span data-ttu-id="3b5f3-178">常にバインディング モードを明示的に宣言し、バインディングに目的の動作があることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-178">You can always declare the binding mode explicitly to ensure that your binding has the desired behavior.</span></span> <span data-ttu-id="3b5f3-179">一般に、ユーザーが編集できる <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> や <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType> などのコントロール プロパティは既定で双方向のバインディングであり、それ以外のほとんどのプロパティは既定で一方向のバインドになります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-179">In general, user-editable control properties, such as <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, default to two-way bindings, whereas most other properties default to one-way bindings.</span></span>

- <span data-ttu-id="3b5f3-180">既定の <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 値は、バインドされている依存関係プロパティによっても <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> と <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> で異なります。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-180">The default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value varies between <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> and <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> depending on the bound dependency property as well.</span></span> <span data-ttu-id="3b5f3-181">ほとんどの依存関係プロパティの既定値は <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> です。ただし、<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> プロパティの既定値は <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> です。</span><span class="sxs-lookup"><span data-stu-id="3b5f3-181">The default value for most dependency properties is <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, while the <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property has a default value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b5f3-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b5f3-182">See also</span></span>

- [<span data-ttu-id="3b5f3-183">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="3b5f3-183">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="3b5f3-184">方法トピック</span><span class="sxs-lookup"><span data-stu-id="3b5f3-184">How-to Topics</span></span>](data-binding-how-to-topics.md)
- [<span data-ttu-id="3b5f3-185">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="3b5f3-185">Data Binding</span></span>](../advanced/optimizing-performance-data-binding.md)
- [<span data-ttu-id="3b5f3-186">PropertyPath の XAML 構文</span><span class="sxs-lookup"><span data-stu-id="3b5f3-186">PropertyPath XAML Syntax</span></span>](../advanced/propertypath-xaml-syntax.md)
