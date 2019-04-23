---
title: '方法: どの修飾子キーが押されたかを判断する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 571af49cdf82b876cfb72a7c7636874c8d155fb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213937"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="fd8af-102">方法: どの修飾子キーが押されたかを判断する</span><span class="sxs-lookup"><span data-stu-id="fd8af-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="fd8af-103">ユーザーのキーボード操作を許可しているアプリケーションを作成するときの SHIFT、ALT、CTRL キーなどの修飾子キーを監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd8af-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="fd8af-104">他のキーまたはマウス クリックで、組み合わせて修飾子キーが押された、ときに、アプリケーションが適切に応答できます。</span><span class="sxs-lookup"><span data-stu-id="fd8af-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="fd8af-105">たとえば、s が押された場合、画面に表示する"s"が生じるだけですが、ctrl キーを押しながら S キーを押すと、現在のドキュメントが保存されます。</span><span class="sxs-lookup"><span data-stu-id="fd8af-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="fd8af-106">処理する場合、<xref:System.Windows.Forms.Control.KeyDown>イベント、<xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A>のプロパティ、<xref:System.Windows.Forms.KeyEventArgs>受信したイベント ハンドラーを指定しますどの修飾子キーが押されました。</span><span class="sxs-lookup"><span data-stu-id="fd8af-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="fd8af-107">または、<xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>プロパティの<xref:System.Windows.Forms.KeyEventArgs>もビットごとの OR と組み合わせると修飾子キーが押された文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd8af-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="fd8af-108">ただし、処理する場合、<xref:System.Windows.Forms.Control.KeyPress>イベントまたはマウス イベント、イベント ハンドラーは、この情報を受信しません。</span><span class="sxs-lookup"><span data-stu-id="fd8af-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="fd8af-109">この場合、使用する必要があります、<xref:System.Windows.Forms.Control.ModifierKeys%2A>のプロパティ、<xref:System.Windows.Forms.Control>クラス。</span><span class="sxs-lookup"><span data-stu-id="fd8af-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="fd8af-110">どちらの場合、適切なビットごとの AND を実行する必要があります<xref:System.Windows.Forms.Keys>値およびテストする値。</span><span class="sxs-lookup"><span data-stu-id="fd8af-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="fd8af-111"><xref:System.Windows.Forms.Keys>列挙には、バリエーションの各修飾子キーは、ため、ビット演算を実行することが重要と適切な値が提供しています。</span><span class="sxs-lookup"><span data-stu-id="fd8af-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="fd8af-112">たとえば、SHIFT キーがによって表される<xref:System.Windows.Forms.Keys.Shift>、 <xref:System.Windows.Forms.Keys.ShiftKey>、<xref:System.Windows.Forms.Keys.RShiftKey>と<xref:System.Windows.Forms.Keys.LShiftKey>修飾子キーと shift キーをテストする適切な値<xref:System.Windows.Forms.Keys.Shift>します。</span><span class="sxs-lookup"><span data-stu-id="fd8af-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="fd8af-113">同様に、修飾子として ctrl キーと alt キーをテストする必要がありますを使用して、<xref:System.Windows.Forms.Keys.Control>と<xref:System.Windows.Forms.Keys.Alt>それぞれ値します。</span><span class="sxs-lookup"><span data-stu-id="fd8af-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd8af-114">Visual Basic プログラマにとっては、を通じてキーの情報にもアクセスできます、<xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>プロパティ</span><span class="sxs-lookup"><span data-stu-id="fd8af-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="fd8af-115">どの修飾子キーが押されたかを判断するには</span><span class="sxs-lookup"><span data-stu-id="fd8af-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="fd8af-116">ビットごとの使用`AND`演算子と共に、<xref:System.Windows.Forms.Control.ModifierKeys%2A>プロパティと値の<xref:System.Windows.Forms.Keys>特定の修飾子キーが押されたかどうかを決定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="fd8af-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="fd8af-117">次のコード例で、SHIFT キーが押されたかどうかを確認する方法を示しています、<xref:System.Windows.Forms.Control.KeyPress>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="fd8af-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="fd8af-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd8af-118">See also</span></span>

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="fd8af-119">Windows フォーム アプリケーションにおけるキーボード入力</span><span class="sxs-lookup"><span data-stu-id="fd8af-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- <span data-ttu-id="fd8af-120">[方法: 場合の CapsLock がオンに Visual Basic で確認します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fd8af-120">[How to: Determine If CapsLock is On in Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span></span>
