---
title: ComponentResourceKey マークアップ拡張機能
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 85e6862d59284df1b51bf5ea7fbba786fe0492d7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458966"
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="69438-102">ComponentResourceKey マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="69438-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="69438-103">外部アセンブリから読み込まれるリソースのキーを定義して参照します。</span><span class="sxs-lookup"><span data-stu-id="69438-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="69438-104">これにより、リソース検索では、アセンブリ内の明示的なリソースディクショナリやクラスではなく、アセンブリ内の対象の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="69438-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="69438-105">XAML 属性の使用法 (キーの設定、コンパクト)</span><span class="sxs-lookup"><span data-stu-id="69438-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="69438-106">XAML 属性の使用法 (キーの設定、詳細)</span><span class="sxs-lookup"><span data-stu-id="69438-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="69438-107">XAML 属性の使用法 (要求元のリソース、コンパクト)</span><span class="sxs-lookup"><span data-stu-id="69438-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="69438-108">XAML 属性の使用法 (要求元のリソース、詳細)</span><span class="sxs-lookup"><span data-stu-id="69438-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="69438-109">XAML 値</span><span class="sxs-lookup"><span data-stu-id="69438-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="69438-110">リソースアセンブリで定義されているパブリック共通言語ランタイム (CLR) 型の名前。</span><span class="sxs-lookup"><span data-stu-id="69438-110">The name of the public common language runtime (CLR) type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="69438-111">リソースのキー。</span><span class="sxs-lookup"><span data-stu-id="69438-111">The key for the resource.</span></span> <span data-ttu-id="69438-112">リソースが検索されると、`targetID` はリソースの[X:Key ディレクティブ](../../xaml-services/x-key-directive.md)に似ています。</span><span class="sxs-lookup"><span data-stu-id="69438-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../xaml-services/x-key-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69438-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="69438-113">Remarks</span></span>  
 <span data-ttu-id="69438-114">上記の使用状況に示されているように、{`ComponentResourceKey`} マークアップ拡張機能の使用方法は次の2つの場所にあります。</span><span class="sxs-lookup"><span data-stu-id="69438-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
- <span data-ttu-id="69438-115">コントロールの作成者によって提供される、テーマリソースディクショナリ内のキーの定義。</span><span class="sxs-lookup"><span data-stu-id="69438-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
- <span data-ttu-id="69438-116">コントロールをテンプレートするときに、コントロールのテーマによって提供されるリソースからのプロパティ値を使用する場合に、アセンブリからテーマリソースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="69438-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="69438-117">テーマに由来するコンポーネントリソースを参照する場合は、通常、`{StaticResource}`ではなく `{DynamicResource}` を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69438-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="69438-118">これは、使用法で示されています。</span><span class="sxs-lookup"><span data-stu-id="69438-118">This is shown in the usages.</span></span> <span data-ttu-id="69438-119">テーマ自体はユーザーが変更できるため、`{DynamicResource}` をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69438-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="69438-120">テーマをサポートするために、コントロールの作成者の意図に最も近いコンポーネントリソースが必要な場合は、コンポーネントのリソース参照も動的にできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69438-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="69438-121"><xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> は、リソースが実際に定義されているターゲットアセンブリに存在する型を識別します。</span><span class="sxs-lookup"><span data-stu-id="69438-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="69438-122">`ComponentResourceKey` は、<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> が定義されている場所を正確に把握することとは別に定義および使用できますが、最終的には参照されたアセンブリを使用して型を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69438-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="69438-123"><xref:System.Windows.ComponentResourceKey> の一般的な使用方法は、クラスのメンバーとして公開されるキーを定義することです。</span><span class="sxs-lookup"><span data-stu-id="69438-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="69438-124">この使用法では、マークアップ拡張機能ではなく <xref:System.Windows.ComponentResourceKey> クラスコンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="69438-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="69438-125">詳細については、「[コントロールの作成の概要](../controls/control-authoring-overview.md)」の「<xref:System.Windows.ComponentResourceKey>」または「テーマリソースのキーの定義と参照」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69438-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="69438-126">キーの確立とキー付きリソースの参照の両方について、属性構文は、通常、`ComponentResourceKey` マークアップ拡張機能で使用されます。</span><span class="sxs-lookup"><span data-stu-id="69438-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="69438-127">ここに示すコンパクトな構文は、マークアップ拡張機能の <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> コンストラクターシグネチャと位置指定パラメーターの使用に依存しています。</span><span class="sxs-lookup"><span data-stu-id="69438-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="69438-128">`targetTypeName` と `targetID` を指定する順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="69438-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="69438-129">Verbose 構文は <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> パラメーターなしのコンストラクターに依存し、オブジェクト要素の真の属性構文に似た方法で <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> と <xref:System.Windows.ComponentResourceKey.ResourceId%2A> を設定します。</span><span class="sxs-lookup"><span data-stu-id="69438-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> parameterless constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="69438-130">Verbose 構文では、プロパティが設定される順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="69438-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="69438-131">この2つの代替手段 (compact および verbose) の関係とメカニズムについては、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」で詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="69438-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="69438-132">技術的には、`targetID` の値は任意のオブジェクトにすることができ、文字列である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69438-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="69438-133">ただし、WPF で最も一般的に使用されるのは、`targetID` 値を文字列であるフォームに揃え、そのような文字列を[XamlName 文法](../../xaml-services/xamlname-grammar.md)で有効にすることです。</span><span class="sxs-lookup"><span data-stu-id="69438-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="69438-134">`ComponentResourceKey` は、オブジェクト要素構文で使用できます。</span><span class="sxs-lookup"><span data-stu-id="69438-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="69438-135">この場合、拡張機能を正しく初期化するには、<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> プロパティと <xref:System.Windows.ComponentResourceKey.ResourceId%2A> プロパティの両方の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69438-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="69438-136">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リーダーの実装では、このマークアップ拡張機能の処理は <xref:System.Windows.ComponentResourceKey> クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="69438-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="69438-137">`ComponentResourceKey` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="69438-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="69438-138">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="69438-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="69438-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 内のすべてのマークアップ拡張機能は、属性構文で {および} 文字を使用します。これは、マークアップ拡張機能が属性を処理する必要があることを [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサが認識する規則です。</span><span class="sxs-lookup"><span data-stu-id="69438-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="69438-140">詳細については、「[マークアップ拡張機能」および「WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69438-140">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69438-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="69438-141">See also</span></span>

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="69438-142">コントロールの作成の概要</span><span class="sxs-lookup"><span data-stu-id="69438-142">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
- [<span data-ttu-id="69438-143">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="69438-143">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="69438-144">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="69438-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
