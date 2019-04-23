---
title: '方法: フォーカス イベントを使用して要素の色を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 744963cc543110121a777e1d4c3cdcb3cec40d9e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217641"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="08005-102">方法: フォーカス イベントを使用して要素の色を変更する</span><span class="sxs-lookup"><span data-stu-id="08005-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="08005-103">この例を取得しを使用してフォーカスを失ったときに、要素の色を変更する方法を示しています、<xref:System.Windows.UIElement.GotFocus>と<xref:System.Windows.UIElement.LostFocus>イベント。</span><span class="sxs-lookup"><span data-stu-id="08005-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="08005-104">この例は、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルと分離コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="08005-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08005-105">例</span><span class="sxs-lookup"><span data-stu-id="08005-105">Example</span></span>  
 <span data-ttu-id="08005-106">次[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]の 2 つで構成されるユーザー インターフェイスを作成します。<xref:System.Windows.Controls.Button>オブジェクト、およびイベント ハンドラーをアタッチします、<xref:System.Windows.UIElement.GotFocus>と<xref:System.Windows.UIElement.LostFocus>イベントを、<xref:System.Windows.Controls.Button>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08005-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="08005-107">次のコードを作成、<xref:System.Windows.UIElement.GotFocus>と<xref:System.Windows.UIElement.LostFocus>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="08005-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="08005-108">ときに、<xref:System.Windows.Controls.Button>キーボード フォーカスの向上、<xref:System.Windows.Controls.Control.Background%2A>の<xref:System.Windows.Controls.Button>赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="08005-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="08005-109">ときに、<xref:System.Windows.Controls.Button>がキーボード フォーカスを失う、<xref:System.Windows.Controls.Control.Background%2A>の<xref:System.Windows.Controls.Button>が白に変更します。</span><span class="sxs-lookup"><span data-stu-id="08005-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="08005-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="08005-110">See also</span></span>

- [<span data-ttu-id="08005-111">入力の概要</span><span class="sxs-lookup"><span data-stu-id="08005-111">Input Overview</span></span>](input-overview.md)
