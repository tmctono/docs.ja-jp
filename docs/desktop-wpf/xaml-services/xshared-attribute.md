---
title: x:Shared 属性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432648"
---
# <a name="xshared-attribute"></a><span data-ttu-id="7d447-102">x:Shared 属性</span><span class="sxs-lookup"><span data-stu-id="7d447-102">x:Shared Attribute</span></span>

<span data-ttu-id="7d447-103">に`false`設定すると、WPF リソース取得動作が変更され、属性付きリソースに対する要求がすべての要求に対して同じインスタンスを共有するのではなく、要求ごとに新しいインスタンスが作成されるようにします。</span><span class="sxs-lookup"><span data-stu-id="7d447-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="7d447-104">XAML 属性の使用方法</span><span class="sxs-lookup"><span data-stu-id="7d447-104">XAML Attribute Usage</span></span>

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a><span data-ttu-id="7d447-105">解説</span><span class="sxs-lookup"><span data-stu-id="7d447-105">Remarks</span></span>

<span data-ttu-id="7d447-106">`x:Shared`XAML 言語 XAML 名前空間にマップされ、.NET XAML サービスとその XAML リーダーによって有効な XAML 言語要素として認識されます。</span><span class="sxs-lookup"><span data-stu-id="7d447-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET XAML Services and its XAML readers.</span></span> <span data-ttu-id="7d447-107">ただし、上記の`x:Shared`機能は、WPF アプリケーションと WPF XAML パーサーにのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="7d447-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="7d447-108">WPF では`x:Shared`、属性が WPF<xref:System.Windows.ResourceDictionary>内に存在するオブジェクトに適用される場合にのみ、属性として役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7d447-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="7d447-109">その他の使用法では、解析例外やその他のエラーはスローされませんが、影響はありません。</span><span class="sxs-lookup"><span data-stu-id="7d447-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>

<span data-ttu-id="7d447-110">の`x:Shared`意味は XAML 言語仕様では指定されていません。</span><span class="sxs-lookup"><span data-stu-id="7d447-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="7d447-111">.NET XAML サービスをベースに構築する XAML 実装など、他の XAML 実装では、リソース共有のサポートが必ずしも提供されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="7d447-111">Other XAML implementations, such as those that build on .NET XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="7d447-112">このような XAML 実装は、同様の動作をサポートフレームワークで提供`x:Shared`し、同様に値を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d447-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>

<span data-ttu-id="7d447-113">WPF では、リソース`x:Shared`の既定の条件`true`は です。</span><span class="sxs-lookup"><span data-stu-id="7d447-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="7d447-114">この条件は、特定のリソース要求が常に同じインスタンスを返すということを意味します。</span><span class="sxs-lookup"><span data-stu-id="7d447-114">This condition means that any given resource request always returns the same instance.</span></span>

<span data-ttu-id="7d447-115">などの<xref:System.Windows.FrameworkElement.FindResource%2A>リソース API を通じて返されるオブジェクトを変更したり、 内で<xref:System.Windows.ResourceDictionary>直接オブジェクトを変更したりすると、元のリソースが変更されます。</span><span class="sxs-lookup"><span data-stu-id="7d447-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="7d447-116">そのリソースへの参照が動的リソース参照である場合、そのリソースのコンシューマーは変更されたリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="7d447-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>

<span data-ttu-id="7d447-117">リソースへの参照が静的リソース参照であった場合、処理時間の経過後[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]のリソースへの変更は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="7d447-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="7d447-118">静的リソース参照と動的リソース参照の詳細については[、「XAML リソース](../fundamentals/xaml-resources-define.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d447-118">For more information about static versus dynamic resource references, see [XAML Resources](../fundamentals/xaml-resources-define.md).</span></span>

<span data-ttu-id="7d447-119">明示的な指定`x:Shared="true"`は、すでにデフォルトであるため、めったに行われません。</span><span class="sxs-lookup"><span data-stu-id="7d447-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="7d447-120">WPF オブジェクト モデルに相当`x:Shared`する直接のコードはありません。このメソッドは XAML の使用法でのみ指定でき、.NET XAML サービスとその XAML リーダーを使用して処理される場合は、既定の WPF 動作または読み込みパスの中間 XAML ノード ストリームで処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d447-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET XAML Services and its XAML readers.</span></span>

<span data-ttu-id="7d447-121">シナリオ`x:Shared="false"`としては、 または<xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkContentElement>派生クラスをリソースとして定義し、その要素リソースをコンテンツ モデルに導入する場合です。</span><span class="sxs-lookup"><span data-stu-id="7d447-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="7d447-122">`x:Shared="false"`では、同じコレクション (a など) で要素リソースを複数回<xref:System.Windows.Controls.UIElementCollection>導入できます。</span><span class="sxs-lookup"><span data-stu-id="7d447-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="7d447-123">コレクション`x:Shared="false"`は、その内容の一意性を強制するため、この値を指定しない場合は無効です。</span><span class="sxs-lookup"><span data-stu-id="7d447-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="7d447-124">ただし、この`x:Shared="false"`動作では、同じインスタンスを返すのではなく、リソースの別の同一のインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d447-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>

<span data-ttu-id="7d447-125">もう 1`x:Shared="false"`つのシナリオは、<xref:System.Windows.Freezable>アニメーション値にリソースを使用するが、アニメーションごとにリソースを変更する場合です。</span><span class="sxs-lookup"><span data-stu-id="7d447-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>

<span data-ttu-id="7d447-126">の文字列処理`false`では、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="7d447-126">The string handling of `false` is not case sensitive.</span></span>

<span data-ttu-id="7d447-127">WPF では`x:Shared`、次の条件でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="7d447-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>

- <span data-ttu-id="7d447-128">と<xref:System.Windows.ResourceDictionary>の`x:Shared`アイテムを含む をコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d447-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="7d447-129">緩<xref:System.Windows.ResourceDictionary>い XAML 内に含めたり、テーマに使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d447-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>

- <span data-ttu-id="7d447-130">アイテム<xref:System.Windows.ResourceDictionary>を含む は、別<xref:System.Windows.ResourceDictionary>の .</span><span class="sxs-lookup"><span data-stu-id="7d447-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="7d447-131">たとえば、 内のアイテム`x:Shared`が既に<xref:System.Windows.ResourceDictionary><xref:System.Windows.Style><xref:System.Windows.ResourceDictionary>アイテムである場合は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7d447-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d447-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d447-132">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- [<span data-ttu-id="7d447-133">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="7d447-133">XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="7d447-134">基本要素</span><span class="sxs-lookup"><span data-stu-id="7d447-134">Base Elements</span></span>](../../framework/wpf/advanced/base-elements.md)
