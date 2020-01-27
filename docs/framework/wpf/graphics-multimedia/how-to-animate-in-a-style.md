---
title: スタイルでアニメーション化する方法
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 0b29648bf15f0046adcdee610f9565f7deb24972
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744879"
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="09d5f-102">スタイルでアニメーション化する方法</span><span class="sxs-lookup"><span data-stu-id="09d5f-102">How to animate in a style</span></span>

<span data-ttu-id="09d5f-103">この例では、スタイル内のプロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="09d5f-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="09d5f-104">スタイル内でアニメーション化する場合、スタイルが定義されているフレームワーク要素のみを直接対象にできます。</span><span class="sxs-lookup"><span data-stu-id="09d5f-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="09d5f-105">Freezable オブジェクトをターゲットにするには、スタイルが指定された要素のプロパティから "ドットダウン" する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d5f-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>

<span data-ttu-id="09d5f-106">次の例では、いくつかのアニメーションがスタイル内で定義され、<xref:System.Windows.Controls.Button>に適用されます。</span><span class="sxs-lookup"><span data-stu-id="09d5f-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="09d5f-107">ユーザーがボタンの上にマウスを移動すると、不透明から部分的に半透明にフェードし、もう一度繰り返し戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="09d5f-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="09d5f-108">ユーザーがマウスポインターをボタンの外に移動すると、完全に不透明になります。</span><span class="sxs-lookup"><span data-stu-id="09d5f-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="09d5f-109">ボタンがクリックされると、背景色がオレンジ色から白に変わり、もう一度戻るようになります。</span><span class="sxs-lookup"><span data-stu-id="09d5f-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="09d5f-110">ボタンの描画に使用される <xref:System.Windows.Media.SolidColorBrush> を直接対象にすることはできません。そのため、ボタンの <xref:System.Windows.Controls.Control.Background%2A> プロパティから、このボタンにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="09d5f-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="09d5f-111">使用例</span><span class="sxs-lookup"><span data-stu-id="09d5f-111">Example</span></span>

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

<span data-ttu-id="09d5f-112">スタイル内でアニメーション化する場合は、存在しないオブジェクトを対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09d5f-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="09d5f-113">たとえば、スタイルでボタンの background プロパティを設定するために <xref:System.Windows.Media.SolidColorBrush> を使用しているときに、ある時点でスタイルがオーバーライドされ、ボタンの背景が <xref:System.Windows.Media.LinearGradientBrush>で設定されているとします。</span><span class="sxs-lookup"><span data-stu-id="09d5f-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="09d5f-114"><xref:System.Windows.Media.SolidColorBrush> をアニメーション化しようとしても、例外はスローされません。アニメーションは、単純にサイレントモードで失敗します。</span><span class="sxs-lookup"><span data-stu-id="09d5f-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>

<span data-ttu-id="09d5f-115">ストーリーボードターゲットの構文の詳細については、「[ストーリーボードの概要](storyboards-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d5f-115">For more information about storyboard targeting syntax, see the [Storyboards Overview](storyboards-overview.md).</span></span> <span data-ttu-id="09d5f-116">アニメーションの詳細については、「[アニメーションの概要](animation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d5f-116">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="09d5f-117">スタイルの詳細については、「スタイル[とテンプレート](../../../desktop-wpf/fundamentals/styles-templates-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d5f-117">For more information about styles, see the [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>
