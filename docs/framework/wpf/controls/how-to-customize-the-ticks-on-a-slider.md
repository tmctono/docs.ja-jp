---
title: '方法: スライダーの目盛りをカスタマイズする'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 3b32bbedb5f654ce75e90a827eb0c4dba1d4d345
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164243"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="00ae6-102">方法: スライダーの目盛りをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="00ae6-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="00ae6-103">この例は、作成する方法を示します、<xref:System.Windows.Controls.Slider>目盛りがあるコントロール。</span><span class="sxs-lookup"><span data-stu-id="00ae6-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00ae6-104">例</span><span class="sxs-lookup"><span data-stu-id="00ae6-104">Example</span></span>  
 <span data-ttu-id="00ae6-105"><xref:System.Windows.Controls.Primitives.TickBar>表示を設定すると、<xref:System.Windows.Controls.Slider.TickPlacement%2A>プロパティ以外の値を<xref:System.Windows.Controls.Primitives.TickPlacement.None>、これは、既定値。</span><span class="sxs-lookup"><span data-stu-id="00ae6-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="00ae6-106">次の例は、作成する方法を示します、<xref:System.Windows.Controls.Slider>で、<xref:System.Windows.Controls.Primitives.TickBar>ことが表示されますが目盛り。</span><span class="sxs-lookup"><span data-stu-id="00ae6-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="00ae6-107"><xref:System.Windows.Controls.Slider.TickPlacement%2A>と<xref:System.Windows.Controls.Slider.TickFrequency%2A>プロパティは、目盛りとそれらの間の間隔の場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="00ae6-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="00ae6-108">移動すると、 <xref:System.Windows.Controls.Primitives.Thumb>、ツール ヒントの値を表示する、<xref:System.Windows.Controls.Slider>します。</span><span class="sxs-lookup"><span data-stu-id="00ae6-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="00ae6-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A>プロパティは、ツールヒントが表示される場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="00ae6-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="00ae6-110"><xref:System.Windows.Controls.Primitives.Thumb>ため目盛りの場所に対応して動き<xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A>に設定されている`true`します。</span><span class="sxs-lookup"><span data-stu-id="00ae6-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="00ae6-111">次の例は、使用する方法を示します、<xref:System.Windows.Controls.Slider.Ticks%2A>マークに沿った目盛りを作成するプロパティ、<xref:System.Windows.Controls.Slider>間隔は不規則です。</span><span class="sxs-lookup"><span data-stu-id="00ae6-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="00ae6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="00ae6-112">See also</span></span>

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [<span data-ttu-id="00ae6-113">方法: スライダーをプロパティの値にバインドします。</span><span class="sxs-lookup"><span data-stu-id="00ae6-113">How to: Bind a Slider to a Property Value</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
