---
title: インライン スタイルおよびテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051014"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="cfcba-102">インライン スタイルおよびテンプレート</span><span class="sxs-lookup"><span data-stu-id="cfcba-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="cfcba-103">提供<xref:System.Windows.Style>オブジェクトおよびオブジェクトのテンプレート (<xref:System.Windows.FrameworkTemplate>サブクラス) リソース内の要素の視覚的な外観を定義する方法、として使用できるように複数回です。</span><span class="sxs-lookup"><span data-stu-id="cfcba-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="cfcba-104">このため、属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]型を受け取る<xref:System.Windows.Style>と<xref:System.Windows.FrameworkTemplate>インライン新しいものを定義するのではなく、ほとんどの場合に既存のスタイルとテンプレートにリソース参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="cfcba-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="cfcba-105">インライン スタイルおよびテンプレートの制限事項</span><span class="sxs-lookup"><span data-stu-id="cfcba-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="cfcba-106">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]スタイルとテンプレートのプロパティは、2 つの方法のいずれかで技術的には設定できます。</span><span class="sxs-lookup"><span data-stu-id="cfcba-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="cfcba-107">たとえば、リソース内で定義されたスタイルを参照する属性の構文を使用できます`<`*オブジェクト*`Style="{StaticResource`*myResourceKey*`}" .../>`します。</span><span class="sxs-lookup"><span data-stu-id="cfcba-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="cfcba-108">または、インスタンスのスタイルをインラインを定義するプロパティ要素構文を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cfcba-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="cfcba-109">`<` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="cfcba-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="cfcba-110">`<` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="cfcba-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="cfcba-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="cfcba-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="cfcba-112">`</` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="cfcba-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="cfcba-113">`</` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="cfcba-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="cfcba-114">属性の使用法が一般的です。</span><span class="sxs-lookup"><span data-stu-id="cfcba-114">The attribute usage is much more common.</span></span> <span data-ttu-id="cfcba-115">スタイルはインラインで定義で定義されていないリソースにのみ、含まれる要素のスコープは必ずしも、再使用できませんに簡単にリソース キーがあるないためです。</span><span class="sxs-lookup"><span data-stu-id="cfcba-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="cfcba-116">リソースによって定義されたスタイルの汎用性と有用では、一般とが高く、一般的な[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]モデルのコードでのプログラム ロジックを分離する、マークアップでのデザイン原則をプログラミングします。</span><span class="sxs-lookup"><span data-stu-id="cfcba-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="cfcba-117">通常は、スタイルまたはテンプレートのインラインを設定する理由の場所にそのスタイルまたはテンプレートを使用する場合でも、</span><span class="sxs-lookup"><span data-stu-id="cfcba-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="cfcba-118">スタイルまたはテンプレートが実行できるほとんどの要素では、コンテンツのプロパティとコンテンツ モデルもサポートします。</span><span class="sxs-lookup"><span data-stu-id="cfcba-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="cfcba-119">論理ツリーをのみを使用している場合は、スタイルまたはテンプレートで 1 回作成する、だけコンテンツ プロパティを直接マークアップで同等の子要素を格納するより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="cfcba-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="cfcba-120">これは、バイパス、スタイルとテンプレート メカニズム完全します。</span><span class="sxs-lookup"><span data-stu-id="cfcba-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="cfcba-121">オブジェクトを返すマークアップ拡張機能によって有効になっているその他の構文は、スタイルとテンプレートのこともできます。</span><span class="sxs-lookup"><span data-stu-id="cfcba-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="cfcba-122">考えられるシナリオがある場合、このような 2 つの拡張子を含める[TemplateBinding](templatebinding-markup-extension.md)と<xref:System.Windows.Data.Binding>します。</span><span class="sxs-lookup"><span data-stu-id="cfcba-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcba-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfcba-123">See also</span></span>

- [<span data-ttu-id="cfcba-124">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cfcba-124">Styling and Templating</span></span>](../controls/styling-and-templating.md)
