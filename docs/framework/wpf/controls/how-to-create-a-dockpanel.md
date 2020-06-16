---
title: '方法: DockPanel を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], creating
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
ms.openlocfilehash: 35434a13386ae89fdc1428bd632d21c1551c9871
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911124"
---
# <a name="how-to-create-a-dockpanel"></a><span data-ttu-id="e97a2-102">方法: DockPanel を作成する</span><span class="sxs-lookup"><span data-stu-id="e97a2-102">How to: Create a DockPanel</span></span>
## <a name="example"></a><span data-ttu-id="e97a2-103">例</span><span class="sxs-lookup"><span data-stu-id="e97a2-103">Example</span></span>  
 <span data-ttu-id="e97a2-104">次の例では、コードを使用して <xref:System.Windows.Controls.DockPanel> のインスタンスを作成し、使用しています。</span><span class="sxs-lookup"><span data-stu-id="e97a2-104">The following example creates and uses an instance of <xref:System.Windows.Controls.DockPanel> by using code.</span></span> <span data-ttu-id="e97a2-105">この例では、<xref:System.Windows.Shapes.Rectangle> 要素を 5 つ作成し、親 <xref:System.Windows.Controls.DockPanel> の内部にそれらを配置する (ドッキングする) ことで領域をパーティション分割する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e97a2-105">The example shows you how to partition space by creating five <xref:System.Windows.Shapes.Rectangle> elements and positioning (docking) them inside a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="e97a2-106">既定の設定を維持する場合、最終的な四角形では、残りの未割り当て領域がすべて塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="e97a2-106">If you retain the default setting, the final rectangle fills all the remaining unallocated space.</span></span>  
  
 [!code-csharp[DockPanelCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e97a2-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="e97a2-107">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Dock>
- [<span data-ttu-id="e97a2-108">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="e97a2-108">Panels Overview</span></span>](panels-overview.md)
