---
title: '方法 : フォーカス イベントを使用して要素の色を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004838"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="954af-102">方法 : フォーカス イベントを使用して要素の色を変更する</span><span class="sxs-lookup"><span data-stu-id="954af-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="954af-103">この例では、<xref:System.Windows.UIElement.GotFocus> イベントと <xref:System.Windows.UIElement.LostFocus> イベントを使用して、要素が取得され、フォーカスを失ったときに、その色を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="954af-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="954af-104">この例は、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ファイルと分離コードファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="954af-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="954af-105">例</span><span class="sxs-lookup"><span data-stu-id="954af-105">Example</span></span>  
 <span data-ttu-id="954af-106">次の XAML は、2つの <xref:System.Windows.Controls.Button> オブジェクトで構成されるユーザーインターフェイスを作成し、<xref:System.Windows.UIElement.GotFocus> イベントと <xref:System.Windows.UIElement.LostFocus> イベントのイベントハンドラーを <xref:System.Windows.Controls.Button> オブジェクトにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="954af-106">The following XAML creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="954af-107">次のコードでは、<xref:System.Windows.UIElement.GotFocus> と <xref:System.Windows.UIElement.LostFocus> のイベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="954af-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="954af-108"><xref:System.Windows.Controls.Button> がキーボードフォーカスを取得すると、<xref:System.Windows.Controls.Button> の <xref:System.Windows.Controls.Control.Background%2A> が赤に変更されます。</span><span class="sxs-lookup"><span data-stu-id="954af-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="954af-109"><xref:System.Windows.Controls.Button> がキーボードフォーカスを失うと、<xref:System.Windows.Controls.Button> の <xref:System.Windows.Controls.Control.Background%2A> が白に戻されます。</span><span class="sxs-lookup"><span data-stu-id="954af-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="954af-110">参照</span><span class="sxs-lookup"><span data-stu-id="954af-110">See also</span></span>

- [<span data-ttu-id="954af-111">入力の概要</span><span class="sxs-lookup"><span data-stu-id="954af-111">Input Overview</span></span>](input-overview.md)
