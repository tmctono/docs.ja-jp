---
title: '方法: グラデーションに対してガンマ補正を適用します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e7205058bc2b93ac453b8c37bfc8d5236433158d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708083"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="56577-102">方法: グラデーションに対してガンマ補正を適用します。</span><span class="sxs-lookup"><span data-stu-id="56577-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="56577-103">線状グラデーション ブラシのガンマ補正を有効にするには、ブラシのできます<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="56577-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="56577-104">ガンマ補正を無効に設定してできます、<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="56577-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="56577-105">既定では、ガンマ補正が無効です。</span><span class="sxs-lookup"><span data-stu-id="56577-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56577-106">例</span><span class="sxs-lookup"><span data-stu-id="56577-106">Example</span></span>  
 <span data-ttu-id="56577-107">例では、線状グラデーション ブラシを作成し、そのブラシを使用して 2 つの四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="56577-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="56577-108">最初の四角形はガンマ補正を適用せず、ガンマ補正と 2 番目の四角形が入力されます。</span><span class="sxs-lookup"><span data-stu-id="56577-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="56577-109">次の図では、2 つの塗りつぶされた四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="56577-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="56577-110">ガンマ補正が、上部の四角形は、中央の濃いが表示されます。</span><span class="sxs-lookup"><span data-stu-id="56577-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="56577-111">統一された複数の強度がガンマ補正は、下の四角形が表示されます。</span><span class="sxs-lookup"><span data-stu-id="56577-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="56577-112">![グラデーション](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="56577-112">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56577-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="56577-113">Compiling the Code</span></span>  
 <span data-ttu-id="56577-114">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="56577-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56577-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="56577-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [<span data-ttu-id="56577-116">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="56577-116">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
