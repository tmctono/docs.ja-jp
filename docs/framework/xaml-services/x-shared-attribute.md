---
title: x:Shared 属性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: da35f209b632bdf9e4ab2298239a505df69d6048
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982632"
---
# <a name="xshared-attribute"></a><span data-ttu-id="e1911-102">x:Shared 属性</span><span class="sxs-lookup"><span data-stu-id="e1911-102">x:Shared Attribute</span></span>
<span data-ttu-id="e1911-103">設定すると`false`、属性付きのリソースの要求は、すべての要求の同じインスタンスを共有することがなく、各要求の新しいインスタンスを作成するために、WPF リソース検索の動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="e1911-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="e1911-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="e1911-104">XAML Attribute Usage</span></span>  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a><span data-ttu-id="e1911-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1911-105">Remarks</span></span>  
 <span data-ttu-id="e1911-106">`x:Shared` XAML 言語の XAML 名前空間にマップされ、.NET Framework XAML サービスおよびその XAML リーダーで有効な XAML 言語要素として認識されます。</span><span class="sxs-lookup"><span data-stu-id="e1911-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET Framework XAML Services and its XAML readers.</span></span> <span data-ttu-id="e1911-107">ただし、示された機能の`x:Shared`は WPF アプリケーションと WPF XAML パーサーに適用します。</span><span class="sxs-lookup"><span data-stu-id="e1911-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="e1911-108">WPF では、 `x:Shared` WPF 内に存在するオブジェクトに適用されたときに属性として便利なだけ<xref:System.Windows.ResourceDictionary>です。</span><span class="sxs-lookup"><span data-stu-id="e1911-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="e1911-109">その他の方法は解析例外やその他のエラーをスローしませんが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="e1911-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>  
  
 <span data-ttu-id="e1911-110">意味`x:Shared`XAML 言語仕様で指定されていません。</span><span class="sxs-lookup"><span data-stu-id="e1911-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="e1911-111">.NET Framework XAML サービスでは、上に構築されるなど、他の XAML 実装は、必ずしもリソース共有のサポートを提供しません。</span><span class="sxs-lookup"><span data-stu-id="e1911-111">Other XAML implementations, such as those that build on .NET Framework XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="e1911-112">このような XAML 実装にも使用するサポートのフレームワークで同様の動作を提供できます`x:Shared`値。</span><span class="sxs-lookup"><span data-stu-id="e1911-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>  
  
 <span data-ttu-id="e1911-113">WPF では、既定で`x:Shared`リソースの条件が`true`します。</span><span class="sxs-lookup"><span data-stu-id="e1911-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="e1911-114">この条件は、特定のリソースの要求が常に同じインスタンスを返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e1911-114">This condition means that any given resource request always returns the same instance.</span></span>  
  
 <span data-ttu-id="e1911-115">など、API のリソースから返されるオブジェクトを変更する<xref:System.Windows.FrameworkElement.FindResource%2A>、または内で直接オブジェクトを変更する、 <xref:System.Windows.ResourceDictionary>、元のリソースを変更します。</span><span class="sxs-lookup"><span data-stu-id="e1911-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="e1911-116">そのリソースへの参照は、動的リソース参照が、そのリソースのコンシューマーは変更されたリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="e1911-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>  
  
 <span data-ttu-id="e1911-117">場合、リソースへの参照は静的リソース参照、変更後にリソース[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]処理時間は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="e1911-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="e1911-118">静的および動的リソース参照の詳細については、次を参照してください。 [XAML リソース](../wpf/advanced/xaml-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1911-118">For more information about static versus dynamic resource references, see [XAML Resources](../wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="e1911-119">明示的に指定する`x:Shared="true"`はあまり一般的には、既定ではないためです。</span><span class="sxs-lookup"><span data-stu-id="e1911-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="e1911-120">同等の直接コードがない`x:Shared`WPF では、オブジェクト モデルは、処理する必要がある既定の WPF の動作をするか、読み込みパスで、中間の XAML ノード ストリームで .NET Framework XAML Se を使用して処理する場合、XAML の使用状況でのみ指定できますターゲットおよびその XAML リーダー。</span><span class="sxs-lookup"><span data-stu-id="e1911-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET Framework XAML Services and its XAML readers.</span></span>  
  
 <span data-ttu-id="e1911-121">シナリオ`x:Shared="false"`定義するかどうかは、<xref:System.Windows.FrameworkElement>または<xref:System.Windows.FrameworkContentElement>リソースとしてのクラスを派生し、コンテンツ モデルに要素のリソースを導入します。</span><span class="sxs-lookup"><span data-stu-id="e1911-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="e1911-122">`x:Shared="false"` により、複数回、同じコレクションに導入する、要素のリソース (など、 <xref:System.Windows.Controls.UIElementCollection>)。</span><span class="sxs-lookup"><span data-stu-id="e1911-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="e1911-123">せず`x:Shared="false"`でない有効なコレクションには、その内容の一意性が強制されるためです。</span><span class="sxs-lookup"><span data-stu-id="e1911-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="e1911-124">ただし、`x:Shared="false"`動作が同じインスタンスを返す代わりに、リソースのもう 1 つの同一インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1911-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>  
  
 <span data-ttu-id="e1911-125">別のシナリオの`x:Shared="false"`使用するかどうかは、<xref:System.Windows.Freezable>アニメーション値がアニメーションあたりごとにリソースを変更するリソース。</span><span class="sxs-lookup"><span data-stu-id="e1911-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>  
  
 <span data-ttu-id="e1911-126">文字列の処理`false`大文字小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="e1911-126">The string handling of `false` is not case sensitive.</span></span>  
  
 <span data-ttu-id="e1911-127">WPF では、`x:Shared`次の条件でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e1911-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>  
  
- <span data-ttu-id="e1911-128"><xref:System.Windows.ResourceDictionary>で項目を含む`x:Shared`コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1911-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="e1911-129"><xref:System.Windows.ResourceDictionary> Loose XAML 内にすることはできませんまたはテーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1911-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>  
  
- <span data-ttu-id="e1911-130"><xref:System.Windows.ResourceDictionary>項目を格納する他の中で入れ子にする必要がありますできません<xref:System.Windows.ResourceDictionary>します。</span><span class="sxs-lookup"><span data-stu-id="e1911-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="e1911-131">たとえば、使用することはできません`x:Shared`内の項目を<xref:System.Windows.ResourceDictionary>内にある、<xref:System.Windows.Style>にではない、<xref:System.Windows.ResourceDictionary>項目。</span><span class="sxs-lookup"><span data-stu-id="e1911-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1911-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1911-132">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- [<span data-ttu-id="e1911-133">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="e1911-133">XAML Resources</span></span>](../wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="e1911-134">基本要素</span><span class="sxs-lookup"><span data-stu-id="e1911-134">Base Elements</span></span>](../wpf/advanced/base-elements.md)
