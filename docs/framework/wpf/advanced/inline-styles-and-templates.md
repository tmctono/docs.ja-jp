---
title: インライン スタイルおよびテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460003"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="c6bff-102">インライン スタイルおよびテンプレート</span><span class="sxs-lookup"><span data-stu-id="c6bff-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="c6bff-103">には、リソース内の要素の外観を定義して複数回使用できるようにする方法として、<xref:System.Windows.Style> オブジェクトとテンプレート オブジェクト (<xref:System.Windows.FrameworkTemplate> サブクラス) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c6bff-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="c6bff-104">このため、型 <xref:System.Windows.Style> と型 <xref:System.Windows.FrameworkTemplate> を取得する [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の属性では、新しいものをインラインで定義するのではなく、既存のスタイルとテンプレートへのリソース参照をほぼ常に作成します。</span><span class="sxs-lookup"><span data-stu-id="c6bff-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="c6bff-105">インライン スタイルとテンプレートの制限事項</span><span class="sxs-lookup"><span data-stu-id="c6bff-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="c6bff-106">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] では、次の 2 つの方法のいずれかで、スタイルとテンプレートのプロパティを技術的に設定します。</span><span class="sxs-lookup"><span data-stu-id="c6bff-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="c6bff-107">属性構文を使用すると、`<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>` など、リソース内で定義されたスタイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="c6bff-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="c6bff-108">または、プロパティ要素構文を使用して、次のようにインラインでスタイルを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6bff-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="c6bff-109">`<` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="c6bff-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="c6bff-110">`<` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="c6bff-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="c6bff-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="c6bff-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="c6bff-112">`</` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="c6bff-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="c6bff-113">`</` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="c6bff-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="c6bff-114">属性を使用する方が、より一般的です。</span><span class="sxs-lookup"><span data-stu-id="c6bff-114">The attribute usage is much more common.</span></span> <span data-ttu-id="c6bff-115">インラインで定義され、リソースで定義されていないスタイルは、必然的に包含要素のみにスコープが設定されます。また、リソース キーがないため、簡単に再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6bff-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="c6bff-116">一般に、リソース定義のスタイルは、高い汎用性と利便性を備え、コード内のプログラム ロジックをマークアップのデザインから分離するという、一般的な [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] プログラミング モデルの原則に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="c6bff-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="c6bff-117">通常、スタイルまたはテンプレートをインラインで設定する理由はありません。その場所で、そのスタイルまたはテンプレートを使用するのみの場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="c6bff-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="c6bff-118">スタイルまたはテンプレートを取得できる要素のほとんどは、コンテンツ プロパティとコンテンツ モデルもサポートします。</span><span class="sxs-lookup"><span data-stu-id="c6bff-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="c6bff-119">スタイルまたはテンプレートを使用して作成した論理ツリーのみを使用する場合は、ダイレクト マークアップ内の同等の子要素を使用すると、そのコンテンツ プロパティを塗りつぶしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c6bff-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="c6bff-120">これにより、スタイルとテンプレートのメカニズムが完全にバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="c6bff-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="c6bff-121">オブジェクトを返すマークアップ拡張によって有効になったその他の構文は、スタイルやテンプレートにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6bff-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="c6bff-122">それら 2 つの拡張には、[TemplateBinding](templatebinding-markup-extension.md) および <xref:System.Windows.Data.Binding> というシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="c6bff-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6bff-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6bff-123">See also</span></span>

- [<span data-ttu-id="c6bff-124">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c6bff-124">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
