---
title: '方法: リソースを定義および参照する'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 80be1460906100072e6263c967c213df7968c705
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776507"
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="9b421-102">方法: リソースを定義および参照する</span><span class="sxs-lookup"><span data-stu-id="9b421-102">How to: Define and Reference a Resource</span></span>

<span data-ttu-id="9b421-103">この例は、リソースを定義し、内の属性を使用して参照する方法を示しています。[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9b421-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

## <a name="example"></a><span data-ttu-id="9b421-104">例</span><span class="sxs-lookup"><span data-stu-id="9b421-104">Example</span></span>

<span data-ttu-id="9b421-105">次の例では、2 種類のリソースを定義します。、<xref:System.Windows.Media.SolidColorBrush>リソース、およびいくつか<xref:System.Windows.Style>リソース。</span><span class="sxs-lookup"><span data-stu-id="9b421-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="9b421-106"><xref:System.Windows.Media.SolidColorBrush>リソース`MyBrush`各取るいくつかのプロパティの値を提供するため、<xref:System.Windows.Media.Brush>値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9b421-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="9b421-107"><xref:System.Windows.Style>リソース`PageBackground`、`TitleText`と`Label`各対象になる特定のコントロールの種類。</span><span class="sxs-lookup"><span data-stu-id="9b421-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="9b421-108">スタイルは、そのスタイル リソースがリソース キーによって参照され、設定に使用されるときに、対象となるコントロールのさまざまなプロパティを設定、<xref:System.Windows.FrameworkElement.Style%2A>プロパティで定義されているいくつかの特定のコントロール要素の[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9b421-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>

<span data-ttu-id="9b421-109">注いずれかのプロパティの setter 内で、`Label`スタイルを参照しても、`MyBrush`以前に定義されているリソース。</span><span class="sxs-lookup"><span data-stu-id="9b421-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="9b421-110">これは、一般的な手法が、リソースが解析され、指定した順序でリソース ディクショナリに入力したことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9b421-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="9b421-111">使用する場合は、ディクショナリ内で見つかった順序により、リソースが要求も、 [StaticResource マークアップ拡張機能](staticresource-markup-extension.md)他のリソース内から参照します。</span><span class="sxs-lookup"><span data-stu-id="9b421-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="9b421-112">参照されている任意のリソースがそのリソースを要求しよりリソースのコレクション内で以前に定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b421-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="9b421-113">かどうか、必要に応じて回避できますリソース参照の作成の厳密な順序を使用して、 [DynamicResource マークアップ拡張機能](dynamicresource-markup-extension.md)代わりに、実行時にリソースを参照するが、注意する必要がありますをこの DynamicResourceパフォーマンスに影響があります。</span><span class="sxs-lookup"><span data-stu-id="9b421-113">If necessary, you can work around the strict creation order of resource references by using a [DynamicResource Markup Extension](dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="9b421-114">詳細については、次を参照してください。 [XAML リソース](xaml-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b421-114">For details, see [XAML Resources](xaml-resources.md).</span></span>

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a><span data-ttu-id="9b421-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b421-115">See also</span></span>

- [<span data-ttu-id="9b421-116">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="9b421-116">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="9b421-117">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="9b421-117">Styling and Templating</span></span>](../controls/styling-and-templating.md)
