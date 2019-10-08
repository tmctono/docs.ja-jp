---
title: '方法: Enter キーが押されたことを検出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004825"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="e2bd9-102">方法: Enter キーが押されたことを検出する</span><span class="sxs-lookup"><span data-stu-id="e2bd9-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="e2bd9-103">この例では、<xref:System.Windows.Input.Key.Enter> キーがキーボードで押されたことを検出する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e2bd9-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="e2bd9-104">この例は、@no__t 0 ファイルと分離コードファイルで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e2bd9-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2bd9-105">例</span><span class="sxs-lookup"><span data-stu-id="e2bd9-105">Example</span></span>  
 <span data-ttu-id="e2bd9-106">ユーザーが <xref:System.Windows.Controls.TextBox> の @no__t 0 キーを押すと、テキストボックスの入力が @no__t の別の領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2bd9-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="e2bd9-107">次の XAML は、@no__t 0、<xref:System.Windows.Controls.TextBlock>、<xref:System.Windows.Controls.TextBox> で構成されるユーザーインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bd9-107">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="e2bd9-108">次のコードでは、<xref:System.Windows.UIElement.KeyDown> イベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bd9-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="e2bd9-109">押されたキーが @no__t 0 キーの場合、<xref:System.Windows.Controls.TextBlock> にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2bd9-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="e2bd9-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2bd9-110">See also</span></span>

- [<span data-ttu-id="e2bd9-111">入力の概要</span><span class="sxs-lookup"><span data-stu-id="e2bd9-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="e2bd9-112">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="e2bd9-112">Routed Events Overview</span></span>](routed-events-overview.md)
