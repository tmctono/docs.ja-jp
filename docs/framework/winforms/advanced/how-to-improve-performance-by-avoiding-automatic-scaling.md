---
title: '方法: 自動スケーリングを解除してパフォーマンスを向上させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: 49ec491308cc6a9fd81e74bff213029389137b88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61724064"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a><span data-ttu-id="b970d-102">方法: 自動スケーリングを解除してパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="b970d-102">How to: Improve Performance by Avoiding Automatic Scaling</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="b970d-103">描画すると、パフォーマンスが低下する、イメージをスケーリング自動的に場合があります。</span><span class="sxs-lookup"><span data-stu-id="b970d-103">may automatically scale an image as you draw it, which would decrease performance.</span></span> <span data-ttu-id="b970d-104">描画先の四角形の大きさを渡すことによって、イメージのスケーリングを制御する代わりに、<xref:System.Drawing.Graphics.DrawImage%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="b970d-104">Alternatively, you can control the scaling of the image by passing the dimensions of the destination rectangle to the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
 <span data-ttu-id="b970d-105">たとえば、次の呼び出し、<xref:System.Drawing.Graphics.DrawImage%2A>メソッドの左上隅を指定します (50, 30) 先の四角形が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="b970d-105">For example, the following call to the <xref:System.Drawing.Graphics.DrawImage%2A> method specifies an upper-left corner of (50, 30) but does not specify a destination rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 <span data-ttu-id="b970d-106">これは最も簡単なバージョンのですが、<xref:System.Drawing.Graphics.DrawImage%2A>メソッドで必須の引数の数の観点からは最も効率的とは限りません。</span><span class="sxs-lookup"><span data-stu-id="b970d-106">Although this is the easiest version of the <xref:System.Drawing.Graphics.DrawImage%2A> method in terms of the number of required arguments, it is not necessarily the most efficient.</span></span> <span data-ttu-id="b970d-107">解像度がで使用される場合[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)](通常は 96 ドット/インチ) に格納されている解像度とは異なる、<xref:System.Drawing.Image>オブジェクト、<xref:System.Drawing.Graphics.DrawImage%2A>メソッドは、イメージを拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="b970d-107">If the resolution used by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (usually 96 dots per inch) is different from the resolution stored in the <xref:System.Drawing.Image> object, then the <xref:System.Drawing.Graphics.DrawImage%2A> method will scale the image.</span></span> <span data-ttu-id="b970d-108">たとえば、<xref:System.Drawing.Image>オブジェクト 216 ピクセルの幅とのインチあたりのドット数 72 ストアド水平方向の解像度の値があります。</span><span class="sxs-lookup"><span data-stu-id="b970d-108">For example, suppose an <xref:System.Drawing.Image> object has a width of 216 pixels and a stored horizontal resolution value of 72 dots per inch.</span></span> <span data-ttu-id="b970d-109">216/72 が 3、ため<xref:System.Drawing.Graphics.DrawImage%2A>を 1 インチあたり 96 ドットの解像度で 3 インチの幅を持つようにイメージをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="b970d-109">Because 216/72 is 3, <xref:System.Drawing.Graphics.DrawImage%2A> will scale the image so that it has a width of 3 inches at a resolution of 96 dots per inch.</span></span> <span data-ttu-id="b970d-110">つまり、<xref:System.Drawing.Graphics.DrawImage%2A>が 96 x 3 = 288 の幅を持つイメージが表示されます (ピクセル)。</span><span class="sxs-lookup"><span data-stu-id="b970d-110">That is, <xref:System.Drawing.Graphics.DrawImage%2A> will display an image that has a width of 96x3 = 288 pixels.</span></span>  
  
 <span data-ttu-id="b970d-111">画面の解像度が 1 インチあたり 96 ドットと異なる場合でも[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]はおそらくスケール イメージ画面の解像度が 96 ドット/インチであるかのようです。</span><span class="sxs-lookup"><span data-stu-id="b970d-111">Even if your screen resolution is different from 96 dots per inch, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] will probably scale the image as if the screen resolution were 96 dots per inch.</span></span> <span data-ttu-id="b970d-112">だ、 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics>オブジェクトは、デバイス コンテキストに関連付けられてとタイミング[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]結果画面の解像度のデバイス コンテキストは、実際の画面の解像度に関係なく、96 では、通常のクエリ。</span><span class="sxs-lookup"><span data-stu-id="b970d-112">That is because a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> object is associated with a device context, and when [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] queries the device context for the screen resolution, the result is usually 96, regardless of the actual screen resolution.</span></span> <span data-ttu-id="b970d-113">先の四角形を指定することで自動スケーリングを避けることができます、<xref:System.Drawing.Graphics.DrawImage%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="b970d-113">You can avoid automatic scaling by specifying the destination rectangle in the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b970d-114">例</span><span class="sxs-lookup"><span data-stu-id="b970d-114">Example</span></span>  
 <span data-ttu-id="b970d-115">次の例では、2 回、同じイメージを描画します。</span><span class="sxs-lookup"><span data-stu-id="b970d-115">The following example draws the same image twice.</span></span> <span data-ttu-id="b970d-116">最初のケースでは、先の四角形の高さと幅が指定されていないと、イメージが自動的に拡大/縮小します。</span><span class="sxs-lookup"><span data-stu-id="b970d-116">In the first case, the width and height of the destination rectangle are not specified, and the image is automatically scaled.</span></span> <span data-ttu-id="b970d-117">2 番目のケースではの幅と高さ (ピクセル単位で測定) 先の四角形は、幅と、元のイメージの高さと同じであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b970d-117">In the second case, the width and height (measured in pixels) of the destination rectangle are specified to be the same as the width and height of the original image.</span></span> <span data-ttu-id="b970d-118">次の図は、2 回表示されるイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="b970d-118">The following illustration shows the image rendered twice:</span></span>  
  
 ![スケール テクスチャとイメージを示すスクリーン ショット。](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b970d-120">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b970d-120">Compiling the Code</span></span>  
 <span data-ttu-id="b970d-121">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b970d-121">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b970d-122">Texture.jpg をイメージの名前と、システムで有効なパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b970d-122">Replace Texture.jpg with an image name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b970d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b970d-123">See also</span></span>

- [<span data-ttu-id="b970d-124">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="b970d-124">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="b970d-125">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="b970d-125">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
