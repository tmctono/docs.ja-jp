---
title: '方法: カスタム パネル要素を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: d4fc9d76ada9f27bd52619280b323691af9382c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910963"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="762e4-102">方法: カスタム パネル要素を作成する</span><span class="sxs-lookup"><span data-stu-id="762e4-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="762e4-103">例</span><span class="sxs-lookup"><span data-stu-id="762e4-103">Example</span></span>  
 <span data-ttu-id="762e4-104">この例の既定のレイアウト動作をオーバーライドする方法を示しています、<xref:System.Windows.Controls.Panel>要素から派生したカスタム レイアウト要素を作成および<xref:System.Windows.Controls.Panel>します。</span><span class="sxs-lookup"><span data-stu-id="762e4-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="762e4-105">例では、定義の単純なカスタム<xref:System.Windows.Controls.Panel>と呼ばれる要素`PlotPanel`、に従って 2 つハード コーディングされた x 座標と y 座標の子要素を配置します。</span><span class="sxs-lookup"><span data-stu-id="762e4-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="762e4-106">この例で`x`と`y`に設定されて`50`。 したがって、すべての子要素は、x と y でその場所に配置される軸。</span><span class="sxs-lookup"><span data-stu-id="762e4-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="762e4-107">ユーザー設定を実装する<xref:System.Windows.Controls.Panel>動作、例では、<xref:System.Windows.FrameworkElement.MeasureOverride%2A>と<xref:System.Windows.FrameworkElement.ArrangeOverride%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="762e4-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="762e4-108">各メソッドを返します、<xref:System.Windows.Size>データを配置および子要素をレンダリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="762e4-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="762e4-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="762e4-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="762e4-110">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="762e4-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="762e4-111">カスタム コンテンツ折り返しパネルのサンプルを作成します。</span><span class="sxs-lookup"><span data-stu-id="762e4-111">Create a Custom Content-Wrapping Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159979)
