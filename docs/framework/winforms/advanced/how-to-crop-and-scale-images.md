---
title: '方法: イメージをトリミングおよびスケーリングする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937575"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="80612-102">方法: イメージをトリミングおよびスケーリングする</span><span class="sxs-lookup"><span data-stu-id="80612-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="80612-103"><xref:System.Drawing.Graphics>クラスには、いくつか用意されて<xref:System.Drawing.Graphics.DrawImage%2A>イメージのトリミングおよびスケールに使用できる元とコピー先の四角形のパラメーターを持つうちいくつかの方法です。</span><span class="sxs-lookup"><span data-stu-id="80612-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80612-104">例</span><span class="sxs-lookup"><span data-stu-id="80612-104">Example</span></span>  
 <span data-ttu-id="80612-105">次の例では、構築、 <xref:System.Drawing.Image> Apple.gif ディスク ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80612-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="80612-106">コードでは、元のサイズでリンゴのイメージ全体を描画します。</span><span class="sxs-lookup"><span data-stu-id="80612-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="80612-107">コードを呼び出して、<xref:System.Drawing.Graphics.DrawImage%2A>のメソッドを<xref:System.Drawing.Graphics>が元の apple イメージよりも大きい先の四角形で apple のイメージの一部を描画するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80612-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="80612-108"><xref:System.Drawing.Graphics.DrawImage%2A>メソッドは、5 番目と 6 番目の引数にこの 4 番目に、3 で指定されたソースの四角形を調べることで描画するために apple のどの部分を決定します。</span><span class="sxs-lookup"><span data-stu-id="80612-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="80612-109">この場合は、apple は、幅の 75% の高さの 75% をトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="80612-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="80612-110"><xref:System.Drawing.Graphics.DrawImage%2A>トリミング apple を描画する場所とする先の四角形を調べることで、トリミングされた apple 大きさ、これは、メソッドが決定します 2 番目の引数で指定します。</span><span class="sxs-lookup"><span data-stu-id="80612-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="80612-111">この場合は、先の四角形は、30% の幅と高さのある、元のイメージよりも 30% です。</span><span class="sxs-lookup"><span data-stu-id="80612-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="80612-112">次の図は apple をトリミングし、スケーリング、元の apple 示します。</span><span class="sxs-lookup"><span data-stu-id="80612-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![元のイメージと同じ画像をトリミングのスクリーン ショット。](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80612-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="80612-114">Compiling the Code</span></span>  
 <span data-ttu-id="80612-115">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="80612-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="80612-116">置き換えてください`Apple.gif`イメージ ファイル名と、システムで有効なパス。</span><span class="sxs-lookup"><span data-stu-id="80612-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80612-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="80612-117">See also</span></span>

- [<span data-ttu-id="80612-118">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="80612-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="80612-119">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="80612-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
