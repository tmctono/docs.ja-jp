---
title: '方法: グラデーションに対してガンマ補正を適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 066ccc649105018d20cb86b6e576a1a238e0dc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973267"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="b3d47-102">方法: グラデーションに対してガンマ補正を適用する</span><span class="sxs-lookup"><span data-stu-id="b3d47-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="b3d47-103">線状グラデーション ブラシのガンマ補正を有効にするには、ブラシのできます<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="b3d47-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="b3d47-104">ガンマ補正を無効に設定してできます、<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="b3d47-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="b3d47-105">既定では、ガンマ補正が無効です。</span><span class="sxs-lookup"><span data-stu-id="b3d47-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3d47-106">例</span><span class="sxs-lookup"><span data-stu-id="b3d47-106">Example</span></span>  

<span data-ttu-id="b3d47-107">次の例は、コントロールから呼び出されるメソッド<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="b3d47-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b3d47-108">例では、線状グラデーション ブラシを作成し、そのブラシを使用して 2 つの四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="b3d47-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="b3d47-109">最初の四角形はガンマ補正を適用せず、ガンマ補正と 2 番目の四角形が入力されます。</span><span class="sxs-lookup"><span data-stu-id="b3d47-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="b3d47-110">次の図では、2 つの塗りつぶされた四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="b3d47-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="b3d47-111">ガンマ補正が、上部の四角形は、中央の濃いが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3d47-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="b3d47-112">統一された複数の強度がガンマ補正は、下の四角形が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3d47-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="b3d47-113">![グラデーション](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="b3d47-113">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3d47-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b3d47-114">Compiling the Code</span></span>  
 <span data-ttu-id="b3d47-115">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b3d47-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d47-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3d47-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="b3d47-117">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="b3d47-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
