---
title: 変換を使用した色のスケーリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504957"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="4480c-102">変換を使用した色のスケーリング</span><span class="sxs-lookup"><span data-stu-id="4480c-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="4480c-103">1 つ以上の数が 4 つの色コンポーネントのスケーリング変換を乗算します。</span><span class="sxs-lookup"><span data-stu-id="4480c-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="4480c-104">次の表に、スケーリングを表すカラー行列のエントリが与えられます。</span><span class="sxs-lookup"><span data-stu-id="4480c-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="4480c-105">スケールのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="4480c-105">Component to be scaled</span></span>|<span data-ttu-id="4480c-106">マトリックスのエントリ</span><span class="sxs-lookup"><span data-stu-id="4480c-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="4480c-107">赤</span><span class="sxs-lookup"><span data-stu-id="4480c-107">Red</span></span>|<span data-ttu-id="4480c-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="4480c-108">[0][0]</span></span>|  
|<span data-ttu-id="4480c-109">緑</span><span class="sxs-lookup"><span data-stu-id="4480c-109">Green</span></span>|<span data-ttu-id="4480c-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="4480c-110">[1][1]</span></span>|  
|<span data-ttu-id="4480c-111">青</span><span class="sxs-lookup"><span data-stu-id="4480c-111">Blue</span></span>|<span data-ttu-id="4480c-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="4480c-112">[2][2]</span></span>|  
|<span data-ttu-id="4480c-113">[アルファ]</span><span class="sxs-lookup"><span data-stu-id="4480c-113">Alpha</span></span>|<span data-ttu-id="4480c-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="4480c-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="4480c-115">1 つの色のスケーリング</span><span class="sxs-lookup"><span data-stu-id="4480c-115">Scaling One Color</span></span>  
 <span data-ttu-id="4480c-116">次の例では、構築、 <xref:System.Drawing.Image> ColorBars2.bmp ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4480c-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="4480c-117">コードは、2 の倍数でイメージ内の各ピクセルの青のコンポーネントをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="4480c-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="4480c-118">変換後のイメージと共に、元のイメージが描画されます。</span><span class="sxs-lookup"><span data-stu-id="4480c-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="4480c-119">次の図は、右側の左側に、元のイメージおよびスケーリングされたイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="4480c-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![元とスケールの色を比較するスクリーン ショット。](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="4480c-121">次の表は、青のスケーリング前に、と後に、4 つのバーの色のベクターを示します。</span><span class="sxs-lookup"><span data-stu-id="4480c-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="4480c-122">4 つ目のカラー バーに青のコンポーネント 0.8 から 0.6 をしたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4480c-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="4480c-123">GDI + は、結果の小数部の一部のみを保持するためです。</span><span class="sxs-lookup"><span data-stu-id="4480c-123">That is because GDI+ retains only the fractional part of the result.</span></span> <span data-ttu-id="4480c-124">たとえば、(2)(0.8) = 1.6、1.6 の小数部は 0.6 です。</span><span class="sxs-lookup"><span data-stu-id="4480c-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="4480c-125">小数部分のみを保持により、結果が、常には [0, 1] 間隔。</span><span class="sxs-lookup"><span data-stu-id="4480c-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="4480c-126">元</span><span class="sxs-lookup"><span data-stu-id="4480c-126">Original</span></span>|<span data-ttu-id="4480c-127">スケール</span><span class="sxs-lookup"><span data-stu-id="4480c-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="4480c-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="4480c-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="4480c-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="4480c-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="4480c-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="4480c-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="4480c-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="4480c-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="4480c-136">複数の色のスケーリング</span><span class="sxs-lookup"><span data-stu-id="4480c-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="4480c-137">次の例では、構築、 <xref:System.Drawing.Image> ColorBars2.bmp ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4480c-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="4480c-138">コードは、イメージ内の各ピクセルの赤、緑、および青のコンポーネントをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="4480c-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="4480c-139">赤のコンポーネントが 25% に縮小、緑のコンポーネントが 35%、拡大/縮小されます、および青のコンポーネントは 50% に縮小します。</span><span class="sxs-lookup"><span data-stu-id="4480c-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="4480c-140">次の図は、右側の左側に、元のイメージおよびスケーリングされたイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="4480c-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![元とスケールの色を比較するスクリーン ショット。](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="4480c-142">次の表は、赤、緑、青のスケーリング前に、と後に、4 つのバーの色のベクターを示します。</span><span class="sxs-lookup"><span data-stu-id="4480c-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="4480c-143">元</span><span class="sxs-lookup"><span data-stu-id="4480c-143">Original</span></span>|<span data-ttu-id="4480c-144">スケール</span><span class="sxs-lookup"><span data-stu-id="4480c-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="4480c-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="4480c-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="4480c-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="4480c-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="4480c-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="4480c-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="4480c-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="4480c-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="4480c-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4480c-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="4480c-153">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="4480c-154">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="4480c-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4480c-155">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="4480c-155">Recoloring Images</span></span>](recoloring-images.md)
