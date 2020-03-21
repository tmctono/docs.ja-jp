---
title: '方法 : 色を回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111336"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="d422c-102">方法 : 色を回転させる</span><span class="sxs-lookup"><span data-stu-id="d422c-102">How to: Rotate Colors</span></span>
<span data-ttu-id="d422c-103">4 次元のカラースペースでの回転は、視覚化が困難です。</span><span class="sxs-lookup"><span data-stu-id="d422c-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="d422c-104">色成分の 1 つを固定していくことに同意することで、回転を簡単に視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="d422c-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="d422c-105">アルファ成分を1(完全に不透明)に固定することに同意するとします。</span><span class="sxs-lookup"><span data-stu-id="d422c-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="d422c-106">次の図に示すように、赤、緑、青の軸を使用して、3 次元の色空間を視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="d422c-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![赤、緑、青の軸で回転を示す図。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="d422c-108">色は 3D 空間の点と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="d422c-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="d422c-109">たとえば、空間内の点 (1, 0, 0) は赤を表し、空間内の点 (0, 1, 0) は緑を表します。</span><span class="sxs-lookup"><span data-stu-id="d422c-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="d422c-110">次の図は、赤緑平面で 60 度の角度で色 (1, 0, 0) を回転する意味を示しています。</span><span class="sxs-lookup"><span data-stu-id="d422c-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="d422c-111">赤緑平面に平行な平面の回転は、青い軸を中心とした回転と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="d422c-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![青い軸を中心とした回転を示す図。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="d422c-113">次の図は、カラー マトリックスを初期化して、3 つの座標軸 (赤、緑、青) のそれぞれについて回転を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d422c-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![3 軸の回転を実行するようにカラー マトリックスを初期化します。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="d422c-115">例</span><span class="sxs-lookup"><span data-stu-id="d422c-115">Example</span></span>  
 <span data-ttu-id="d422c-116">次の例では、1 色 (1, 0, 0.6) のイメージを取得し、青軸を中心に 60 度回転します。</span><span class="sxs-lookup"><span data-stu-id="d422c-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="d422c-117">回転角度は、赤緑の平面に平行な平面でスイープされます。</span><span class="sxs-lookup"><span data-stu-id="d422c-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="d422c-118">次の図は、左側に元のイメージを、右にカラー回転したイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="d422c-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![元のイメージとカラー回転したイメージを示す図。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="d422c-120">次の図は、次のコードで実行される色の回転の視覚化を示しています。</span><span class="sxs-lookup"><span data-stu-id="d422c-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![色の回転の視覚化を示す図。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d422c-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d422c-122">Compiling the Code</span></span>  
 <span data-ttu-id="d422c-123">上記の例は Windows フォームで使用するように設計されており、<xref:System.Windows.Forms.PaintEventArgs>`e`<xref:System.Windows.Forms.Control.Paint>イベント ハンドラーのパラメーターである が必要です。</span><span class="sxs-lookup"><span data-stu-id="d422c-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="d422c-124">システム`RotationInput.bmp`で有効なイメージ ファイル名とパスで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d422c-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d422c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d422c-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="d422c-126">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="d422c-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="d422c-127">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="d422c-127">Recoloring Images</span></span>](recoloring-images.md)
