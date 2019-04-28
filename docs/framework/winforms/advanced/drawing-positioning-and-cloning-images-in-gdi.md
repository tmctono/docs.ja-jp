---
title: GDI+ でのイメージの描画、配置、およびクローン作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756924"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="8a036-102">GDI+ でのイメージの描画、配置、およびクローン作成</span><span class="sxs-lookup"><span data-stu-id="8a036-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="8a036-103">使用することができます、<xref:System.Drawing.Bitmap>読み込みし、ラスター イメージを表示するクラスを使用できます、<xref:System.Drawing.Imaging.Metafile>クラスを読み込み、ベクター イメージを表示します。</span><span class="sxs-lookup"><span data-stu-id="8a036-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="8a036-104"><xref:System.Drawing.Bitmap>と<xref:System.Drawing.Imaging.Metafile>クラスから継承、<xref:System.Drawing.Image>クラス。</span><span class="sxs-lookup"><span data-stu-id="8a036-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="8a036-105">インスタンスが必要なベクター画像を表示する、<xref:System.Drawing.Graphics>クラスと<xref:System.Drawing.Imaging.Metafile>します。</span><span class="sxs-lookup"><span data-stu-id="8a036-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="8a036-106">インスタンスが必要なラスター イメージを表示する、<xref:System.Drawing.Graphics>クラスと<xref:System.Drawing.Bitmap>します。</span><span class="sxs-lookup"><span data-stu-id="8a036-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="8a036-107">インスタンス、<xref:System.Drawing.Graphics>クラスには、<xref:System.Drawing.Graphics.DrawImage%2A>メソッドで、受信、<xref:System.Drawing.Imaging.Metafile>または<xref:System.Drawing.Bitmap>を引数として。</span><span class="sxs-lookup"><span data-stu-id="8a036-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="8a036-108">ファイルの種類と複製</span><span class="sxs-lookup"><span data-stu-id="8a036-108">File Types and Cloning</span></span>  
 <span data-ttu-id="8a036-109">次のコード例を作成する方法を示しています、 <xref:System.Drawing.Bitmap> Climber.jpg ファイルからビットマップを表示します。</span><span class="sxs-lookup"><span data-stu-id="8a036-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="8a036-110">イメージの左上隅の終点 (10, 10) が 2 番目と 3 番目のパラメーターで指定されています。</span><span class="sxs-lookup"><span data-stu-id="8a036-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="8a036-111">次の図は、イメージを示します。</span><span class="sxs-lookup"><span data-stu-id="8a036-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="8a036-112">![サンプル イメージ](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="8a036-112">![Image Sample](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="8a036-113">構築できます<xref:System.Drawing.Bitmap>グラフィックスのさまざまなオブジェクト ファイル形式。BMP、GIF、JPEG、EXIF、PNG、TIFF、およびアイコン。</span><span class="sxs-lookup"><span data-stu-id="8a036-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="8a036-114">次のコード例は、作成する方法を示しています。<xref:System.Drawing.Bitmap>さまざまな種類のファイルからオブジェクトとし、ビットマップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a036-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="8a036-115"><xref:System.Drawing.Bitmap>クラスには、 <xref:System.Drawing.Bitmap.Clone%2A> 、既存のコピーを作成するために使用できるメソッド<xref:System.Drawing.Bitmap>します。</span><span class="sxs-lookup"><span data-stu-id="8a036-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="8a036-116"><xref:System.Drawing.Bitmap.Clone%2A>メソッドにコピーする元のビットマップの部分を指定するのに使用できるソース四角形のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="8a036-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="8a036-117">次のコード例を作成する方法を示しています、 <xref:System.Drawing.Bitmap> 、既存の上半分を複製することにより<xref:System.Drawing.Bitmap>します。</span><span class="sxs-lookup"><span data-stu-id="8a036-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="8a036-118">次に、両方のイメージが描画します。</span><span class="sxs-lookup"><span data-stu-id="8a036-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="8a036-119">次の図は、2 つのイメージを示します。</span><span class="sxs-lookup"><span data-stu-id="8a036-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="8a036-120">![トリミング](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="8a036-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a036-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a036-121">See also</span></span>

- [<span data-ttu-id="8a036-122">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="8a036-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="8a036-123">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a036-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="8a036-124">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="8a036-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
