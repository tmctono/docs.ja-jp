---
title: '方法: 不透明ブラシおよび半透明ブラシを使用して描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
ms.openlocfilehash: 1be3fd2ce10f6681e531559a6e9594fe3d021f5f
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582574"
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="04149-102">方法: 不透明ブラシおよび半透明ブラシを使用して描画する</span><span class="sxs-lookup"><span data-stu-id="04149-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="04149-103">図形を塗りつぶすときに<xref:System.Drawing.Brush> オブジェクトを <xref:System.Drawing.Graphics> クラスの fill メソッドの 1 つに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="04149-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="04149-104"><xref:System.Drawing.SolidBrush.%23ctor%2A> コンストラクターのパラメーターの 1 つは、<xref:System.Drawing.Color> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="04149-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="04149-105">不透明な図形を塗りつぶすには、色のアルファ コンポーネントを 255 に設定します。</span><span class="sxs-lookup"><span data-stu-id="04149-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="04149-106">半透明な図形を塗りつぶすには、アルファ コンポーネントを 1 ～ 254 の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="04149-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="04149-107">半透明な図形を塗りつぶすするとき、図形の色は、背景の色とブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="04149-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="04149-108">アルファ コンポーネントは、図形と背景色が混在する方法を指定します。0 に近いのアルファ値は、背景色の比重が高く、255 に近いアルファ値は、図形の色の比重が高くなります。</span><span class="sxs-lookup"><span data-stu-id="04149-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04149-109">例</span><span class="sxs-lookup"><span data-stu-id="04149-109">Example</span></span>  
 <span data-ttu-id="04149-110">次の例では、ビットマップを描画し、ビットマップの重複する 3 つの楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="04149-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="04149-111">最初の楕円はアルファ コンポーネントに 255 を使用するので、不透明です。</span><span class="sxs-lookup"><span data-stu-id="04149-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="04149-112">2 番目と 3 番目の楕円は、アルファ コンポーネントに 128 を使用するので、楕円から背景画像を確認できます。</span><span class="sxs-lookup"><span data-stu-id="04149-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="04149-113"><xref:System.Drawing.Graphics.CompositingQuality%2A> プロパティを設定する呼び出しにより、3 番目の楕円がのブレンドがガンマ補正と組み合わせて実行されます。</span><span class="sxs-lookup"><span data-stu-id="04149-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  

 [!code-csharp[System.Drawing.AlphaBlending#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  

 <span data-ttu-id="04149-114">次の図は、次のコードの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="04149-114">The following illustration shows the output of the following code:</span></span> 
  
 ![不透明な直線および半透明な出力を示す図。](./media/how-to-draw-with-opaque-and-semitransparent-brushes/compositingquality-ellipse-semitransparent.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="04149-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="04149-116">Compiling the Code</span></span>  
 <span data-ttu-id="04149-117">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="04149-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04149-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="04149-118">See also</span></span>

- [<span data-ttu-id="04149-119">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="04149-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="04149-120">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="04149-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="04149-121">方法: コントロールに透明な背景を提供します。</span><span class="sxs-lookup"><span data-stu-id="04149-121">How to: Give Your Control a Transparent Background</span></span>](../controls/how-to-give-your-control-a-transparent-background.md)
- [<span data-ttu-id="04149-122">方法: 不透明な直線および半透明な直線を描画します。</span><span class="sxs-lookup"><span data-stu-id="04149-122">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)
