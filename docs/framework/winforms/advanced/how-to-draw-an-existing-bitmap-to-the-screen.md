---
title: '方法: 既存のビットマップを画面に描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 90511adf9caffe7952e270d6fe32dd85162a29d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004186"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="a25dd-102">方法: 既存のビットマップを画面に描画する</span><span class="sxs-lookup"><span data-stu-id="a25dd-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="a25dd-103">既存のイメージは、画面に簡単に描画できます。</span><span class="sxs-lookup"><span data-stu-id="a25dd-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="a25dd-104">まずを作成する必要があります、<xref:System.Drawing.Bitmap>オブジェクトは、ファイル名を受け取り、ビットマップ コンス トラクターを使用して<xref:System.Drawing.Bitmap.%23ctor%28System.String%29>します。</span><span class="sxs-lookup"><span data-stu-id="a25dd-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="a25dd-105">このコンス トラクターは、BMP、GIF、JPEG、PNG、TIFF など、いくつかの異なるファイル形式を使用したイメージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="a25dd-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="a25dd-106">作成した後、<xref:System.Drawing.Bitmap>オブジェクトを渡す<xref:System.Drawing.Bitmap>オブジェクトを<xref:System.Drawing.Graphics.DrawImage%2A>のメソッドを<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a25dd-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a25dd-107">例</span><span class="sxs-lookup"><span data-stu-id="a25dd-107">Example</span></span>  
 <span data-ttu-id="a25dd-108">この例で作成、 <xref:System.Drawing.Bitmap> JPEG ファイルからオブジェクトとで、左上隅のビットマップが描画されます (60, 10)。</span><span class="sxs-lookup"><span data-stu-id="a25dd-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="a25dd-109">次の図は、指定した位置に描画されるビットマップを示しています。</span><span class="sxs-lookup"><span data-stu-id="a25dd-109">The following illustration shows the bitmap drawn at the specified location:</span></span>  
  
 ![指定した位置にあるイメージを示すスクリーン ショット。](./media/how-to-draw-an-existing-bitmap-to-the-screen/bitmap-specified-position.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a25dd-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a25dd-111">Compiling the Code</span></span>  
 <span data-ttu-id="a25dd-112">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="a25dd-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25dd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a25dd-113">See also</span></span>

- [<span data-ttu-id="a25dd-114">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="a25dd-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="a25dd-115">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="a25dd-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
