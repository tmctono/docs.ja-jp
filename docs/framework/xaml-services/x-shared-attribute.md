---
title: x:Shared 属性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: c820a9b1d9708e24b1460378199a6addc1e20899
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459928"
---
# <a name="xshared-attribute"></a><span data-ttu-id="57c3b-102">x:Shared 属性</span><span class="sxs-lookup"><span data-stu-id="57c3b-102">x:Shared Attribute</span></span>
<span data-ttu-id="57c3b-103">`false`に設定すると、WPF のリソース取得動作を変更して、すべての要求に対して同じインスタンスを共有するのではなく、属性付きリソースの要求によって要求ごとに新しいインスタンスが作成されるようにします。</span><span class="sxs-lookup"><span data-stu-id="57c3b-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="57c3b-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="57c3b-104">XAML Attribute Usage</span></span>  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a><span data-ttu-id="57c3b-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="57c3b-105">Remarks</span></span>  
 <span data-ttu-id="57c3b-106">`x:Shared` は xaml 言語の XAML 名前空間にマップされ、xaml サービスとその XAML リーダー .NET Framework によって有効な XAML 言語要素として認識されます。</span><span class="sxs-lookup"><span data-stu-id="57c3b-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET Framework XAML Services and its XAML readers.</span></span> <span data-ttu-id="57c3b-107">ただし、`x:Shared` に示されている機能は、WPF アプリケーションと WPF XAML パーサーにのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="57c3b-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="57c3b-108">WPF では、WPF <xref:System.Windows.ResourceDictionary>内に存在するオブジェクトに適用される場合、`x:Shared` は属性としてのみ役立ちます。</span><span class="sxs-lookup"><span data-stu-id="57c3b-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="57c3b-109">その他の使用方法では、解析例外やその他のエラーはスローされませんが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>  
  
 <span data-ttu-id="57c3b-110">`x:Shared` の意味は、XAML 言語仕様では指定されていません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="57c3b-111">.NET Framework XAML サービス上に構築されるようなその他の XAML 実装は、必ずしもリソース共有のサポートを提供するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-111">Other XAML implementations, such as those that build on .NET Framework XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="57c3b-112">このような XAML 実装は、値の `x:Shared` も使用する、サポートフレームワークで同様の動作を提供する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57c3b-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>  
  
 <span data-ttu-id="57c3b-113">WPF では、リソースの既定の `x:Shared` 条件が `true`ます。</span><span class="sxs-lookup"><span data-stu-id="57c3b-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="57c3b-114">この条件は、特定のリソース要求が常に同じインスタンスを返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="57c3b-114">This condition means that any given resource request always returns the same instance.</span></span>  
  
 <span data-ttu-id="57c3b-115">リソース API によって返されたオブジェクト (<xref:System.Windows.FrameworkElement.FindResource%2A>など) を変更したり、<xref:System.Windows.ResourceDictionary>内のオブジェクトを直接変更したりすると、元のリソースが変更されます。</span><span class="sxs-lookup"><span data-stu-id="57c3b-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="57c3b-116">そのリソースへの参照が動的リソース参照であった場合、そのリソースのコンシューマーは、変更されたリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="57c3b-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>  
  
 <span data-ttu-id="57c3b-117">リソースへの参照が静的リソース参照であった場合、[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] の処理時間の後にリソースを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="57c3b-118">静的リソース参照と動的リソース参照の詳細については、「 [XAML Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57c3b-118">For more information about static versus dynamic resource references, see [XAML Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
 <span data-ttu-id="57c3b-119">`x:Shared="true"` は、既に既定値であるため、明示的に指定することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="57c3b-120">WPF オブジェクトモデルの `x:Shared` に対応するダイレクトコードはありません。XAML の使用でのみ指定でき、既定の WPF の動作、または .NET Framework XAML サービスとその XAML リーダーを使用して処理された場合は、読み込みパスの中間 XAML ノードストリームで処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57c3b-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET Framework XAML Services and its XAML readers.</span></span>  
  
 <span data-ttu-id="57c3b-121">`x:Shared="false"` のシナリオは、<xref:System.Windows.FrameworkElement> または <xref:System.Windows.FrameworkContentElement> 派生クラスをリソースとして定義し、要素リソースをコンテンツモデルに導入する場合です。</span><span class="sxs-lookup"><span data-stu-id="57c3b-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="57c3b-122">`x:Shared="false"` を使用すると、要素リソースを同じコレクション (<xref:System.Windows.Controls.UIElementCollection>など) に複数回導入できます。</span><span class="sxs-lookup"><span data-stu-id="57c3b-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="57c3b-123">`x:Shared="false"` がない場合、コレクションはその内容の一意性を強制するため無効です。</span><span class="sxs-lookup"><span data-stu-id="57c3b-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="57c3b-124">ただし、`x:Shared="false"` の動作では、同じインスタンスを返す代わりに、リソースの同じインスタンスがもう1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="57c3b-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>  
  
 <span data-ttu-id="57c3b-125">`x:Shared="false"` のもう1つのシナリオは、<xref:System.Windows.Freezable> リソースをアニメーション値に使用し、アニメーションごとにリソースを変更する場合です。</span><span class="sxs-lookup"><span data-stu-id="57c3b-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>  
  
 <span data-ttu-id="57c3b-126">`false` の文字列処理では、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-126">The string handling of `false` is not case sensitive.</span></span>  
  
 <span data-ttu-id="57c3b-127">WPF では、`x:Shared` は次の条件下でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="57c3b-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>  
  
- <span data-ttu-id="57c3b-128">`x:Shared` を持つ項目を含む <xref:System.Windows.ResourceDictionary> をコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57c3b-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="57c3b-129"><xref:System.Windows.ResourceDictionary> をルース XAML の内側に配置したり、テーマに使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>  
  
- <span data-ttu-id="57c3b-130">項目を含む <xref:System.Windows.ResourceDictionary> を別の <xref:System.Windows.ResourceDictionary>内で入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="57c3b-131">たとえば、既に <xref:System.Windows.ResourceDictionary> 項目である <xref:System.Windows.Style> 内にある <xref:System.Windows.ResourceDictionary> 内の項目に対して `x:Shared` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="57c3b-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c3b-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="57c3b-132">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- [<span data-ttu-id="57c3b-133">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="57c3b-133">XAML Resources</span></span>](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="57c3b-134">基本要素</span><span class="sxs-lookup"><span data-stu-id="57c3b-134">Base Elements</span></span>](../wpf/advanced/base-elements.md)
