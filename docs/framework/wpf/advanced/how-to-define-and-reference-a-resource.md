---
title: '方法 : リソースを定義および参照する'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 89471c45aabd9f3415c45a2e8af41d1a52900324
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460178"
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="14d18-102">方法 : リソースを定義および参照する</span><span class="sxs-lookup"><span data-stu-id="14d18-102">How to: Define and Reference a Resource</span></span>

<span data-ttu-id="14d18-103">この例では、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の属性を使用してリソースを定義し、それを参照する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14d18-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

## <a name="example"></a><span data-ttu-id="14d18-104">例</span><span class="sxs-lookup"><span data-stu-id="14d18-104">Example</span></span>

<span data-ttu-id="14d18-105">次の例では、2種類のリソースを定義しています。 <xref:System.Windows.Media.SolidColorBrush> リソースと、いくつかの <xref:System.Windows.Style> リソースです。</span><span class="sxs-lookup"><span data-stu-id="14d18-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="14d18-106"><xref:System.Windows.Media.SolidColorBrush> リソース `MyBrush` は、それぞれが <xref:System.Windows.Media.Brush> 型の値を受け取るいくつかのプロパティの値を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="14d18-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="14d18-107"><xref:System.Windows.Style> リソース `PageBackground`、`TitleText`、および `Label` は、特定のコントロールの種類を対象とします。</span><span class="sxs-lookup"><span data-stu-id="14d18-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="14d18-108">スタイルリソースがリソースキーによって参照され、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]で定義されているいくつかの特定のコントロール要素の <xref:System.Windows.FrameworkElement.Style%2A> プロパティを設定するために使用される場合、スタイルは対象のコントロールにさまざまなプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="14d18-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>

<span data-ttu-id="14d18-109">`Label` スタイルの setter 内のいずれかのプロパティも、前に定義した `MyBrush` リソースを参照していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="14d18-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="14d18-110">これは一般的な手法ですが、リソースが解析され、指定された順序でリソースディクショナリに入力されることに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="14d18-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="14d18-111">また、 [StaticResource マークアップ拡張機能](staticresource-markup-extension.md)を使用して別のリソース内から参照する場合は、ディクショナリ内で見つかった順序によってリソースが要求されます。</span><span class="sxs-lookup"><span data-stu-id="14d18-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="14d18-112">参照するリソースがリソースコレクション内で前に定義されていることを確認してから、そのリソースを要求します。</span><span class="sxs-lookup"><span data-stu-id="14d18-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="14d18-113">必要に応じて、 [Dynamicresource マークアップ拡張機能](dynamicresource-markup-extension.md)を使用してリソース参照の厳密な作成順序を回避し、代わりに実行時にリソースを参照することができますが、この dynamicresource 手法はパフォーマンスを備えていることに注意する必要があります。措置.</span><span class="sxs-lookup"><span data-stu-id="14d18-113">If necessary, you can work around the strict creation order of resource references by using a [DynamicResource Markup Extension](dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="14d18-114">詳細については、「 [XAML Resources](xaml-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d18-114">For details, see [XAML Resources](xaml-resources.md).</span></span>

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a><span data-ttu-id="14d18-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="14d18-115">See also</span></span>

- [<span data-ttu-id="14d18-116">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="14d18-116">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="14d18-117">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="14d18-117">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
