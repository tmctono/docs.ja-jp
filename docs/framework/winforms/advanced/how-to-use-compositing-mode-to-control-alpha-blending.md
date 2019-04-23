---
title: '方法: 複合モードを使用してアルファ ブレンドを制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 15cb111a68cedaec011e88fa4916c292786d16b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210699"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="411f4-102">方法: 複合モードを使用してアルファ ブレンドを制御する</span><span class="sxs-lookup"><span data-stu-id="411f4-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="411f4-103">次の特性を持つオフスクリーン ビットマップを作成する場合がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="411f4-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="411f4-104">色のアルファ値 255 未満であるがあります。</span><span class="sxs-lookup"><span data-stu-id="411f4-104">Colors have alpha values that are less than 255.</span></span>  
  
-   <span data-ttu-id="411f4-105">色はいないアルファ ビットマップを作成すると、相互のブレンドです。</span><span class="sxs-lookup"><span data-stu-id="411f4-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
-   <span data-ttu-id="411f4-106">完成したビットマップを表示する場合、ビットマップの色は、アルファ ブレンドされるディスプレイ デバイスの背景色になります。</span><span class="sxs-lookup"><span data-stu-id="411f4-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="411f4-107">このようなビットマップを作成するには空白を構築<xref:System.Drawing.Bitmap>オブジェクト、および構築し、<xref:System.Drawing.Graphics>オブジェクトに基づくビットマップ。</span><span class="sxs-lookup"><span data-stu-id="411f4-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="411f4-108">複合モードの設定、<xref:System.Drawing.Graphics>オブジェクトを<xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="411f4-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="411f4-109">例</span><span class="sxs-lookup"><span data-stu-id="411f4-109">Example</span></span>  
 <span data-ttu-id="411f4-110">次の例では、作成、<xref:System.Drawing.Graphics>オブジェクトに基づいて、<xref:System.Drawing.Bitmap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="411f4-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="411f4-111">コードを使用して、<xref:System.Drawing.Graphics>と共に半透明ブラシを 2 つのオブジェクト (アルファ = 160) にビットマップを描画します。</span><span class="sxs-lookup"><span data-stu-id="411f4-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="411f4-112">コードでは、赤い楕円および半透明ブラシを使用して、緑の楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="411f4-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="411f4-113">緑色の楕円が赤い楕円、重なっているが、ため、赤、緑がブレンドしないの複合モード、<xref:System.Drawing.Graphics>にオブジェクトが設定されている<xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>します。</span><span class="sxs-lookup"><span data-stu-id="411f4-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="411f4-114">コードは、ビットマップを描画、画面に 2 回: 白の背景に 1 回と 1 回マルチカラーの背景色。</span><span class="sxs-lookup"><span data-stu-id="411f4-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="411f4-115">2 つの楕円の一部であるビットマップのピクセルはあるので、省略記号は、画面の背景色とブレンドされた、160、アルファ コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="411f4-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="411f4-116">次の図は、コード例の出力を示します。</span><span class="sxs-lookup"><span data-stu-id="411f4-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="411f4-117">省略記号がバック グラウンドとブレンドされたが、相互ブレンドしないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="411f4-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 ![ダイアグラムが表示された楕円はない他のバック グラウンドとブレンドされます。](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 <span data-ttu-id="411f4-119">コード例には、このステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="411f4-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="411f4-120">およびバック グラウンドでブレンドする省略記号を設定する場合は、そのステートメントを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="411f4-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="411f4-121">次の図は、変更後のコードの出力を示します。</span><span class="sxs-lookup"><span data-stu-id="411f4-121">The following illustration shows the output of the revised code.</span></span>  
  
 ![省略記号を示す図は、バック グラウンドを使用してまとめてブレンドされます。](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="411f4-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="411f4-123">Compiling the Code</span></span>  
 <span data-ttu-id="411f4-124">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> のパラメーターである `e`<xref:System.Windows.Forms.PaintEventHandler> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="411f4-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411f4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="411f4-125">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="411f4-126">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="411f4-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
