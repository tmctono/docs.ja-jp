---
title: '方法: キャッシュされた要素をブラシとして使用します。'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 008bec87390a807ae2b4797af8b86aaf59c92ef5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372491"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="7fa54-102">方法: キャッシュされた要素をブラシとして使用します。</span><span class="sxs-lookup"><span data-stu-id="7fa54-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="7fa54-103">使用して、<xref:System.Windows.Media.BitmapCacheBrush>を効率的にキャッシュされた要素を再利用するクラス。</span><span class="sxs-lookup"><span data-stu-id="7fa54-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="7fa54-104">要素をキャッシュするには、新しいインスタンスを作成、<xref:System.Windows.Media.BitmapCache>クラスし、要素に割り当てる<xref:System.Windows.UIElement.CacheMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7fa54-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fa54-105">例</span><span class="sxs-lookup"><span data-stu-id="7fa54-105">Example</span></span>  
 <span data-ttu-id="7fa54-106">次のコード例では、キャッシュされた要素を再利用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7fa54-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="7fa54-107">キャッシュされた要素は、<xref:System.Windows.Controls.Image>大きな画像を表示するコントロール。</span><span class="sxs-lookup"><span data-stu-id="7fa54-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="7fa54-108"><xref:System.Windows.Controls.Image>を使用して、コントロールをビットマップとしてキャッシュ、<xref:System.Windows.Media.BitmapCache>クラス、さらに、キャッシュに割り当てることで再利用、<xref:System.Windows.Media.BitmapCacheBrush>します。</span><span class="sxs-lookup"><span data-stu-id="7fa54-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="7fa54-109">ブラシは、効率的に再利用を表示する、25 個のボタンの背景に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7fa54-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="7fa54-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fa54-110">See also</span></span>
- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="7fa54-111">方法: 要素をキャッシュしてレンダリングのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="7fa54-111">How to: Improve Rendering Performance by Caching an Element</span></span>](how-to-improve-rendering-performance-by-caching-an-element.md)
