---
title: '方法: カラー行列を使用して、イメージのアルファ値を設定するには'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 9e102f51d00953d05ed1d217a345e32178676ffe
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716336"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="2ee06-102">方法: カラー行列を使用して、イメージのアルファ値を設定するには</span><span class="sxs-lookup"><span data-stu-id="2ee06-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="2ee06-103"><xref:System.Drawing.Bitmap>クラス (から継承する、<xref:System.Drawing.Image>クラス) と<xref:System.Drawing.Imaging.ImageAttributes>クラスが取得およびピクセル値を設定するための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2ee06-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="2ee06-104">使用することができます、<xref:System.Drawing.Imaging.ImageAttributes>アルファを変更するクラスは、イメージ全体の値または呼び出すことができます、<xref:System.Drawing.Bitmap.SetPixel%2A>のメソッド、<xref:System.Drawing.Bitmap>個々 のピクセル値を変更するクラス。</span><span class="sxs-lookup"><span data-stu-id="2ee06-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ee06-105">例</span><span class="sxs-lookup"><span data-stu-id="2ee06-105">Example</span></span>  
 <span data-ttu-id="2ee06-106"><xref:System.Drawing.Imaging.ImageAttributes>クラスの表示中にイメージの変更に使用できる多くのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="2ee06-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="2ee06-107">次の例では、<xref:System.Drawing.Imaging.ImageAttributes>だったの 80% にすべてのアルファ値を設定するオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ee06-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="2ee06-108">これは、カラー行列を初期化し、アルファ 0.8 をマトリックス内の値をスケーリングを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ee06-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="2ee06-109">カラー行列のアドレスが渡される、<xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A>のメソッド、<xref:System.Drawing.Imaging.ImageAttributes>オブジェクト、および<xref:System.Drawing.Imaging.ImageAttributes>にオブジェクトが渡される、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2ee06-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="2ee06-110">レンダリング中には、ビットマップのアルファ値は、元の 80% に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2ee06-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="2ee06-111">これは、結果、画像の背景とブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="2ee06-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="2ee06-112">ビットマップ イメージが透明は次の図では、黒い実線を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2ee06-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="2ee06-113">![行列を使用してアルファ ブレンド](./media/image2.png "イメージ 2")</span><span class="sxs-lookup"><span data-stu-id="2ee06-113">![Alpha Blending Using a Matrix](./media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="2ee06-114">イメージは、バック グラウンドの白い部分には、イメージを白にブレンドされています。</span><span class="sxs-lookup"><span data-stu-id="2ee06-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="2ee06-115">イメージは、イメージが黒の線と交差する位置黒い色とブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="2ee06-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ee06-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2ee06-116">Compiling the Code</span></span>  
 <span data-ttu-id="2ee06-117">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> のパラメーターである `e`<xref:System.Windows.Forms.PaintEventHandler> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="2ee06-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee06-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ee06-118">See also</span></span>
- [<span data-ttu-id="2ee06-119">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="2ee06-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="2ee06-120">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="2ee06-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
