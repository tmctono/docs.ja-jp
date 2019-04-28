---
title: '方法: グリッドの子要素を配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: c508f45c1ea3d0925503d6fe5600498a0558d5ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770803"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="8f09f-102">方法: グリッドの子要素を配置する</span><span class="sxs-lookup"><span data-stu-id="8f09f-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="8f09f-103">この例は、get を使用してで定義されているメソッドを設定する方法を示しています。<xref:System.Windows.Controls.Grid>子要素を配置します。</span><span class="sxs-lookup"><span data-stu-id="8f09f-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f09f-104">例</span><span class="sxs-lookup"><span data-stu-id="8f09f-104">Example</span></span>  
 <span data-ttu-id="8f09f-105">次の例では、親<xref:System.Windows.Controls.Grid>要素 (`grid1`) を持つ 3 つの列と 3 つの行。</span><span class="sxs-lookup"><span data-stu-id="8f09f-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="8f09f-106">子<xref:System.Windows.Shapes.Rectangle>要素 (`rect1`) に追加されます、<xref:System.Windows.Controls.Grid>列の位置 0 の行の位置は 0。</span><span class="sxs-lookup"><span data-stu-id="8f09f-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="8f09f-107"><xref:System.Windows.Controls.Button> 要素の位置を指定して呼び出すことができるメソッドを表す、<xref:System.Windows.Shapes.Rectangle>内の要素、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="8f09f-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="8f09f-108">ユーザーは、ボタンをクリックすると、関連メソッドは、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="8f09f-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="8f09f-109">分離コード例では、次の処理方法をボタン<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="8f09f-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="8f09f-110">例では、これらのメソッド呼び出しを書き込みます<xref:System.Windows.Controls.TextBlock>使用に関連する要素が文字列として新しいプロパティ値を出力するメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="8f09f-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="8f09f-111">最終的な結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8f09f-111">Here is the finished result!</span></span>
 
 ![スクリーン ショットは、2 つの列を含む WPF ユーザー インターフェイスを示しています、右側にある 3 x 3 のグリッドがあり、左の列と、グリッドの行の間、色付きの四角形を移動するボタン](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a><span data-ttu-id="8f09f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f09f-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="8f09f-114">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="8f09f-114">Panels Overview</span></span>](panels-overview.md)
