---
title: '方法: パネルの OnRender メソッドをオーバーライドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666716"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="8e73e-102">方法: パネルの OnRender メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="8e73e-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="8e73e-103">この例では、レイアウト要素<xref:System.Windows.Controls.Panel.OnRender%2A>にカスタム<xref:System.Windows.Controls.Panel>のグラフィカル効果を追加するために、のメソッドをオーバーライドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8e73e-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e73e-104">例</span><span class="sxs-lookup"><span data-stu-id="8e73e-104">Example</span></span>  
 <span data-ttu-id="8e73e-105">レンダリングさ<xref:System.Windows.Controls.Panel.OnRender%2A>れた panel 要素にグラフィカルな効果を追加するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e73e-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="8e73e-106">たとえば、このメソッドを使用して、カスタムの罫線または背景効果を追加できます。</span><span class="sxs-lookup"><span data-stu-id="8e73e-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="8e73e-107"><xref:System.Windows.Media.DrawingContext>オブジェクトは、図形、テキスト、画像、またはビデオを描画するためのメソッドを提供する引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="8e73e-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="8e73e-108">このため、このメソッドは、panel オブジェクトをカスタマイズする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8e73e-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8e73e-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e73e-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="8e73e-110">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="8e73e-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="8e73e-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8e73e-111">How-to Topics</span></span>](panel-how-to-topics.md)
