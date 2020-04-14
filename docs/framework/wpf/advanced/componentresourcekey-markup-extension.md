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
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243363"
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="2758a-102">ComponentResourceKey マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="2758a-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="2758a-103">外部アセンブリから読み込まれるリソースのキーを定義および参照します。</span><span class="sxs-lookup"><span data-stu-id="2758a-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="2758a-104">これにより、アセンブリまたはクラスで明示的なリソース ディクショナリではなく、アセンブリ内のターゲット型を指定するリソースルックアップが可能になります。</span><span class="sxs-lookup"><span data-stu-id="2758a-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="2758a-105">XAML 属性の使用 (設定キー、コンパクト)</span><span class="sxs-lookup"><span data-stu-id="2758a-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="2758a-106">XAML 属性の使用 (キー、詳細な設定)</span><span class="sxs-lookup"><span data-stu-id="2758a-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="2758a-107">XAML 属性の使用 (リソースの要求、コンパクト)</span><span class="sxs-lookup"><span data-stu-id="2758a-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="2758a-108">XAML 属性の使用 (リソースの要求、詳細)</span><span class="sxs-lookup"><span data-stu-id="2758a-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2758a-109">XAML 値</span><span class="sxs-lookup"><span data-stu-id="2758a-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="2758a-110">リソース アセンブリで定義されているパブリック共通言語ランタイム (CLR) 型の名前。</span><span class="sxs-lookup"><span data-stu-id="2758a-110">The name of the public common language runtime (CLR) type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="2758a-111">リソースのキー。</span><span class="sxs-lookup"><span data-stu-id="2758a-111">The key for the resource.</span></span> <span data-ttu-id="2758a-112">リソースを検索すると、`targetID`リソースの[x:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)に類似します。</span><span class="sxs-lookup"><span data-stu-id="2758a-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2758a-113">解説</span><span class="sxs-lookup"><span data-stu-id="2758a-113">Remarks</span></span>  
 <span data-ttu-id="2758a-114">上記の使用方法で見られるように、 {`ComponentResourceKey`} マークアップ拡張機能の使用は 2 箇所にあります。</span><span class="sxs-lookup"><span data-stu-id="2758a-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
- <span data-ttu-id="2758a-115">コントロールの作成者が提供する、テーマ リソース ディクショナリ内のキーの定義。</span><span class="sxs-lookup"><span data-stu-id="2758a-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
- <span data-ttu-id="2758a-116">コントロールを再設定するが、コントロールのテーマによって提供されるリソースから取得したプロパティ値を使用する場合は、アセンブリからテーマ リソースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2758a-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="2758a-117">テーマから取得したコンポーネント リソースを参照する場合は、通常、 ではなく`{DynamicResource}``{StaticResource}`を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2758a-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="2758a-118">これは、使用方法に示されています。</span><span class="sxs-lookup"><span data-stu-id="2758a-118">This is shown in the usages.</span></span> <span data-ttu-id="2758a-119">`{DynamicResource}`テーマ自体はユーザーが変更できるため、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="2758a-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="2758a-120">テーマをサポートするコントロール作成者の意図に最も近いコンポーネント リソースを使用する場合は、コンポーネント リソース参照も動的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2758a-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="2758a-121">リソース<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>が実際に定義されているターゲット アセンブリに存在する型を識別します。</span><span class="sxs-lookup"><span data-stu-id="2758a-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="2758a-122">を`ComponentResourceKey`定義し、定義<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>されている場所を正確に知ることとは別に使用できますが、最終的には参照アセンブリを通じて型を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2758a-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="2758a-123">一般的な<xref:System.Windows.ComponentResourceKey>用途は、クラスのメンバーとして公開されるキーを定義することです。</span><span class="sxs-lookup"><span data-stu-id="2758a-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="2758a-124">この使用法では、マークアップ拡張機能<xref:System.Windows.ComponentResourceKey>ではなくクラス コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2758a-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="2758a-125">詳細については、「 」<xref:System.Windows.ComponentResourceKey>または トピック「[コントロールオーサリングの概要](../controls/control-authoring-overview.md)」の「テーマリソースのキーの定義と参照」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2758a-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="2758a-126">キーの確立とキー付きリソースの参照の両方で、属性構文は通常、`ComponentResourceKey`マークアップ拡張機能に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2758a-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="2758a-127">この compact 構文は、コンストラクター<xref:System.Windows.ComponentResourceKey.%23ctor%2A>シグネチャとマークアップ拡張機能の位置指定パラメーターの使用法に依存しています。</span><span class="sxs-lookup"><span data-stu-id="2758a-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="2758a-128">と`targetTypeName``targetID`が与えられる順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="2758a-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="2758a-129">詳細な構文は、パラメーターなしの<xref:System.Windows.ComponentResourceKey.%23ctor%2A>コンストラクターに依存し、オブジェクト要素の真<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>の<xref:System.Windows.ComponentResourceKey.ResourceId%2A>属性構文に類似した方法で and を設定します。</span><span class="sxs-lookup"><span data-stu-id="2758a-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> parameterless constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="2758a-130">詳細な構文では、プロパティが設定される順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2758a-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="2758a-131">これら 2 つの代替手段 (コンパクトと詳細) の関係とメカニズムについては、「[マークアップ拡張機能と WPF XAML」](markup-extensions-and-wpf-xaml.md)のトピックで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2758a-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="2758a-132">技術的には、値は`targetID`任意のオブジェクトにすることができ、文字列である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2758a-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="2758a-133">ただし、WPFWPF で最もよく使用される使用方法は`targetID`、値を文字列で配置し、XamlName[の文法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)でこのような文字列が有効な場所に配置することです。</span><span class="sxs-lookup"><span data-stu-id="2758a-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../../desktop-wpf/xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="2758a-134">`ComponentResourceKey`オブジェクト要素構文で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2758a-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="2758a-135">この場合、拡張機能を適切に初期化するには<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>、 および<xref:System.Windows.ComponentResourceKey.ResourceId%2A>プロパティの両方の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2758a-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="2758a-136">リーダーの[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]実装では、このマークアップ拡張機能の処理は、クラスによって定義されます<xref:System.Windows.ComponentResourceKey>。</span><span class="sxs-lookup"><span data-stu-id="2758a-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="2758a-137">`ComponentResourceKey` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="2758a-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="2758a-138">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="2758a-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="2758a-139">すべてのマークアップ拡張機能は[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]、属性構文で { と } 文字を使用します[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2758a-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="2758a-140">詳細については、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2758a-140">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2758a-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="2758a-141">See also</span></span>

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2758a-142">コントロールの作成の概要</span><span class="sxs-lookup"><span data-stu-id="2758a-142">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
- [<span data-ttu-id="2758a-143">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="2758a-143">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="2758a-144">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="2758a-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
