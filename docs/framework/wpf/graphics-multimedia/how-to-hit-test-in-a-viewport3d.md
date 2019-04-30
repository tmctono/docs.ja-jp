---
title: '方法: Viewport3D でヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: c3238161a01df67b05be6284b8eed61981ff3974
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947330"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="1812a-102">方法: Viewport3D でヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="1812a-102">How to: Hit Test in a Viewport3D</span></span>
<span data-ttu-id="1812a-103">この例では、ヒット テストでの 3D ビジュアルの<xref:System.Windows.Controls.Viewport3D>します。</span><span class="sxs-lookup"><span data-stu-id="1812a-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>  
  
 <span data-ttu-id="1812a-104"><xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D および 3D の情報を返します 3D のみの結果を確認するテスト結果を反復処理することができます。</span><span class="sxs-lookup"><span data-stu-id="1812a-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <span data-ttu-id="1812a-105"><xref:System.Windows.Media.HitTestResultBehavior>次のコードでヒット テストの結果を処理する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="1812a-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span>  <span data-ttu-id="1812a-106">`UpdateResultInfo` `UpdateMaterial`はローカルに定義されたメソッド。</span><span class="sxs-lookup"><span data-stu-id="1812a-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a><span data-ttu-id="1812a-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="1812a-107">See also</span></span>

- [<span data-ttu-id="1812a-108">3-D のヒット テストのサンプル</span><span class="sxs-lookup"><span data-stu-id="1812a-108">3-D Hit Testing Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159959)
