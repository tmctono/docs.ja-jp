---
title: '方法: 回転、反転、およびイメージの傾斜'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 3e539f41667edb505269fe420396c79b68f34e8f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711500"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="fd947-102">方法: 回転、反転、およびイメージの傾斜</span><span class="sxs-lookup"><span data-stu-id="fd947-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="fd947-103">回転、反転、および元のイメージの左上隅や右、左下角の終点を指定することで、イメージを傾けることができます。</span><span class="sxs-lookup"><span data-stu-id="fd947-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="fd947-104">次の 3 つの終点では、平行四辺形に元の四角形のイメージをマップするアフィン変換を決定します。</span><span class="sxs-lookup"><span data-stu-id="fd947-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd947-105">例</span><span class="sxs-lookup"><span data-stu-id="fd947-105">Example</span></span>  
 <span data-ttu-id="fd947-106">たとえば、元のイメージ左上隅を四角形は、(0, 0)、右上隅 (100, 0) と左下隅にある (0, 50)。</span><span class="sxs-lookup"><span data-stu-id="fd947-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="fd947-107">3 つの点を次のように終点にマップするものとします。</span><span class="sxs-lookup"><span data-stu-id="fd947-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="fd947-108">元のポイント</span><span class="sxs-lookup"><span data-stu-id="fd947-108">Original point</span></span>|<span data-ttu-id="fd947-109">終点</span><span class="sxs-lookup"><span data-stu-id="fd947-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="fd947-110">左 (0, 0)</span><span class="sxs-lookup"><span data-stu-id="fd947-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="fd947-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="fd947-111">(200, 20)</span></span>|  
|<span data-ttu-id="fd947-112">右 (100, 0)</span><span class="sxs-lookup"><span data-stu-id="fd947-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="fd947-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="fd947-113">(110, 100)</span></span>|  
|<span data-ttu-id="fd947-114">左 (0, 50)</span><span class="sxs-lookup"><span data-stu-id="fd947-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="fd947-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="fd947-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="fd947-116">次の図は、元のイメージと平行四辺形にマップされているイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="fd947-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="fd947-117">元のイメージがされて傾斜した、反映、回転、および翻訳されました。</span><span class="sxs-lookup"><span data-stu-id="fd947-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="fd947-118">元のイメージの上端に沿って、x 軸を実行している行にマップされます (200, 20) と (110, 100)。</span><span class="sxs-lookup"><span data-stu-id="fd947-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="fd947-119">元のイメージの左の端に沿って、y 軸を実行している行にマップされます (200, 20) と (250, 30)。</span><span class="sxs-lookup"><span data-stu-id="fd947-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="fd947-120">![ストライプ](./media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="fd947-120">![Stripes](./media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="fd947-121">次の図は、写真のイメージに適用するような変換を示します。</span><span class="sxs-lookup"><span data-stu-id="fd947-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="fd947-122">![変換クライマ](./media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="fd947-122">![Transformed Climber](./media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="fd947-123">次の図は、メタファイルに適用するような変換を示します。</span><span class="sxs-lookup"><span data-stu-id="fd947-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="fd947-124">![変換メタファイル](./media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="fd947-124">![Transformed Metafile](./media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="fd947-125">次の例では、最初の図に示すようにイメージを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd947-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd947-126">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fd947-126">Compiling the Code</span></span>  
 <span data-ttu-id="fd947-127">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="fd947-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="fd947-128">置き換えてください`Stripes.bmp`システム上で有効であるイメージへのパス。</span><span class="sxs-lookup"><span data-stu-id="fd947-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd947-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd947-129">See also</span></span>
- [<span data-ttu-id="fd947-130">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="fd947-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
