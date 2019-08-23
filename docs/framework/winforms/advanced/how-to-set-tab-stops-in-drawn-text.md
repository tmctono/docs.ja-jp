---
title: '方法: 描画されたテキストにタブ ストップを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947819"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="4f11e-102">方法: 描画されたテキストにタブ ストップを設定する</span><span class="sxs-lookup"><span data-stu-id="4f11e-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="4f11e-103"><xref:System.Drawing.StringFormat.SetTabStops%2A> オブジェクトのメソッドを<xref:System.Drawing.StringFormat>呼び出して<xref:System.Drawing.Graphics.DrawString%2A> 、<xref:System.Drawing.Graphics>そのオブジェクトをクラスのメソッドに渡すことで、テキストのタブストップを設定できます。 <xref:System.Drawing.StringFormat></span><span class="sxs-lookup"><span data-stu-id="4f11e-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f11e-104">は<xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> 、描画されたテキストへのタブストップの追加をサポートしていません<xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType>が、フラグを使用して既存のタブストップを展開することはできます。</span><span class="sxs-lookup"><span data-stu-id="4f11e-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f11e-105">例</span><span class="sxs-lookup"><span data-stu-id="4f11e-105">Example</span></span>  
 <span data-ttu-id="4f11e-106">次の例では、150、250、および350でタブストップを設定します。</span><span class="sxs-lookup"><span data-stu-id="4f11e-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="4f11e-107">次に、コードは、名前とテストスコアのタブ付きリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="4f11e-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="4f11e-108">次の図は、タブ付きテキストを示しています。</span><span class="sxs-lookup"><span data-stu-id="4f11e-108">The following illustration shows the tabbed text:</span></span>  
  
 ![タブ付きの名前とスコアの一覧を示すスクリーンショット。](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="4f11e-110">次のコードでは、 <xref:System.Drawing.StringFormat.SetTabStops%2A>メソッドに2つの引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="4f11e-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="4f11e-111">2番目の引数は、タブオフセットを格納する配列です。</span><span class="sxs-lookup"><span data-stu-id="4f11e-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="4f11e-112">に<xref:System.Drawing.StringFormat.SetTabStops%2A>渡される最初の引数は0です。これは、配列内の最初のオフセットが、外接する四角形の左端である位置0から測定されることを示します。</span><span class="sxs-lookup"><span data-stu-id="4f11e-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f11e-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4f11e-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="4f11e-114">前の例は、Windows フォームで使用するように設計さ<xref:System.Windows.Forms.PaintEventArgs>れています。これ<xref:System.Windows.Forms.PaintEventHandler>は、のパラメーターであるを必要`e`とします。</span><span class="sxs-lookup"><span data-stu-id="4f11e-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f11e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f11e-115">See also</span></span>

- [<span data-ttu-id="4f11e-116">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="4f11e-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="4f11e-117">方法: GDI を使用してテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="4f11e-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
