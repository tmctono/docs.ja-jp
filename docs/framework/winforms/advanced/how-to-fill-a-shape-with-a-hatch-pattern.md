---
title: '方法: ハッチ パターンで図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: f5399c4151b335090f4b93be041375b8c2781afa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781347"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="ff0e9-102">方法: ハッチ パターンで図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="ff0e9-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="ff0e9-103">2 つの色からハッチ パターンが行われます。 バック グラウンドとバック グラウンドでパターンを形成する行のいずれかのいずれか。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="ff0e9-104">ハッチ パターンでは、閉じた図形を塗りつぶすを使用して、<xref:System.Drawing.Drawing2D.HatchBrush>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="ff0e9-105">次の例では、ハッチ パターンで楕円の塗りつぶし方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff0e9-106">例</span><span class="sxs-lookup"><span data-stu-id="ff0e9-106">Example</span></span>  
 <span data-ttu-id="ff0e9-107"><xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A>コンス トラクターは 3 つの引数を受け取ります。 陰影のスタイル、ハッチ線の色および背景の色。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="ff0e9-108">陰影のスタイル引数は、任意の値を指定できます、<xref:System.Drawing.Drawing2D.HatchStyle>列挙体。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="ff0e9-109">50 人を超える要素がある、<xref:System.Drawing.Drawing2D.HatchStyle>列挙体。 いくつかの要素の次のリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="ff0e9-110">次の図は、塗りつぶされた楕円を示します。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="ff0e9-111">![ハッチ パターン](./media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="ff0e9-111">![Hatch Pattern](./media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff0e9-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ff0e9-112">Compiling the Code</span></span>  
 <span data-ttu-id="ff0e9-113">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="ff0e9-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0e9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff0e9-114">See also</span></span>

- [<span data-ttu-id="ff0e9-115">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="ff0e9-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
