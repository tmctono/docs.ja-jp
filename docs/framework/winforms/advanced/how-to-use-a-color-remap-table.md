---
title: '方法: カラー リマップ テーブルを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: bff5e3585804e027f2d0e78e5ea525f933a351a5
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593182"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="0549d-102">方法: カラー リマップ テーブルを使用する</span><span class="sxs-lookup"><span data-stu-id="0549d-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="0549d-103">カラー リマップ テーブルをに従ってイメージの色を変換するプロセスは、再マップします。</span><span class="sxs-lookup"><span data-stu-id="0549d-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="0549d-104">カラー リマップ テーブルの配列は、<xref:System.Drawing.Imaging.ColorMap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0549d-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="0549d-105">各<xref:System.Drawing.Imaging.ColorMap>、配列内のオブジェクトは、<xref:System.Drawing.Imaging.ColorMap.OldColor%2A>プロパティと<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0549d-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="0549d-106">ときに[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]イメージ、イメージの各ピクセルの描画は古い色の配列と比較されます。</span><span class="sxs-lookup"><span data-stu-id="0549d-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="0549d-107">ピクセルの色が以前の色に一致する場合、その色は、対応する新しい色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="0549d-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="0549d-108">表示のみの色を変更、イメージ自体の色の値 (に格納されている、<xref:System.Drawing.Image>または<xref:System.Drawing.Bitmap>オブジェクト) は変更されません。</span><span class="sxs-lookup"><span data-stu-id="0549d-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="0549d-109">マップが変更されたイメージを描画するには、配列を初期化<xref:System.Drawing.Imaging.ColorMap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0549d-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="0549d-110">その配列を渡す、<xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A>のメソッド、<xref:System.Drawing.Imaging.ImageAttributes>オブジェクト、し、渡します、<xref:System.Drawing.Imaging.ImageAttributes>オブジェクトを<xref:System.Drawing.Graphics.DrawImage%2A>のメソッドを<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0549d-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0549d-111">例</span><span class="sxs-lookup"><span data-stu-id="0549d-111">Example</span></span>  
 <span data-ttu-id="0549d-112">次の例では、作成、 <xref:System.Drawing.Image> RemapInput.bmp ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0549d-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="0549d-113">コードが単一のカラー リマップ テーブルを作成します<xref:System.Drawing.Imaging.ColorMap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0549d-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="0549d-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A>のプロパティ、`ColorRemap`オブジェクトは赤い、および<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>プロパティは青です。</span><span class="sxs-lookup"><span data-stu-id="0549d-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="0549d-115">イメージは、描画せず、再マップと再マップが 1 回です。</span><span class="sxs-lookup"><span data-stu-id="0549d-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="0549d-116">再マッピング プロセスを青の赤のすべてのピクセルを変更します。</span><span class="sxs-lookup"><span data-stu-id="0549d-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="0549d-117">次の図は、左側の元のイメージ、右側のマップが変更されたイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="0549d-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![元のイメージとマップが変更されたイメージを示すスクリーン ショット。](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0549d-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="0549d-119">Compiling the Code</span></span>  
 <span data-ttu-id="0549d-120">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0549d-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0549d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0549d-121">See also</span></span>

- [<span data-ttu-id="0549d-122">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="0549d-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="0549d-123">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="0549d-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
