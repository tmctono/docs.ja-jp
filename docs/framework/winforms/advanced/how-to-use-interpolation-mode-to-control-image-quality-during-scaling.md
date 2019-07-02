---
title: '方法: 補間モードを使用してスケーリング時の画質を制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505715"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="a49d6-102">方法: 補間モードを使用してスケーリング時の画質を制御する</span><span class="sxs-lookup"><span data-stu-id="a49d6-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="a49d6-103">補間モードを<xref:System.Drawing.Graphics>オブジェクトの方法で構成される GDI + 拡張 (拡大および縮小) イメージに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="a49d6-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way GDI+ scales (stretches and shrinks) images.</span></span> <span data-ttu-id="a49d6-104"><xref:System.Drawing.Drawing2D.InterpolationMode>列挙型は、次のリストに表示される一部のいくつかの補間モードを定義します。</span><span class="sxs-lookup"><span data-stu-id="a49d6-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="a49d6-105">イメージを拡大するには、元のイメージ内の各ピクセルは大きいイメージのピクセルのグループにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a49d6-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="a49d6-106">イメージを縮小するには、小さいイメージの 1 つのピクセルに、元のイメージのピクセルのグループをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a49d6-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="a49d6-107">これらのマッピングを実行するアルゴリズムの効果は、スケーリングされたイメージの品質を決定します。</span><span class="sxs-lookup"><span data-stu-id="a49d6-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="a49d6-108">高品質な拡大縮小されたイメージを生成するアルゴリズムは、処理時間を必要とする傾向があります。</span><span class="sxs-lookup"><span data-stu-id="a49d6-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="a49d6-109">上記の一覧で<xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>最低の品質のモードと<xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>は最高品質のモードです。</span><span class="sxs-lookup"><span data-stu-id="a49d6-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="a49d6-110">補間モードを設定するには、メンバーのいずれかを割り当てる、<xref:System.Drawing.Drawing2D.InterpolationMode>列挙体を<xref:System.Drawing.Graphics.InterpolationMode%2A>のプロパティを<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a49d6-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a49d6-111">例</span><span class="sxs-lookup"><span data-stu-id="a49d6-111">Example</span></span>  
 <span data-ttu-id="a49d6-112">次の例では、イメージを描画し、3 つの異なる補間モードを使用してイメージが圧縮されます。</span><span class="sxs-lookup"><span data-stu-id="a49d6-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="a49d6-113">次の図は、元のイメージと 3 つの小さいイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="a49d6-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 ![さまざまな補間設定を使用してイメージを示すスクリーン ショット。](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a49d6-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a49d6-115">Compiling the Code</span></span>  
 <span data-ttu-id="a49d6-116">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="a49d6-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49d6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a49d6-117">See also</span></span>

- [<span data-ttu-id="a49d6-118">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="a49d6-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="a49d6-119">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="a49d6-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
