---
title: '方法: イメージ テクスチャによって図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911689"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="99a09-102">方法: イメージ テクスチャによって図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="99a09-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="99a09-103"><xref:System.Drawing.Image> クラス<xref:System.Drawing.TextureBrush>とクラスを使用して、閉じた図形にテクスチャを埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="99a09-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99a09-104">例</span><span class="sxs-lookup"><span data-stu-id="99a09-104">Example</span></span>  
 <span data-ttu-id="99a09-105">次の例では、楕円にイメージを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="99a09-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="99a09-106">このコードは、 <xref:System.Drawing.Image>オブジェクトを構築し、その<xref:System.Drawing.Image>オブジェクトのアドレスを引数<xref:System.Drawing.TextureBrush.%23ctor%2A>としてコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="99a09-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="99a09-107">3番目のステートメントはイメージをスケーリングし、4番目のステートメントは、拡大縮小されたイメージの繰り返しコピーを楕円に入力します。</span><span class="sxs-lookup"><span data-stu-id="99a09-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="99a09-108">次のコード<xref:System.Drawing.TextureBrush.Transform%2A>では、プロパティには、イメージが描画される前に適用される変換が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99a09-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="99a09-109">元のイメージの幅が640ピクセル、高さが480ピクセルであると仮定します。</span><span class="sxs-lookup"><span data-stu-id="99a09-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="99a09-110">変換は、水平方向と垂直方向のスケーリング値を設定することによって、イメージを75×75に縮小します。</span><span class="sxs-lookup"><span data-stu-id="99a09-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99a09-111">次の例では、イメージのサイズは75×75、楕円のサイズは150×250です。</span><span class="sxs-lookup"><span data-stu-id="99a09-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="99a09-112">画像は塗りつぶされている楕円より小さいため、楕円は画像で並べられています。</span><span class="sxs-lookup"><span data-stu-id="99a09-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="99a09-113">タイルは、図形の境界に到達するまで、画像が水平方向および垂直方向に繰り返されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="99a09-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="99a09-114">タイルの詳細については[、「方法:イメージ](how-to-tile-a-shape-with-an-image.md)を含む図形を並べます。</span><span class="sxs-lookup"><span data-stu-id="99a09-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99a09-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="99a09-115">Compiling the Code</span></span>  
 <span data-ttu-id="99a09-116">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="99a09-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99a09-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="99a09-117">See also</span></span>

- [<span data-ttu-id="99a09-118">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="99a09-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
