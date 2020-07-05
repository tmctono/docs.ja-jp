---
title: グラフィックスとマルチメディア
description: Windows Presentation Foundation (WPF) のメディア機能を検出します。 アプリケーションにグラフィックス、切り替え効果、サウンド、ビデオを追加します。
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
ms.openlocfilehash: ba52e78564484f7714ab0035a5e1861766b72bbf
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853687"
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="cef26-104">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="cef26-104">Graphics and Multimedia</span></span>

<a name="introduction"></a>
<span data-ttu-id="cef26-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] では、マルチ メディア、ベクター グラフィックス、アニメーション、コンテンツ構成のサポートが提供されるので、開発者はユーザーの関心を引くユーザー インターフェイスやコンテンツを簡単に開発できます。</span><span class="sxs-lookup"><span data-stu-id="cef26-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="cef26-106">Visual Studio を使用して、ベクター グラフィックスや複雑なアニメーションを作成し、メディアをアプリケーションに統合できます。</span><span class="sxs-lookup"><span data-stu-id="cef26-106">Using Visual Studio, you can create vector graphics or complex animations and integrate media into your applications.</span></span>

<span data-ttu-id="cef26-107">このトピックでは、アプリケーションにグラフィックス、画面切り替え効果、サウンド、ビデオを追加できるようにする [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のグラフィックス、アニメーション、メディア機能を紹介します。</span><span class="sxs-lookup"><span data-stu-id="cef26-107">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>

> [!NOTE]
> <span data-ttu-id="cef26-108">Windows サービスで WPF 型を使用するのは避けることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cef26-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="cef26-109">Windows サービスで WPF 型を使用しようとした場合、サービスが期待どおりに動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="cef26-109">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>

<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>

## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="cef26-110">WPF 4 のグラフィックスとマルチメディアの新機能</span><span class="sxs-lookup"><span data-stu-id="cef26-110">What's New with Graphics and Multimedia in WPF 4</span></span>

<span data-ttu-id="cef26-111">グラフィックスとアニメーションに関するいくつかの変更点があります。</span><span class="sxs-lookup"><span data-stu-id="cef26-111">Several changes have been made related to graphics and animations.</span></span>

- <span data-ttu-id="cef26-112">レイアウトの丸め</span><span class="sxs-lookup"><span data-stu-id="cef26-112">Layout Rounding</span></span>

  <span data-ttu-id="cef26-113">オブジェクトの端が 1 ピクセル デバイスの中間に位置する場合、DPI に依存しないグラフィックス システムでは、端がぼやけたり半透明になったりするなどのレンダリング アーティファクトが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cef26-113">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="cef26-114">以前のバージョンの WPF には、このような場合の処理に役立つピクセル スナップが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="cef26-114">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="cef26-115">Silverlight 2 では、端がピクセル境界全体に位置するように要素を移動する別の方法としてレイアウトの丸めが導入されました。</span><span class="sxs-lookup"><span data-stu-id="cef26-115">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="cef26-116">WPF で <xref:System.Windows.FrameworkElement> の <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 添付プロパティを使用したレイアウトの丸めがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cef26-116">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>

- <span data-ttu-id="cef26-117">キャッシュ済みコンポジション</span><span class="sxs-lookup"><span data-stu-id="cef26-117">Cached Composition</span></span>

  <span data-ttu-id="cef26-118">新しい <xref:System.Windows.Media.BitmapCache> と <xref:System.Windows.Media.BitmapCacheBrush> のクラスを使用すると、ビジュアル ツリーの複雑な部分をビットマップとしてキャッシュし、レンダリング時間を大幅に短縮することができます。</span><span class="sxs-lookup"><span data-stu-id="cef26-118">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="cef26-119">ビットマップは、マウス クリックなどのユーザー入力に引き続き応答し、その他の要素上にブラシのように描画できます。</span><span class="sxs-lookup"><span data-stu-id="cef26-119">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>

- <span data-ttu-id="cef26-120">Pixel Shader 3 のサポート</span><span class="sxs-lookup"><span data-stu-id="cef26-120">Pixel Shader 3 Support</span></span>

  <span data-ttu-id="cef26-121">WPF 4 は、WPF 3.5 SP1 で導入された <xref:System.Windows.Media.Effects.ShaderEffect> サポートを基に、アプリケーションでピクセル シェーダー (PS) バージョン 3.0 を使用した効果を記述できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cef26-121">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="cef26-122">PS 3.0 のシェーダー モデルは PS 2.0 より洗練されており、サポートされているハードウェア上でより多くのエフェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cef26-122">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>

- <span data-ttu-id="cef26-123">イージング関数</span><span class="sxs-lookup"><span data-stu-id="cef26-123">Easing Functions</span></span>

  <span data-ttu-id="cef26-124">イージング関数を使用してアニメーションを強化し、アニメーションの動作をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="cef26-124">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="cef26-125">たとえば、<xref:System.Windows.Media.Animation.ElasticEase> をアニメーションに適用すると、アニメーションに弾むような動作を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="cef26-125">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="cef26-126">詳細については、<xref:System.Windows.Media.Animation> 名前空間のイージング型に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cef26-126">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>

<a name="graphics_and_rendering"></a>

## <a name="graphics-and-rendering"></a><span data-ttu-id="cef26-127">グラフィックスとレンダリング</span><span class="sxs-lookup"><span data-stu-id="cef26-127">Graphics and Rendering</span></span>

<span data-ttu-id="cef26-128">WPF では、高品質な 2D グラフィックがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cef26-128">WPF includes support for high quality 2D graphics.</span></span> <span data-ttu-id="cef26-129">ブラシ、ジオメトリ、イメージ、図形、変換などの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cef26-129">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="cef26-130">詳しくは、「[グラフィックス](graphics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-130">For more information, see [Graphics](graphics.md).</span></span> <span data-ttu-id="cef26-131">グラフィカル要素のレンダリングは、<xref:System.Windows.Media.Visual> クラスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="cef26-131">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="cef26-132">画面のビジュアル オブジェクトの構造は、ビジュアル ツリーで表されます。</span><span class="sxs-lookup"><span data-stu-id="cef26-132">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="cef26-133">詳しくは、「[WPF グラフィックス レンダリングの概要](wpf-graphics-rendering-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-133">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="cef26-134">2D シェイプ</span><span class="sxs-lookup"><span data-stu-id="cef26-134">2D Shapes</span></span>

<span data-ttu-id="cef26-135">WPF には、次の図に示す四角形や楕円のような、一般的に使用されるベクター描画の 2D シェイプのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="cef26-135">WPF provides a library of commonly used, vector-drawn 2D shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>

![楕円と四角形を示す図。](./media/index/two-deminsional-shapes-ellipses-rectangles.png)

<span data-ttu-id="cef26-137">これらの固有の WPF シェイプは単なるシェイプではなく、一般的なコントロールに期待されるキーボード入力やマウス入力などの機能の多くを実装するプログラミング可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="cef26-137">These intrinsic WPF shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="cef26-138">次の例は、<xref:System.Windows.Shapes.Ellipse> 要素をクリックすることによって発生する <xref:System.Windows.UIElement.MouseUp> イベントの処理方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cef26-138">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>

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

<span data-ttu-id="cef26-139">上記の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] マークアップとコードビハインドの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="cef26-139">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>

!["楕円をクリックしました" というメッセージ ボックス](./media/index/messagebox-text-output.png)

<span data-ttu-id="cef26-141">詳しくは、「 [WPF での図形と基本描画の概要](shapes-and-basic-drawing-in-wpf-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-141">For more information, see [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="cef26-142">入門用のサンプルについては、「[Shape 要素のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-142">For an introductory sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="cef26-143">2D ジオメトリ</span><span class="sxs-lookup"><span data-stu-id="cef26-143">2D Geometries</span></span>

<span data-ttu-id="cef26-144">WPF で提供される 2D シェイプでは不十分な場合は、WPF のジオメトリとパスのサポートを利用して独自に作成できます。</span><span class="sxs-lookup"><span data-stu-id="cef26-144">When the 2D shapes that WPF provides are not sufficient, you can use WPF support for geometries and paths to create your own.</span></span> <span data-ttu-id="cef26-145">ジオメトリを使用してシェイプを描画ブラシとして作成し、他の WPF 要素をクリップする方法を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="cef26-145">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other WPF elements.</span></span>

![シェイプを作成するためのジオメトリの使用方法を示すスクリーンショット。](./media/index/use-geometries-create-shapes.png)

<span data-ttu-id="cef26-147">詳しくは、「[ジオメトリの概要](geometry-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-147">For more information, see [Geometry Overview](geometry-overview.md).</span></span> <span data-ttu-id="cef26-148">入門用のサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-148">For an introductory sample, see [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="cef26-149">2D 効果</span><span class="sxs-lookup"><span data-stu-id="cef26-149">2D Effects</span></span>

<span data-ttu-id="cef26-150">WPF には、さまざまな効果の作成に使用できる 2D クラスのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="cef26-150">WPF provides a library of 2D classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="cef26-151">WPF の 2D レンダリング機能を使用すると、グラデーション、ビットマップ、描画、ビデオを持つ [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 要素を塗りつぶすことができます。また、回転、拡大縮小、傾斜を使用してそれらの要素を操作できます。</span><span class="sxs-lookup"><span data-stu-id="cef26-151">The 2D rendering capability of WPF provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="cef26-152">WPF のブラシを使用して実現できる多くの効果の例を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="cef26-152">The following illustration gives an example of the many effects you can achieve by using WPF brushes.</span></span>

![さまざまな WPF のブラシと描画要素を示す図。](./media/index/brushes-paint-elements.png)

<span data-ttu-id="cef26-154">詳しくは、「 [WPF のブラシの概要](wpf-brushes-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-154">For more information, see [WPF Brushes Overview](wpf-brushes-overview.md).</span></span> <span data-ttu-id="cef26-155">入門用のサンプルについては、「[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-155">For an introductory sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>

<a name="rendering"></a>

## <a name="3d-rendering"></a><span data-ttu-id="cef26-156">3D レンダリング</span><span class="sxs-lookup"><span data-stu-id="cef26-156">3D Rendering</span></span>

<span data-ttu-id="cef26-157">WPF には、さらに魅力的なレイアウト、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]、データの視覚化を実現するために WPF の 2D グラフィックス サポートと統合された一連の 3D レンダリング機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cef26-157">WPF provides a set of 3D rendering capabilities that integrate with 2D graphics support in WPF in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="cef26-158">たとえば、WPF では、次の図に示すように 2D イメージを 3D シェイプのサーフェイスにレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="cef26-158">At one end of the spectrum, WPF enables you to render 2D images onto the surfaces of 3D shapes, which the following illustration demonstrates.</span></span>

![異なるテクスチャを持つ 3D シェイプを示すサンプルのスクリーンショット。](./media/index/visual-three-dimensional-shape.png)

<span data-ttu-id="cef26-160">詳細については、「[3D グラフィックスの概要](3-d-graphics-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cef26-160">For more information, see [3D Graphics Overview](3-d-graphics-overview.md).</span></span> <span data-ttu-id="cef26-161">入門用のサンプルについては、[3D ソリッドのサンプル](https://go.microsoft.com/fwlink/?LinkID=159964)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-161">For an introductory sample, see [3D Solids Sample](https://go.microsoft.com/fwlink/?LinkID=159964).</span></span>

<a name="animation"></a>

## <a name="animation"></a><span data-ttu-id="cef26-162">アニメーション</span><span class="sxs-lookup"><span data-stu-id="cef26-162">Animation</span></span>

<span data-ttu-id="cef26-163">アニメーションを使用すると、コントロールや要素を拡大、振動、回転、フェードさせることができ、魅力的なページ遷移なども作成できです。</span><span class="sxs-lookup"><span data-stu-id="cef26-163">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="cef26-164">WPF ではほとんどのプロパティをアニメーション化できるため、ほとんどの WPF オブジェクトをアニメーション化できるだけでなく、WPF を使用して作成するカスタム オブジェクトをアニメーション化することもできます。</span><span class="sxs-lookup"><span data-stu-id="cef26-164">Because WPF enables you to animate most properties, not only can you animate most WPF objects, you can also use WPF to animate custom objects that you create.</span></span>

![アニメーション キューブのスクリーンショット。](./media/index/animate-custom-objects.png)

<span data-ttu-id="cef26-166">詳しくは、「 [アニメーションの概要](animation-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-166">For more information, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="cef26-167">入門用のサンプルについては、「[アニメーション サンプル ギャラリー](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-167">For an introductory sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>

<a name="media"></a>

## <a name="media"></a><span data-ttu-id="cef26-168">Media</span><span class="sxs-lookup"><span data-stu-id="cef26-168">Media</span></span>

<span data-ttu-id="cef26-169">イメージ、ビデオ、オーディオは、情報とユーザー エクスペリエンスを伝えるメディア リッチな手段です。</span><span class="sxs-lookup"><span data-stu-id="cef26-169">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>

### <a name="images"></a><span data-ttu-id="cef26-170">イメージ</span><span class="sxs-lookup"><span data-stu-id="cef26-170">Images</span></span>

<span data-ttu-id="cef26-171">アイコン、背景、アニメーションのパーツを含むイメージは、ほとんどのアプリケーションの中核です。</span><span class="sxs-lookup"><span data-stu-id="cef26-171">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="cef26-172">イメージは頻繁に使用する必要があるため、WPF ではさまざまな方法でイメージを処理する機能を公開しています。</span><span class="sxs-lookup"><span data-stu-id="cef26-172">Because you frequently need to use images, WPF exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="cef26-173">その方法の 1 つを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="cef26-173">The following illustration shows just one of those ways.</span></span>

<span data-ttu-id="cef26-174">![スタイル サンプルのスクリーンショット](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="cef26-174">![Styling sample screenshot](../controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>

<span data-ttu-id="cef26-175">詳しくは、「 [イメージングの概要](imaging-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-175">For more information, see [Imaging Overview](imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="cef26-176">ビデオとオーディオ</span><span class="sxs-lookup"><span data-stu-id="cef26-176">Video and Audio</span></span>

<span data-ttu-id="cef26-177">WPF のグラフィックス機能の中核となる機能は、ビデオやオーディオを含むマルチメディアの処理をネイティブにサポートすることです。</span><span class="sxs-lookup"><span data-stu-id="cef26-177">A core feature of the graphics capabilities of WPF is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="cef26-178">次の例では、メディア プレーヤーをアプリケーションに挿入する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cef26-178">The following example shows how to insert a media player into an application.</span></span>

```xaml
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />
```

<span data-ttu-id="cef26-179"><xref:System.Windows.Controls.MediaElement> は、ビデオとオーディオの両方を再生でき、カスタム UI を簡単に作成できる拡張性を備えています。</span><span class="sxs-lookup"><span data-stu-id="cef26-179"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom UIs.</span></span>

<span data-ttu-id="cef26-180">詳しくは、「[マルチメディアの概要](multimedia-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cef26-180">For more information, see the [Multimedia Overview](multimedia-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cef26-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="cef26-181">See also</span></span>

- <xref:System.Windows.Media>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Media3D>
- [<span data-ttu-id="cef26-182">2D グラフィックスとイメージング</span><span class="sxs-lookup"><span data-stu-id="cef26-182">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="cef26-183">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="cef26-183">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="cef26-184">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="cef26-184">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="cef26-185">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="cef26-185">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="cef26-186">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="cef26-186">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="cef26-187">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="cef26-187">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="cef26-188">マルチメディアの概要</span><span class="sxs-lookup"><span data-stu-id="cef26-188">Multimedia Overview</span></span>](multimedia-overview.md)
