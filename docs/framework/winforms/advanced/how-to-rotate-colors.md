---
title: '方法: 色を回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967356"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="f427e-102">方法: 色を回転させる</span><span class="sxs-lookup"><span data-stu-id="f427e-102">How to: Rotate Colors</span></span>
<span data-ttu-id="f427e-103">4 次元色空間で回転は、視覚化が困難です。</span><span class="sxs-lookup"><span data-stu-id="f427e-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="f427e-104">できることができます簡単に固定色コンポーネントの 1 つを保持することに同意する回転を視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="f427e-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="f427e-105">そうですね、アルファ コンポーネントに 1 に固定の (完全に不透明) を保持するとします。</span><span class="sxs-lookup"><span data-stu-id="f427e-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="f427e-106">次の図に示すように赤、緑、および青の軸を持つ 3 次元のカラー スペースを視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="f427e-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![赤、緑、および青の軸の回転を示す図。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="f427e-108">色は、3-D 空間内の点として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="f427e-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="f427e-109">たとえば、領域で、ポイント (1, 0, 0) は赤の色を表し領域で、ポイント (0, 1, 0) は、緑の色を表します。</span><span class="sxs-lookup"><span data-stu-id="f427e-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="f427e-110">次の図は、(1, 0, 0) の色を回転する意味を示します、赤、緑のプレーンで 60 度の角度までです。</span><span class="sxs-lookup"><span data-stu-id="f427e-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="f427e-111">赤、緑の平面に平行な平面の回転は、青の軸の周りの回転として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="f427e-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![青の軸の周りの回転を示す図。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="f427e-113">次の図は、3 つの座標軸 (赤、緑、青) のそれぞれについての回転を実行するカラー行列を初期化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f427e-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![3 つの軸を中心として回転を実行するカラー行列を初期化します。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="f427e-115">例</span><span class="sxs-lookup"><span data-stu-id="f427e-115">Example</span></span>  
 <span data-ttu-id="f427e-116">次の例は、イメージを 1 つのすべての色 (1, 0, 0.6) は、青の軸の周りで 60 度回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="f427e-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="f427e-117">回転の角度は赤、緑の平面に平行な平面でをスイープします。</span><span class="sxs-lookup"><span data-stu-id="f427e-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="f427e-118">次の図は、左側と右側の色の回転後のイメージで、元のイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="f427e-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![元のイメージとイメージの色の回転を示す図。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="f427e-120">次の図は、色の回転を次のコード実行の視覚化を示しています。</span><span class="sxs-lookup"><span data-stu-id="f427e-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![色の回転の視覚エフェクトを示す図。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f427e-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f427e-122">Compiling the Code</span></span>  
 <span data-ttu-id="f427e-123">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="f427e-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f427e-124">置換`RotationInput.bmp`イメージ ファイル名とパス、システムでは無効です。</span><span class="sxs-lookup"><span data-stu-id="f427e-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f427e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f427e-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f427e-126">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="f427e-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f427e-127">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="f427e-127">Recoloring Images</span></span>](recoloring-images.md)
