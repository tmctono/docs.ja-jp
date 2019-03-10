---
title: '方法: セットのペンの幅と配置'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: e82f406b4fdca93df7a811eea5506846d56fda28
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703050"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="02e75-102">方法: セットのペンの幅と配置</span><span class="sxs-lookup"><span data-stu-id="02e75-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="02e75-103">作成するときに、 <xref:System.Drawing.Pen>、コンス トラクターに引数の 1 つとして、ペンの幅を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="02e75-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="02e75-104">ペンの幅を変更することも、<xref:System.Drawing.Pen.Width%2A>のプロパティ、<xref:System.Drawing.Pen>クラス。</span><span class="sxs-lookup"><span data-stu-id="02e75-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="02e75-105">理論上の線は、幅は 0 です。</span><span class="sxs-lookup"><span data-stu-id="02e75-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="02e75-106">1 ピクセルの幅の線を描画するときに、理論上の線のピクセルが中央揃えされます。</span><span class="sxs-lookup"><span data-stu-id="02e75-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="02e75-107">1 つ以上のピクセル幅の線を描画する場合、ピクセルは理論上の線の中央揃えするかまたは、理論上の線の一方の側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="02e75-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="02e75-108">ペンの配置プロパティを設定することができます、<xref:System.Drawing.Pen>理論上の線を基準とのペンで描画されるピクセルの配置方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="02e75-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="02e75-109">値<xref:System.Drawing.Drawing2D.PenAlignment.Center>、 <xref:System.Drawing.Drawing2D.PenAlignment.Outset>、および<xref:System.Drawing.Drawing2D.PenAlignment.Inset>、次に表示されるコードの例のメンバーである、<xref:System.Drawing.Drawing2D.PenAlignment>列挙体。</span><span class="sxs-lookup"><span data-stu-id="02e75-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="02e75-110">次のコード例が 2 回線を描画します。 幅 1 の黒色のペンで 1 回と 1 回の幅が 10 の緑色のペンを使用します。</span><span class="sxs-lookup"><span data-stu-id="02e75-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="02e75-111">ペンの幅を変更するには</span><span class="sxs-lookup"><span data-stu-id="02e75-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="02e75-112">値を設定、<xref:System.Drawing.Pen.Alignment%2A>プロパティを<xref:System.Drawing.Drawing2D.PenAlignment.Center>(既定) に緑のペンで描画されるピクセルが理論上の線の中央揃えにするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="02e75-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="02e75-113">次の図は、その結果、行を示します。</span><span class="sxs-lookup"><span data-stu-id="02e75-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="02e75-114">![ペン](./media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="02e75-114">![Pens](./media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="02e75-115">次のコード例が 2 回四角形を描画します。 黒のペンの幅が 1 で 1 回と緑のペンの幅が 10 で 1 回です。</span><span class="sxs-lookup"><span data-stu-id="02e75-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="02e75-116">ペンのアラインメントを変更するには</span><span class="sxs-lookup"><span data-stu-id="02e75-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="02e75-117">値を設定、<xref:System.Drawing.Pen.Alignment%2A>プロパティを<xref:System.Drawing.Drawing2D.PenAlignment.Center>四角形の境界に緑のペンで描画されるピクセルに表示することを指定します。</span><span class="sxs-lookup"><span data-stu-id="02e75-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="02e75-118">次の図は、結果として得られる四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="02e75-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="02e75-119">![ペン](./media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="02e75-119">![Pens](./media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="02e75-120">ペンを作成するには</span><span class="sxs-lookup"><span data-stu-id="02e75-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="02e75-121">上記のコード例では、3 番目のステートメントを次のように変更することで、緑色のペンの配置を変更します。</span><span class="sxs-lookup"><span data-stu-id="02e75-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="02e75-122">今すぐ次の図に示すようには、四角形の内側にワイド緑の線のピクセルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02e75-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="02e75-123">![ペン](./media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="02e75-123">![Pens](./media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e75-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="02e75-124">See also</span></span>
- [<span data-ttu-id="02e75-125">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="02e75-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="02e75-126">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="02e75-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
