---
title: '方法: トリミングおよびスケール イメージ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: ff0567dca0fd86736e02a9dd827ec15df8bf2df8
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654498"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="220ba-102">方法: トリミングおよびスケール イメージ</span><span class="sxs-lookup"><span data-stu-id="220ba-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="220ba-103"><xref:System.Drawing.Graphics>クラスには、いくつか用意されて<xref:System.Drawing.Graphics.DrawImage%2A>イメージのトリミングおよびスケールに使用できる元とコピー先の四角形のパラメーターを持つうちいくつかの方法です。</span><span class="sxs-lookup"><span data-stu-id="220ba-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="220ba-104">例</span><span class="sxs-lookup"><span data-stu-id="220ba-104">Example</span></span>  
 <span data-ttu-id="220ba-105">次の例では、構築、 <xref:System.Drawing.Image> Apple.gif ディスク ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="220ba-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="220ba-106">コードでは、元のサイズでリンゴのイメージ全体を描画します。</span><span class="sxs-lookup"><span data-stu-id="220ba-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="220ba-107">コードを呼び出して、<xref:System.Drawing.Graphics.DrawImage%2A>のメソッドを<xref:System.Drawing.Graphics>が元の apple イメージよりも大きい先の四角形で apple のイメージの一部を描画するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="220ba-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="220ba-108"><xref:System.Drawing.Graphics.DrawImage%2A>メソッドは、5 番目と 6 番目の引数にこの 4 番目に、3 で指定されたソースの四角形を調べることで描画するために apple のどの部分を決定します。</span><span class="sxs-lookup"><span data-stu-id="220ba-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="220ba-109">この場合は、apple は、幅の 75% の高さの 75% をトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="220ba-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="220ba-110"><xref:System.Drawing.Graphics.DrawImage%2A>トリミング apple を描画する場所とする先の四角形を調べることで、トリミングされた apple 大きさ、これは、メソッドが決定します 2 番目の引数で指定します。</span><span class="sxs-lookup"><span data-stu-id="220ba-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="220ba-111">この場合は、先の四角形は、30% の幅と高さのある、元のイメージよりも 30% です。</span><span class="sxs-lookup"><span data-stu-id="220ba-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="220ba-112">次の図は apple をトリミングし、スケーリング、元の apple 示します。</span><span class="sxs-lookup"><span data-stu-id="220ba-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![元のイメージと同じ画像をトリミングのスクリーン ショット。](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="220ba-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="220ba-114">Compiling the Code</span></span>  
 <span data-ttu-id="220ba-115">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="220ba-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="220ba-116">置き換えてください`Apple.gif`イメージ ファイル名と、システムで有効なパス。</span><span class="sxs-lookup"><span data-stu-id="220ba-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="220ba-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="220ba-117">See also</span></span>
- [<span data-ttu-id="220ba-118">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="220ba-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="220ba-119">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="220ba-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
