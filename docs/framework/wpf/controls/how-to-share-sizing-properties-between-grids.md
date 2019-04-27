---
title: '方法: グリッド間でサイズ設定プロパティを共有する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910586"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="035dd-102">方法: グリッド間でサイズ設定プロパティを共有する</span><span class="sxs-lookup"><span data-stu-id="035dd-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="035dd-103">この例は、列のサイズ設定データを共有する方法を示していて、行の間で<xref:System.Windows.Controls.Grid>一貫性のあるサイズ設定するには要素です。</span><span class="sxs-lookup"><span data-stu-id="035dd-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="035dd-104">例</span><span class="sxs-lookup"><span data-stu-id="035dd-104">Example</span></span>  
 <span data-ttu-id="035dd-105">次の例では、2 つを紹介<xref:System.Windows.Controls.Grid>要素の親の子要素として<xref:System.Windows.Controls.DockPanel>します。</span><span class="sxs-lookup"><span data-stu-id="035dd-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="035dd-106"><xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>添付プロパティの<xref:System.Windows.Controls.Grid>親が定義されて<xref:System.Windows.Controls.DockPanel>します。</span><span class="sxs-lookup"><span data-stu-id="035dd-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="035dd-107">例では、2 つを使用してプロパティ値を操作する<xref:System.Windows.Controls.Button>要素は、ブール型プロパティ値の各要素は 1 つ。</span><span class="sxs-lookup"><span data-stu-id="035dd-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="035dd-108">ときに、<xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>プロパティの値に設定されて`true`の各列または行のメンバー、<xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>行または列のコンテンツに関係なく、サイズ設定情報を共有します。</span><span class="sxs-lookup"><span data-stu-id="035dd-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="035dd-109">...</span><span class="sxs-lookup"><span data-stu-id="035dd-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="035dd-110">分離コード例では、次の処理方法をボタン<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="035dd-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="035dd-111">例では、これらのメソッド呼び出しの結果を書き込みます<xref:System.Windows.Controls.TextBlock>使用に関連する要素が文字列として新しいプロパティ値を出力するメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="035dd-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="035dd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="035dd-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="035dd-113">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="035dd-113">Panels Overview</span></span>](panels-overview.md)
