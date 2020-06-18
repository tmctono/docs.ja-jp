---
title: '方法: グリッドの子要素を配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186717"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="0f2c5-102">方法: グリッドの子要素を配置する</span><span class="sxs-lookup"><span data-stu-id="0f2c5-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="0f2c5-103">この例では、<xref:System.Windows.Controls.Grid> で定義されている get メソッドと set メソッドを使用して、子要素を配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f2c5-104">例</span><span class="sxs-lookup"><span data-stu-id="0f2c5-104">Example</span></span>  
 <span data-ttu-id="0f2c5-105">次の例では、3 つの列と 3 つの行を持つ親 <xref:System.Windows.Controls.Grid> 要素 (`grid1`) を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="0f2c5-106">子 <xref:System.Windows.Shapes.Rectangle> 要素 (`rect1`) は、列位置 0、行位置 0 の <xref:System.Windows.Controls.Grid> に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="0f2c5-107"><xref:System.Windows.Controls.Button> 要素によって表されるメソッドを呼び出すことで、<xref:System.Windows.Controls.Grid> 内の <xref:System.Windows.Shapes.Rectangle> 要素の位置を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="0f2c5-108">ユーザーがボタンをクリックすると、関連するメソッドがアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="0f2c5-109">次のコードビハインドの例では、ボタンの <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントが発生するメソッドが処理されています。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="0f2c5-110">この例では、これらのメソッドの呼び出しが <xref:System.Windows.Controls.TextBlock> 要素に書き込まれ、そこで関連する get メソッドを使用して新しいプロパティ値が文字列として出力されます。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="0f2c5-111">完成した結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f2c5-111">Here is the finished result!</span></span>

 ![2 つの列を持つ WPF ユーザー インターフェイスを示すスクリーンショット。右側には 3 × 3 のグリッドがあり、左側にはグリッドの列と行の間で色付きの四角形を移動するボタンがある](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="0f2c5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f2c5-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="0f2c5-114">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="0f2c5-114">Panels Overview</span></span>](panels-overview.md)
