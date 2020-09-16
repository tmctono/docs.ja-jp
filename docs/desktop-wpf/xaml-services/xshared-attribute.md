---
title: x:Shared 属性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557789"
---
# <a name="xshared-attribute"></a><span data-ttu-id="a8268-102">x:Shared 属性</span><span class="sxs-lookup"><span data-stu-id="a8268-102">x:Shared Attribute</span></span>

<span data-ttu-id="a8268-103">に設定すると `false` 、WPF リソース取得動作を変更して、属性を持つリソースの要求で、すべての要求に対して同じインスタンスを共有するのではなく、各要求に対して新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8268-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="a8268-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="a8268-104">XAML Attribute Usage</span></span>

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a><span data-ttu-id="a8268-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8268-105">Remarks</span></span>

<span data-ttu-id="a8268-106">`x:Shared` は XAML 言語の XAML 名前空間にマップされ、.NET XAML サービスとその XAML リーダーによって有効な XAML 言語要素として認識されます。</span><span class="sxs-lookup"><span data-stu-id="a8268-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET XAML Services and its XAML readers.</span></span> <span data-ttu-id="a8268-107">ただし、に示されている機能は、 `x:Shared` wpf アプリケーションと WPF XAML パーサーにのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="a8268-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="a8268-108">WPF で `x:Shared` は、は、wpf 内に存在するオブジェクトに適用されるときに、属性としてのみ役立ち <xref:System.Windows.ResourceDictionary> ます。</span><span class="sxs-lookup"><span data-stu-id="a8268-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="a8268-109">その他の使用方法では、解析例外やその他のエラーはスローされませんが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="a8268-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>

<span data-ttu-id="a8268-110">の意味 `x:Shared` は、XAML 言語仕様では指定されていません。</span><span class="sxs-lookup"><span data-stu-id="a8268-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="a8268-111">.NET XAML サービス上に構築されるようなその他の XAML 実装は、必ずしもリソース共有のサポートを提供するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a8268-111">Other XAML implementations, such as those that build on .NET XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="a8268-112">このような XAML 実装は、値を使用するサポートフレームワークでも同様の動作を提供する可能性が `x:Shared` あります。</span><span class="sxs-lookup"><span data-stu-id="a8268-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>

<span data-ttu-id="a8268-113">WPF で `x:Shared` は、リソースの既定の条件は `true` です。</span><span class="sxs-lookup"><span data-stu-id="a8268-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="a8268-114">この条件は、特定のリソース要求が常に同じインスタンスを返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a8268-114">This condition means that any given resource request always returns the same instance.</span></span>

<span data-ttu-id="a8268-115">リソース API によって返されたオブジェクト (など) を変更し <xref:System.Windows.FrameworkElement.FindResource%2A> たり、内で直接オブジェクトを変更したりすると <xref:System.Windows.ResourceDictionary> 、元のリソースが変更されます。</span><span class="sxs-lookup"><span data-stu-id="a8268-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="a8268-116">そのリソースへの参照が動的リソース参照であった場合、そのリソースのコンシューマーは、変更されたリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8268-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>

<span data-ttu-id="a8268-117">リソースへの参照が静的リソース参照であった場合、処理時間後のリソースへの変更 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="a8268-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="a8268-118">静的リソース参照と動的リソース参照の詳細については、「 [XAML Resources](../fundamentals/xaml-resources-define.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8268-118">For more information about static versus dynamic resource references, see [XAML Resources](../fundamentals/xaml-resources-define.md).</span></span>

<span data-ttu-id="a8268-119">が明示的に指定され `x:Shared="true"` ていることはほとんどありません。これは既に既定値であるためです。</span><span class="sxs-lookup"><span data-stu-id="a8268-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="a8268-120">WPF オブジェクトモデルでは、に相当する直接コードはありません `x:Shared` 。 XAML の使用法でのみ指定できます。また、.NET Xaml サービスとその xaml リーダーを使用して処理する場合は、読み込みパスの既定の WPF の動作または中間の xaml ノードストリームで処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8268-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET XAML Services and its XAML readers.</span></span>

<span data-ttu-id="a8268-121">のシナリオは、 `x:Shared="false"` またはの派生クラスをリソースとして定義し、 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 要素リソースをコンテンツモデルに導入する場合です。</span><span class="sxs-lookup"><span data-stu-id="a8268-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="a8268-122">`x:Shared="false"` 要素リソースを同じコレクション (など) に複数回導入できるように <xref:System.Windows.Controls.UIElementCollection> します。</span><span class="sxs-lookup"><span data-stu-id="a8268-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="a8268-123">`x:Shared="false"`コレクションがその内容の一意性を強制するため、これは無効です。</span><span class="sxs-lookup"><span data-stu-id="a8268-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="a8268-124">ただし、 `x:Shared="false"` 同じインスタンスを返す代わりに、この動作によってリソースの同じインスタンスがもう1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="a8268-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>

<span data-ttu-id="a8268-125">のもう1つのシナリオ `x:Shared="false"` は、 <xref:System.Windows.Freezable> アニメーション値にリソースを使用し、アニメーションごとにリソースを変更する場合です。</span><span class="sxs-lookup"><span data-stu-id="a8268-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>

<span data-ttu-id="a8268-126">の文字列処理で `false` は、大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="a8268-126">The string handling of `false` is not case sensitive.</span></span>

<span data-ttu-id="a8268-127">WPF で `x:Shared` は、は次の条件下でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a8268-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>

- <span data-ttu-id="a8268-128"><xref:System.Windows.ResourceDictionary>を持つ項目を格納しているを `x:Shared` コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8268-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="a8268-129">を <xref:System.Windows.ResourceDictionary> ルース XAML の内側に配置したり、テーマに使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a8268-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>

- <span data-ttu-id="a8268-130"><xref:System.Windows.ResourceDictionary>項目を含むを別の内で入れ子にすることはできません <xref:System.Windows.ResourceDictionary> 。</span><span class="sxs-lookup"><span data-stu-id="a8268-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="a8268-131">たとえば、 `x:Shared` <xref:System.Windows.ResourceDictionary> <xref:System.Windows.Style> 既に項目である内の項目に対してを使用することはできません <xref:System.Windows.ResourceDictionary> 。</span><span class="sxs-lookup"><span data-stu-id="a8268-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8268-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8268-132">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- [<span data-ttu-id="a8268-133">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="a8268-133">XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="a8268-134">基本要素</span><span class="sxs-lookup"><span data-stu-id="a8268-134">Base Elements</span></span>](/dotnet/desktop/wpf/advanced/base-elements)
