---
title: グラフィックスとマルチメディア
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
ms.openlocfilehash: be8dcfce44347e8099e8cfa693bcee341514de2b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291442"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="dd2ef-102">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="dd2ef-102">Graphics and Multimedia</span></span>

<a name="introduction"></a>
 <span data-ttu-id="dd2ef-103">@ no__t を使用すると、マルチメディア、ベクターグラフィックス、アニメーション、およびコンテンツコンポジションがサポートされるため、開発者は興味深いユーザーインターフェイスやコンテンツを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="dd2ef-104">[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] を使用して、ベクター グラフィックスや複雑なアニメーションを作成し、メディアをアプリケーションに統合できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-104">Using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="dd2ef-105">このトピックでは、アプリケーションにグラフィックス、画面切り替え効果、サウンド、ビデオを追加できるようにする [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のグラフィックス、アニメーション、メディア機能を紹介します。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="dd2ef-106">Windows サービスで WPF 型を使用するのは避けることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="dd2ef-107">Windows サービスで WPF 型を使用しようとした場合、サービスが期待どおりに動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="dd2ef-108">WPF 4 のグラフィックスとマルチメディアの新機能</span><span class="sxs-lookup"><span data-stu-id="dd2ef-108">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="dd2ef-109">グラフィックスとアニメーションに関するいくつかの変更点があります。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-109">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="dd2ef-110">レイアウトの丸め</span><span class="sxs-lookup"><span data-stu-id="dd2ef-110">Layout Rounding</span></span>

  <span data-ttu-id="dd2ef-111">オブジェクトの端が 1 ピクセル デバイスの中間に位置する場合、DPI に依存しないグラフィックス システムでは、端がぼやけたり半透明になったりするなどのレンダリング アーティファクトが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="dd2ef-112">以前のバージョンの WPF には、このような場合の処理に役立つピクセル スナップが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="dd2ef-113">Silverlight 2 では、端がピクセル境界全体に位置するように要素を移動する別の方法としてレイアウトの丸めが導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="dd2ef-114">WPF では、<xref:System.Windows.FrameworkElement> の <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 添付プロパティを使用したレイアウト丸めがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="dd2ef-115">キャッシュ済みコンポジション</span><span class="sxs-lookup"><span data-stu-id="dd2ef-115">Cached Composition</span></span>

  <span data-ttu-id="dd2ef-116">新しい <xref:System.Windows.Media.BitmapCache> および <xref:System.Windows.Media.BitmapCacheBrush> クラスを使用すると、ビジュアルツリーの複雑な部分をビットマップとしてキャッシュし、レンダリング時間を大幅に短縮することができます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="dd2ef-117">ビットマップは、マウス クリックなどのユーザー入力に引き続き応答し、その他の要素上にブラシのように描画できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="dd2ef-118">Pixel Shader 3 のサポート</span><span class="sxs-lookup"><span data-stu-id="dd2ef-118">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="dd2ef-119">Wpf 4 は、WPF 3.5 SP1 で導入された @no__t 0 サポートの上に構築されます。これは、アプリケーションがピクセルシェーダー (PS) バージョン3.0 を使用して効果を書き込むことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="dd2ef-120">PS 3.0 のシェーダー モデルは PS 2.0 より洗練されており、サポートされているハードウェア上でより多くのエフェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="dd2ef-121">イージング関数</span><span class="sxs-lookup"><span data-stu-id="dd2ef-121">Easing Functions</span></span>

  <span data-ttu-id="dd2ef-122">イージング関数を使用してアニメーションを強化し、アニメーションの動作をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="dd2ef-123">たとえば、アニメーションに @no__t 0 を適用して、アニメーションに springy の動作を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="dd2ef-124">詳細については、「<xref:System.Windows.Media.Animation> 名前空間のイージング型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="dd2ef-125">グラフィックスとレンダリング</span><span class="sxs-lookup"><span data-stu-id="dd2ef-125">Graphics and Rendering</span></span>

<span data-ttu-id="dd2ef-126">WPF では、高品質な 2-D グラフィックがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-126">WPF includes support for high quality 2-D graphics.</span></span> <span data-ttu-id="dd2ef-127">ブラシ、ジオメトリ、イメージ、図形、変換などの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="dd2ef-128">詳しくは、「[グラフィックス](graphics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-128">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="dd2ef-129">グラフィカル要素のレンダリングは、@no__t 0 のクラスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="dd2ef-130">画面のビジュアル オブジェクトの構造は、ビジュアル ツリーで表されます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="dd2ef-131">詳しくは、「[WPF グラフィックス レンダリングの概要](wpf-graphics-rendering-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-131">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2-d-shapes"></a><span data-ttu-id="dd2ef-132">2-D 図形</span><span class="sxs-lookup"><span data-stu-id="dd2ef-132">2-D Shapes</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="dd2ef-133">は、次の図に示すように、一般的に使用されるベクター描画の2-d 図形 (四角形や楕円など) のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-133">provides a library of commonly used, vector-drawn 2-D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![楕円と四角形を示す図。](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="dd2ef-135">これらの固有の [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 図形は単なる図形ではなく、一般的なコントロールに期待されるキーボード入力やマウス入力などの機能の多くを実装するプログラミング可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-135">These intrinsic [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="dd2ef-136">次の例は、<xref:System.Windows.Shapes.Ellipse> 要素をクリックすることによって発生する @no__t 0 イベントを処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="Window1" >
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />
</Window>
```

```csharp
public partial class Window1  : Window
{
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)
    {
        MessageBox.Show("You clicked the ellipse!");
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)
        MessageBox.Show("You clicked the ellipse!")
    End Sub
End Class
```

<span data-ttu-id="dd2ef-137">上記の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] マークアップとコードビハインドの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

!["楕円をクリックしました" というメッセージボックスが表示されます。](./media/index/messagebox-text-output.png)

<span data-ttu-id="dd2ef-139">詳しくは、「 [WPF での図形と基本描画の概要](shapes-and-basic-drawing-in-wpf-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-139">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="dd2ef-140">入門用のサンプルについては、「[Shape 要素のサンプル](https://go.microsoft.com/fwlink/?LinkID=160037)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-140">For an introductory sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>

### <a name="2-d-geometries"></a><span data-ttu-id="dd2ef-141">2-D ジオメトリ</span><span class="sxs-lookup"><span data-stu-id="dd2ef-141">2-D Geometries</span></span>

<span data-ttu-id="dd2ef-142">によって提供される2-d 図形では不十分な場合は、ジオメトリとパスに対して [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] のサポートを使用して、独自の @no__t を作成できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-142">When the 2-D shapes that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides are not sufficient, you can use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] support for geometries and paths to create your own.</span></span> <span data-ttu-id="dd2ef-143">ジオメトリを使用して図形を描画ブラシとして作成し、他の [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 要素をクリップする方法を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elements.</span></span>

![図形を作成するためにジオメトリを使用する方法を示すスクリーンショット。](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="dd2ef-145">詳しくは、「[ジオメトリの概要](geometry-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-145">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="dd2ef-146">入門用のサンプルについては、「[ジオメトリのサンプル](https://go.microsoft.com/fwlink/?LinkID=159989)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-146">For an introductory sample, see [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>

### <a name="2-d-effects"></a><span data-ttu-id="dd2ef-147">2-D 効果</span><span class="sxs-lookup"><span data-stu-id="dd2ef-147">2-D Effects</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="dd2ef-148">には、さまざまな効果を作成するために使用できる2-d クラスのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-148">provides a library of 2-D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="dd2ef-149">@No__t-0 の2-d レンダリング機能を使用すると、グラデーション、ビットマップ、描画、およびビデオを含む [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 要素を描画できます。回転、拡大縮小、傾斜を使用してそれらを操作します。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-149">The 2-D rendering capability of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="dd2ef-150">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ブラシを使用して実現できる多くの効果の例を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-150">The following illustration gives an example of the many effects you can achieve by using [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] brushes.</span></span>

![さまざまな WPF ブラシと描画要素を示す図。](./media/index/brushes-paint-elements.png)

<span data-ttu-id="dd2ef-152">詳しくは、「 [WPF のブラシの概要](wpf-brushes-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-152">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="dd2ef-153">入門用のサンプルについては、「[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-153">For an introductory sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>

<a name="rendering"></a>

## <a name="3-d-rendering"></a><span data-ttu-id="dd2ef-154">3-D レンダリング</span><span class="sxs-lookup"><span data-stu-id="dd2ef-154">3-D Rendering</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="dd2ef-155">は、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] の2-d グラフィックスサポートと統合する3-d レンダリング機能のセットを提供します。これにより、より魅力的なレイアウト、@no__t 2、データビジュアライゼーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-155">provides a set of 3-D rendering capabilities that integrate with 2-D graphics support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="dd2ef-156">次の図に示すように、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] を使用すると、3-d 図形の表面に2-d イメージをレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-156">At one end of the spectrum, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to render 2-D images onto the surfaces of 3-D shapes, which the following illustration demonstrates.</span></span>

![異なるテクスチャを持つ3-d 図形を示すサンプルのスクリーンショット。](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="dd2ef-158">詳しくは、「 [3-D グラフィックスの概要](3-d-graphics-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-158">For more information, see [3-D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="dd2ef-159">入門用のサンプルについては、「[3-D ソリッドのサンプル](https://go.microsoft.com/fwlink/?LinkID=159964)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-159">For an introductory sample, see [3-D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="dd2ef-160">アニメーション</span><span class="sxs-lookup"><span data-stu-id="dd2ef-160">Animation</span></span>

<span data-ttu-id="dd2ef-161">アニメーションを使用すると、コントロールや要素を拡大、振動、回転、フェードさせることができ、魅力的なページ遷移なども作成できです。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="dd2ef-162">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ではほとんどのプロパティをアニメーション化できるため、ほとんどの [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] オブジェクトをアニメーション化できるだけでなく、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] を使用して作成するカスタム オブジェクトをアニメーション化することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-162">Because [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to animate most properties, not only can you animate most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] objects, you can also use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to animate custom objects that you create.</span></span>

![アニメーションキューブのスクリーンショット。](./media/index/animate-custom-objects.png)

<span data-ttu-id="dd2ef-164">詳しくは、「 [アニメーションの概要](animation-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-164">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="dd2ef-165">入門用のサンプルについては、「[アニメーション サンプル ギャラリー](https://go.microsoft.com/fwlink/?LinkID=159969)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-165">For an introductory sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="dd2ef-166">メディア</span><span class="sxs-lookup"><span data-stu-id="dd2ef-166">Media</span></span>

<span data-ttu-id="dd2ef-167">イメージ、ビデオ、オーディオは、情報とユーザー エクスペリエンスを伝えるメディア リッチな手段です。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="dd2ef-168">画像</span><span class="sxs-lookup"><span data-stu-id="dd2ef-168">Images</span></span>

<span data-ttu-id="dd2ef-169">アイコン、背景、アニメーションのパーツを含むイメージは、ほとんどのアプリケーションの中核です。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="dd2ef-170">イメージは頻繁に使用する必要があるため、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ではさまざまな方法でイメージを処理する機能を公開しています。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-170">Because you frequently need to use images, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="dd2ef-171">その方法の 1 つを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-171">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="dd2ef-172">![スタイルのサンプルスクリーンショット](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="dd2ef-172">![Styling sample screenshot](../controls/./media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="dd2ef-173">詳しくは、「 [イメージングの概要](imaging-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-173">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="dd2ef-174">ビデオとオーディオ</span><span class="sxs-lookup"><span data-stu-id="dd2ef-174">Video and Audio</span></span>

<span data-ttu-id="dd2ef-175">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] のグラフィックス機能の中核となる機能は、ビデオやオーディオを含むマルチメディアの処理をネイティブにサポートすることです。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-175">A core feature of the graphics capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="dd2ef-176">次の例では、メディア プレーヤーをアプリケーションに挿入する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-176">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="dd2ef-177"><xref:System.Windows.Controls.MediaElement> はビデオとオーディオの両方を再生できるので、カスタム Ui を簡単に作成できるように拡張できます。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="dd2ef-178">詳しくは、「[マルチメディアの概要](multimedia-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dd2ef-178">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd2ef-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd2ef-179">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="dd2ef-180">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="dd2ef-180">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="dd2ef-181">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="dd2ef-181">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="dd2ef-182">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="dd2ef-182">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="dd2ef-183">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="dd2ef-183">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="dd2ef-184">アニメーションとタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="dd2ef-184">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="dd2ef-185">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="dd2ef-185">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="dd2ef-186">マルチメディアの概要</span><span class="sxs-lookup"><span data-stu-id="dd2ef-186">Multimedia Overview</span></span>](multimedia-overview.md)
