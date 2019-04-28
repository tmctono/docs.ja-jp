---
title: スタイル (WPF) でアニメーション化する方法
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 5fb18a2d927746c3437ec01d2a19327be373cae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789286"
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="4b675-102">スタイル内でアニメーション化する方法</span><span class="sxs-lookup"><span data-stu-id="4b675-102">How to animate in a style</span></span>

<span data-ttu-id="4b675-103">この例では、スタイル内でプロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4b675-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="4b675-104">スタイル内でアニメーション化するときに、スタイルが定義されているフレームワーク要素だけを直接ターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="4b675-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="4b675-105">Freezable オブジェクトを対象とする必要があります「ドット ダウン」スタイルの要素のプロパティから。</span><span class="sxs-lookup"><span data-stu-id="4b675-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>

<span data-ttu-id="4b675-106">次の例では、複数のアニメーションのスタイル内で定義されているし、に適用される、<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="4b675-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="4b675-107">部分的に透明とバックエンドを不透明なから消えてしまうと、ユーザーがマウス ボタン、もう一度、繰り返し。</span><span class="sxs-lookup"><span data-stu-id="4b675-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="4b675-108">ユーザーがボタンをマウスを移動すると完全に不透明になります。</span><span class="sxs-lookup"><span data-stu-id="4b675-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="4b675-109">ボタンをクリックすると、その背景色は白を再びオレンジから変更します。</span><span class="sxs-lookup"><span data-stu-id="4b675-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="4b675-110"><xref:System.Windows.Media.SolidColorBrush>描画に使用されるボタンを直接ターゲットにできない、ボタンからダウン求めたによりアクセスされる<xref:System.Windows.Controls.Control.Background%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4b675-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="4b675-111">例</span><span class="sxs-lookup"><span data-stu-id="4b675-111">Example</span></span>

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

<span data-ttu-id="4b675-112">スタイル内でアニメーション化するときに、存在しないオブジェクトはターゲットにすることことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b675-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="4b675-113">たとえば、自分のスタイルを使用して、<xref:System.Windows.Media.SolidColorBrush>ボタンの背景のプロパティの設定が、ある時点で、スタイルがオーバーライドされ、ボタンの背景が設定されている、<xref:System.Windows.Media.LinearGradientBrush>します。</span><span class="sxs-lookup"><span data-stu-id="4b675-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="4b675-114">アニメーション化しようとして、 <xref:System.Windows.Media.SolidColorBrush> ; 例外をスローしません、アニメーションはサイレント モードで失敗します。</span><span class="sxs-lookup"><span data-stu-id="4b675-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>

<span data-ttu-id="4b675-115">構文を対象とするストーリー ボードの詳細については、次を参照してください。、[ストーリー ボードの概要](storyboards-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b675-115">For more information about storyboard targeting syntax, see the [Storyboards Overview](storyboards-overview.md).</span></span> <span data-ttu-id="4b675-116">アニメーションの詳細については、次を参照してください。、[アニメーションの概要](animation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b675-116">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="4b675-117">スタイルの詳細については、次を参照してください。、[スタイルとテンプレート](../controls/styling-and-templating.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b675-117">For more information about styles, see the [Styling and Templating](../controls/styling-and-templating.md).</span></span>
