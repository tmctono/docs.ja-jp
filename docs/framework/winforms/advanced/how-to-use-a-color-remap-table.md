---
title: '方法: カラー リマップ テーブルを使用して、'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 72965d6968aab256579929acc00e629bcd3c71f0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707335"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="3bad1-102">方法: カラー リマップ テーブルを使用して、</span><span class="sxs-lookup"><span data-stu-id="3bad1-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="3bad1-103">カラー リマップ テーブルをに従ってイメージの色を変換するプロセスは、再マップします。</span><span class="sxs-lookup"><span data-stu-id="3bad1-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="3bad1-104">カラー リマップ テーブルの配列は、<xref:System.Drawing.Imaging.ColorMap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3bad1-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3bad1-105">各<xref:System.Drawing.Imaging.ColorMap>、配列内のオブジェクトは、<xref:System.Drawing.Imaging.ColorMap.OldColor%2A>プロパティと<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3bad1-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="3bad1-106">ときに[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]イメージ、イメージの各ピクセルの描画は古い色の配列と比較されます。</span><span class="sxs-lookup"><span data-stu-id="3bad1-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="3bad1-107">ピクセルの色が以前の色に一致する場合、その色は、対応する新しい色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="3bad1-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="3bad1-108">表示のみの色を変更、イメージ自体の色の値 (に格納されている、<xref:System.Drawing.Image>または<xref:System.Drawing.Bitmap>オブジェクト) は変更されません。</span><span class="sxs-lookup"><span data-stu-id="3bad1-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="3bad1-109">マップが変更されたイメージを描画するには、配列を初期化<xref:System.Drawing.Imaging.ColorMap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3bad1-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3bad1-110">その配列を渡す、<xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A>のメソッド、<xref:System.Drawing.Imaging.ImageAttributes>オブジェクト、し、渡します、<xref:System.Drawing.Imaging.ImageAttributes>オブジェクトを<xref:System.Drawing.Graphics.DrawImage%2A>のメソッドを<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3bad1-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bad1-111">例</span><span class="sxs-lookup"><span data-stu-id="3bad1-111">Example</span></span>  
 <span data-ttu-id="3bad1-112">次の例では、作成、 <xref:System.Drawing.Image> RemapInput.bmp ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3bad1-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="3bad1-113">コードが単一のカラー リマップ テーブルを作成します<xref:System.Drawing.Imaging.ColorMap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3bad1-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="3bad1-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A>のプロパティ、`ColorRemap`オブジェクトは赤い、および<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>プロパティは青です。</span><span class="sxs-lookup"><span data-stu-id="3bad1-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="3bad1-115">イメージは、描画せず、再マップと再マップが 1 回です。</span><span class="sxs-lookup"><span data-stu-id="3bad1-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="3bad1-116">再マッピング プロセスを青の赤のすべてのピクセルを変更します。</span><span class="sxs-lookup"><span data-stu-id="3bad1-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="3bad1-117">次の図は、左側の元のイメージ、右側のマップが変更されたイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="3bad1-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="3bad1-118">![カラー リマップ](./media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="3bad1-118">![Color ReMap](./media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3bad1-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3bad1-119">Compiling the Code</span></span>  
 <span data-ttu-id="3bad1-120">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="3bad1-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bad1-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bad1-121">See also</span></span>
- [<span data-ttu-id="3bad1-122">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="3bad1-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="3bad1-123">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="3bad1-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
