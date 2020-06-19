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
ms.openlocfilehash: f86b7000b97bbc1287347947a9244c24a7de74c2
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141139"
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="71c39-102">ComponentResourceKey マークアップ拡張機能</span><span class="sxs-lookup"><span data-stu-id="71c39-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="71c39-103">外部アセンブリから読み込まれるリソースのキーを定義して参照します。</span><span class="sxs-lookup"><span data-stu-id="71c39-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="71c39-104">これにより、リソース検索では、アセンブリ内の明示的なリソース ディクショナリやクラスではなく、アセンブリ内の対象の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71c39-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="71c39-105">XAML 属性の使用方法 (キーの設定、コンパクト)</span><span class="sxs-lookup"><span data-stu-id="71c39-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="71c39-106">XAML 属性の使用方法 (キーの設定、詳細)</span><span class="sxs-lookup"><span data-stu-id="71c39-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="71c39-107">XAML 属性の使用方法 (リソースの要求、コンパクト)</span><span class="sxs-lookup"><span data-stu-id="71c39-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="71c39-108">XAML 属性の使用方法 (リソースの要求、詳細)</span><span class="sxs-lookup"><span data-stu-id="71c39-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" ... />  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="71c39-109">XAML 値</span><span class="sxs-lookup"><span data-stu-id="71c39-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="71c39-110">リソース アセンブリで定義されているパブリック共通言語ランタイム (CLR) 型の名前。</span><span class="sxs-lookup"><span data-stu-id="71c39-110">The name of the public common language runtime (CLR) type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="71c39-111">リソースのキー。</span><span class="sxs-lookup"><span data-stu-id="71c39-111">The key for the resource.</span></span> <span data-ttu-id="71c39-112">リソースを検索すとき、`targetID` はリソースの [x:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)に似ています。</span><span class="sxs-lookup"><span data-stu-id="71c39-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71c39-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="71c39-113">Remarks</span></span>  
 <span data-ttu-id="71c39-114">上記の使用方法で示されているように、{`ComponentResourceKey`} マークアップ拡張は次の 2 つの場所で使用されています。</span><span class="sxs-lookup"><span data-stu-id="71c39-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
- <span data-ttu-id="71c39-115">コントロールの作成者によって提供される、テーマ リソース ディクショナリ内のキーの定義。</span><span class="sxs-lookup"><span data-stu-id="71c39-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
- <span data-ttu-id="71c39-116">コントロールを再テンプレート化するが、コントロールのテーマによって提供されるリソースのプロパティ値を使用したい場合の、アセンブリのテーマ リソースへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="71c39-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="71c39-117">テーマのコンポーネント リソースを参照する場合は、通常、`{StaticResource}` ではなく `{DynamicResource}` を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71c39-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="71c39-118">これは、使用方法で示されています。</span><span class="sxs-lookup"><span data-stu-id="71c39-118">This is shown in the usages.</span></span> <span data-ttu-id="71c39-119">`{DynamicResource}` が推奨されるのは、テーマ自体がユーザーによって変更される場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="71c39-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="71c39-120">コントロールの作成者が意図するテーマのサポートに最も近いコンポーネント リソースが必要な場合は、コンポーネントのリソース参照を動的にできる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="71c39-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="71c39-121"><xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> では、リソースが実際に定義されているターゲット アセンブリに存在する型が示されてます。</span><span class="sxs-lookup"><span data-stu-id="71c39-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="71c39-122">`ComponentResourceKey` は、<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> が定義されている場所の正確な情報とは関係なく定義および使用できますが、最終的には参照されているアセンブリを使用して型を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c39-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="71c39-123"><xref:System.Windows.ComponentResourceKey> の一般的な使用方法は、そのときにクラスのメンバーとして公開されるキーを定義することです。</span><span class="sxs-lookup"><span data-stu-id="71c39-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="71c39-124">この使用方法では、マークアップ拡張ではなく <xref:System.Windows.ComponentResourceKey> クラスのコンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="71c39-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="71c39-125">詳細については、<xref:System.Windows.ComponentResourceKey> に関する記事、または「[コントロールの作成の概要](../controls/control-authoring-overview.md)」の「テーマ リソース用のキーの定義と参照」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c39-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="71c39-126">キーの設定とキー付きリソースの参照の両方で、通常は、属性構文が `ComponentResourceKey` マークアップ拡張に使用されます。</span><span class="sxs-lookup"><span data-stu-id="71c39-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="71c39-127">示されているコンパクト構文は、<xref:System.Windows.ComponentResourceKey.%23ctor%2A> コンストラクターのシグネチャと、マークアップ拡張の位置指定パラメーターの使用に依存しています。</span><span class="sxs-lookup"><span data-stu-id="71c39-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="71c39-128">`targetTypeName` と `targetID` を指定する順序が重要です。</span><span class="sxs-lookup"><span data-stu-id="71c39-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="71c39-129">詳細構文は、<xref:System.Windows.ComponentResourceKey.%23ctor%2A> のパラメーターなしのコンストラクターに依存し、オブジェクト要素の真の属性構文に似た方法で <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> と <xref:System.Windows.ComponentResourceKey.ResourceId%2A> が設定されます。</span><span class="sxs-lookup"><span data-stu-id="71c39-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> parameterless constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="71c39-130">詳細構文では、プロパティが設定される順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="71c39-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="71c39-131">これら 2 つの代替手段 (コンパクトと詳細) の関係とメカニズムについては、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」で詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="71c39-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="71c39-132">技術的には、`targetID` の値はどのようなオブジェクトでもよく、文字列である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="71c39-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="71c39-133">ただし、WPF での最も一般的な使用方法は、`targetID` の値を文字列の形式と揃えることであり、そのような文字列が [XamlName 文法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)において有効である場所です。</span><span class="sxs-lookup"><span data-stu-id="71c39-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../../desktop-wpf/xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="71c39-134">`ComponentResourceKey` は、オブジェクト要素構文で使用できます。</span><span class="sxs-lookup"><span data-stu-id="71c39-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="71c39-135">この場合、拡張機能を正しく初期化するには、<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> プロパティと <xref:System.Windows.ComponentResourceKey.ResourceId%2A> プロパティの両方の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c39-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="71c39-136">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リーダーの実装では、このマークアップ拡張の処理は <xref:System.Windows.ComponentResourceKey> クラスによって定義されています。</span><span class="sxs-lookup"><span data-stu-id="71c39-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="71c39-137">`ComponentResourceKey` はマークアップ拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="71c39-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="71c39-138">一般にマークアップ拡張機能を実装するのは、属性値をリテラル値やハンドラー名以外にエスケープする要件が存在し、その要件の適用範囲がグローバルで、特定の型やプロパティに型コンバーターを適用するだけにとどまらない場合です。</span><span class="sxs-lookup"><span data-stu-id="71c39-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="71c39-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のすべてのマークアップ拡張では、それぞれの属性構文で { と } の 2 つの記号が使用されます。これは規約であり、これに従って [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] プロセッサでは、マークアップ拡張で属性を処理する必要があることが認識されます。</span><span class="sxs-lookup"><span data-stu-id="71c39-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="71c39-140">詳細については、「[マークアップ拡張機能と WPF XAML](markup-extensions-and-wpf-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71c39-140">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c39-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="71c39-141">See also</span></span>

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="71c39-142">コントロールの作成の概要</span><span class="sxs-lookup"><span data-stu-id="71c39-142">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
- [<span data-ttu-id="71c39-143">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="71c39-143">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="71c39-144">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="71c39-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
