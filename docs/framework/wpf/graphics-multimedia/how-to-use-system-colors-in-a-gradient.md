---
title: '方法: グラデーションでシステム カラーを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 55c99640907a0c372f8c7bbc50b9b45c9f15ef3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769240"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="04315-102">方法: グラデーションでシステム カラーを使用する</span><span class="sxs-lookup"><span data-stu-id="04315-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="04315-103">グラデーションでシステム カラーを使用するには、<xref:System.Windows.SystemColors> クラスの *\<SystemColor>* Color と *\<SystemColor>* ColorKey の静的プロパティを使用して、カラーの参照を取得します。ここで、 *\<SystemColor>* は、目的のシステム カラーの名前です。</span><span class="sxs-lookup"><span data-stu-id="04315-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="04315-104">システム テーマが変更されたときに自動的に更新される動的参照を作成する場合は、 *\<SystemColor>* ColorKey プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="04315-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="04315-105">それ以外の場合は、 *\<SystemColor>* Color プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="04315-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04315-106">例</span><span class="sxs-lookup"><span data-stu-id="04315-106">Example</span></span>  
 <span data-ttu-id="04315-107">次の例では、動的なシステム カラー リソースを使用して、グラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="04315-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="04315-108">次の例では、静的なシステム カラー リソースを使用して、グラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="04315-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="04315-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="04315-109">See also</span></span>

- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="04315-110">システム ブラシで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="04315-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="04315-111">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="04315-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
