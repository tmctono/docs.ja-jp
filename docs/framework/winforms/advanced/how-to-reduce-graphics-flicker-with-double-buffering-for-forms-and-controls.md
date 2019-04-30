---
title: '方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: ef05b72b33d3f28d1811389dfae65554a1567d43
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967129"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="2bcdd-102">方法: フォームとコントロールのダブル バッファリングを行うことによってグラフィックスのちらつきを軽減する</span><span class="sxs-lookup"><span data-stu-id="2bcdd-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="2bcdd-103">ダブル バッファリングでは、メモリ バッファーを使用して、複数の描画操作に関連するちらつきの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="2bcdd-104">ダブル バッファリングを有効にすると、すべての描画操作が画面上の描画サーフェイスではなく、最初にメモリ バッファーに描画されます。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="2bcdd-105">描画操作がすべて完了すると、メモリ バッファーが、関連付けられている描画サーフェイスに直接コピーされます。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="2bcdd-106">画面に 1 つだけのグラフィックス操作を実行するため、複雑な描画操作に関連付けられているイメージのちらつきがなくなります。ほとんどのアプリケーションの既定のダブル バッファリングによって提供される、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]最良の結果を提供します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="2bcdd-107">標準の Windows フォーム コントロールは、既定でバッファリング double です。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="2bcdd-108">既定のダブル バッファリング、フォーム内で有効にすることができ、2 つの方法でコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="2bcdd-109">設定するか、<xref:System.Windows.Forms.Control.DoubleBuffered%2A>プロパティを`true`、または呼び出すことができます、<xref:System.Windows.Forms.Control.SetStyle%2A>を設定するメソッド、<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>フラグを`true`します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="2bcdd-110">どちらの方法は、フォームまたはコントロールのダブル バッファリングを既定値を有効にして、グラフィックスのちらつきのないレンダリングを提供します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="2bcdd-111">呼び出す、<xref:System.Windows.Forms.Control.SetStyle%2A>メソッドがすべてのレンダリング コードを記述したカスタム コントロールに対してのみお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="2bcdd-112">アニメーションや高度なメモリ管理より高度なダブル バッファリングのシナリオには、独自のダブル バッファリング ロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="2bcdd-113">詳細については、「[方法 :バッファリングされたグラフィックスを手動で管理](how-to-manually-manage-buffered-graphics.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-113">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="2bcdd-114">ちらつきを軽減するには</span><span class="sxs-lookup"><span data-stu-id="2bcdd-114">To reduce flicker</span></span>  
  
- <span data-ttu-id="2bcdd-115"><xref:System.Windows.Forms.Control.DoubleBuffered%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="2bcdd-116">\- または -</span><span class="sxs-lookup"><span data-stu-id="2bcdd-116">\- or -</span></span>  
  
- <span data-ttu-id="2bcdd-117">呼び出す、<xref:System.Windows.Forms.Control.SetStyle%2A>を設定するメソッド、<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>フラグを`true`します。</span><span class="sxs-lookup"><span data-stu-id="2bcdd-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="2bcdd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bcdd-118">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="2bcdd-119">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="2bcdd-119">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="2bcdd-120">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="2bcdd-120">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
