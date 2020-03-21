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
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182482"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="b2d8a-102">方法: テキストでのアンチエイリアシングの使用</span><span class="sxs-lookup"><span data-stu-id="b2d8a-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="b2d8a-103">*アンチエイリアシング*とは、描画されたグラフィックスとテキストのギザギザのエッジをスムージングして、外観や読みやすさを向上させます。</span><span class="sxs-lookup"><span data-stu-id="b2d8a-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="b2d8a-104">マネージ GDI+ クラスを使用すると、高品質のアンチエイリアステキストをレンダリングできるだけでなく、低品質のテキストをレンダリングできます。</span><span class="sxs-lookup"><span data-stu-id="b2d8a-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="b2d8a-105">通常、高品質のレンダリングは、低品質のレンダリングよりも処理に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="b2d8a-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="b2d8a-106">テキストの品質レベルを設定するには、列挙<xref:System.Drawing.Graphics.TextRenderingHint%2A>体の要素<xref:System.Drawing.Graphics>の 1 つに a<xref:System.Drawing.Text.TextRenderingHint>のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b2d8a-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2d8a-107">例</span><span class="sxs-lookup"><span data-stu-id="b2d8a-107">Example</span></span>  
 <span data-ttu-id="b2d8a-108">次のコード例では、2 つの異なる品質設定を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="b2d8a-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 <span data-ttu-id="b2d8a-109">次の図は、コード例の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2d8a-109">The following illustration shows the output of the example code:</span></span>  
  
 ![2 つの異なる品質設定を持つテキストを示すスクリーンショット。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2d8a-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b2d8a-111">Compiling the Code</span></span>  
 <span data-ttu-id="b2d8a-112">上記のコード例は Windows フォームで使用するように設計されており、<xref:System.Windows.Forms.PaintEventArgs>`e`のパラメーターである が必要<xref:System.Windows.Forms.PaintEventHandler>です。</span><span class="sxs-lookup"><span data-stu-id="b2d8a-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d8a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2d8a-113">See also</span></span>

- [<span data-ttu-id="b2d8a-114">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="b2d8a-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
