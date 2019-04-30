---
title: '方法: ときに検出、押されたキーを入力します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051417"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="9205c-102">方法: ときに検出、押されたキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="9205c-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="9205c-103">この例では、ときに検出、<xref:System.Windows.Input.Key.Enter>キーボードのキーが押されました。</span><span class="sxs-lookup"><span data-stu-id="9205c-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="9205c-104">この例は、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルと分離コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="9205c-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9205c-105">例</span><span class="sxs-lookup"><span data-stu-id="9205c-105">Example</span></span>  
 <span data-ttu-id="9205c-106">押されたとき、<xref:System.Windows.Input.Key.Enter>キー、<xref:System.Windows.Controls.TextBox>の別の領域で、テキスト ボックスに入力が表示されます、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9205c-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="9205c-107">次[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]で構成されるユーザー インターフェイスを作成、 <xref:System.Windows.Controls.StackPanel>、 <xref:System.Windows.Controls.TextBlock>、および<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="9205c-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="9205c-108">次のコードを作成、<xref:System.Windows.UIElement.KeyDown>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="9205c-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="9205c-109">押されたキーがある場合、<xref:System.Windows.Input.Key.Enter>でメッセージを表示、キー、<xref:System.Windows.Controls.TextBlock>します。</span><span class="sxs-lookup"><span data-stu-id="9205c-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="9205c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9205c-110">See also</span></span>

- [<span data-ttu-id="9205c-111">入力の概要</span><span class="sxs-lookup"><span data-stu-id="9205c-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="9205c-112">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="9205c-112">Routed Events Overview</span></span>](routed-events-overview.md)
