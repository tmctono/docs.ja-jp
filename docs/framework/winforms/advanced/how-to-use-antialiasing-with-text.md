---
title: '方法: テキストでのアンチエイリアシングの使用'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 080d946bd72da8b76ed846efdf149eb328d66336
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505731"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="f2b13-102">方法: テキストでのアンチエイリアシングの使用</span><span class="sxs-lookup"><span data-stu-id="f2b13-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="f2b13-103">*アンチエイリアシング*ぎざぎざのグラフィックスを描画し、外観と読みやすさを向上させるためにテキストのスムージングを参照します。</span><span class="sxs-lookup"><span data-stu-id="f2b13-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="f2b13-104">マネージ GDI + クラスでは、高品質なアンチ エイリアス化テキストと低品質のテキストを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f2b13-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="f2b13-105">通常、高品質なレンダリングでは、低品質のレンダリングよりも処理時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="f2b13-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="f2b13-106">テキスト品質レベルを設定するには、設定、<xref:System.Drawing.Graphics.TextRenderingHint%2A>のプロパティを<xref:System.Drawing.Graphics>の要素の 1 つに、<xref:System.Drawing.Text.TextRenderingHint>列挙型</span><span class="sxs-lookup"><span data-stu-id="f2b13-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2b13-107">例</span><span class="sxs-lookup"><span data-stu-id="f2b13-107">Example</span></span>  
 <span data-ttu-id="f2b13-108">次のコード例では、2 つの別々 の品質設定でテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="f2b13-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="f2b13-109">次の図は、コード例の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="f2b13-109">The following illustration shows the output of the example code:</span></span>  
  
 ![2 つの別々 の品質設定でテキストを示すスクリーン ショット。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2b13-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f2b13-111">Compiling the Code</span></span>  
 <span data-ttu-id="f2b13-112">上記のコード例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="f2b13-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b13-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2b13-113">See also</span></span>

- [<span data-ttu-id="f2b13-114">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="f2b13-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
