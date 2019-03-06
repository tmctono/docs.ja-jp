---
title: '方法: システム ブラシで領域を塗りつぶす'
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 7beaf4370f115a3995c9ca23bb0022bd5b269193
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364113"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="92b4d-102">方法: システム ブラシで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="92b4d-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="92b4d-103"><xref:System.Windows.SystemColors>などクラスにシステム ブラシやシステムへのアクセスが用意されています<xref:System.Windows.SystemColors.ControlBrush%2A>、 <xref:System.Windows.SystemColors.ControlBrushKey%2A>、および<xref:System.Windows.SystemColors.DesktopBrush%2A>します。</span><span class="sxs-lookup"><span data-stu-id="92b4d-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="92b4d-104">システム ブラシは、<xref:System.Windows.Media.SolidColorBrush>オブジェクトを指定したシステム カラーで領域を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="92b4d-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="92b4d-105">システム ブラシは、常に純色の塗りつぶしを生成します。グラデーションを作成するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="92b4d-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="92b4d-106">システム ブラシは、静的なリソースとしても、動的なリソースとしても使用できます。</span><span class="sxs-lookup"><span data-stu-id="92b4d-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="92b4d-107">アプリケーションの実行中にユーザーがシステム ブラシを変更したときにブラシを自動的に更新する場合は、動的なリソースを使用します。それ以外の場合は、静的なリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="92b4d-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="92b4d-108">SystemColors クラスには、厳密な名前付け規則に従うさまざまな静的プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92b4d-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="92b4d-109">*\<SystemColor>* Brush</span><span class="sxs-lookup"><span data-stu-id="92b4d-109">*\<SystemColor>* Brush</span></span>  
  
     <span data-ttu-id="92b4d-110">静的参照を取得、<xref:System.Windows.Media.SolidColorBrush>の指定したシステム カラーです。</span><span class="sxs-lookup"><span data-stu-id="92b4d-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="92b4d-111">*\<SystemColor>* BrushKey</span><span class="sxs-lookup"><span data-stu-id="92b4d-111">*\<SystemColor>* BrushKey</span></span>  
  
     <span data-ttu-id="92b4d-112">動的参照を取得、<xref:System.Windows.Media.SolidColorBrush>の指定したシステム カラーです。</span><span class="sxs-lookup"><span data-stu-id="92b4d-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="92b4d-113">*\<SystemColor>* Color</span><span class="sxs-lookup"><span data-stu-id="92b4d-113">*\<SystemColor>* Color</span></span>  
  
     <span data-ttu-id="92b4d-114">静的参照を取得、<xref:System.Windows.Media.Color>指定したシステム カラーの構造体。</span><span class="sxs-lookup"><span data-stu-id="92b4d-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="92b4d-115">*\<SystemColor>* ColorKey</span><span class="sxs-lookup"><span data-stu-id="92b4d-115">*\<SystemColor>* ColorKey</span></span>  
  
     <span data-ttu-id="92b4d-116">動的参照を取得、<xref:System.Windows.Media.Color>指定したシステム カラーの構造体。</span><span class="sxs-lookup"><span data-stu-id="92b4d-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="92b4d-117">システム カラーは、<xref:System.Windows.Media.Color>ブラシを構成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="92b4d-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="92b4d-118">たとえば、システム カラーを設定して、使用してグラデーションを作成することができます、<xref:System.Windows.Media.GradientStop.Color%2A>のプロパティを<xref:System.Windows.Media.LinearGradientBrush>オブジェクトのシステム カラーとグラデーションの分岐点。</span><span class="sxs-lookup"><span data-stu-id="92b4d-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="92b4d-119">例については、次を参照してください。[グラデーションでシステム カラーを使用して](how-to-use-system-colors-in-a-gradient.md)します。</span><span class="sxs-lookup"><span data-stu-id="92b4d-119">For an example, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92b4d-120">例</span><span class="sxs-lookup"><span data-stu-id="92b4d-120">Example</span></span>  
 <span data-ttu-id="92b4d-121">次の例では、動的なシステム ブラシの参照を使用して、ボタンの背景を設定します。</span><span class="sxs-lookup"><span data-stu-id="92b4d-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="92b4d-122">次の例では、静的なシステム ブラシの参照を使用して、ボタンの背景を設定します。</span><span class="sxs-lookup"><span data-stu-id="92b4d-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="92b4d-123">グラデーションでシステム カラーを使用する方法を示す例は、次を参照してください。[グラデーションでシステム カラーを使用して](how-to-use-system-colors-in-a-gradient.md)します。</span><span class="sxs-lookup"><span data-stu-id="92b4d-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b4d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="92b4d-124">See also</span></span>
- [<span data-ttu-id="92b4d-125">グラデーションでシステム カラーを使用する</span><span class="sxs-lookup"><span data-stu-id="92b4d-125">Use System Colors in a Gradient</span></span>](how-to-use-system-colors-in-a-gradient.md)
- [<span data-ttu-id="92b4d-126">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="92b4d-126">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
