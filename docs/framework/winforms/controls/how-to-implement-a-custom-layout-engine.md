---
title: '方法: カスタム レイアウト エンジンを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: 8e5043e2b42b1e7449c6dab51691b6d57e28cd53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772696"
---
# <a name="how-to-implement-a-custom-layout-engine"></a><span data-ttu-id="ed6f5-102">方法: カスタム レイアウト エンジンを実装する</span><span class="sxs-lookup"><span data-stu-id="ed6f5-102">How to: Implement a Custom Layout Engine</span></span>
<span data-ttu-id="ed6f5-103">次のコード例では、単純なフロー レイアウトを実行するカスタム レイアウト エンジンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ed6f5-103">The following code example demonstrates how to create a custom layout engine that performs a simple flow layout.</span></span> <span data-ttu-id="ed6f5-104">という名前のパネル コントロールを実装して`DemoFlowPanel`が優先されます、<xref:System.Windows.Forms.Control.LayoutEngine%2A>のインスタンスを指定するプロパティ、`DemoFlowLayout`クラス。</span><span class="sxs-lookup"><span data-stu-id="ed6f5-104">It implements a panel control named `DemoFlowPanel`, which overrides the <xref:System.Windows.Forms.Control.LayoutEngine%2A> property to provide an instance of the `DemoFlowLayout` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed6f5-105">例</span><span class="sxs-lookup"><span data-stu-id="ed6f5-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ed6f5-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed6f5-106">See also</span></span>

- <xref:System.Windows.Forms.Layout.LayoutEngine>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
