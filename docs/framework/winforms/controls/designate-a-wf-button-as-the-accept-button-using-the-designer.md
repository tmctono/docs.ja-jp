---
title: デザイナーを使用してボタンを [Accept] ボタンとして指定する
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746067"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="10055-102">方法 : デザイナーを使用して Windows フォームの Button コントロールを承認ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="10055-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="10055-103">任意の Windows フォームで、[accept] ボタンとして <xref:System.Windows.Forms.Button> コントロールを指定できます (既定のボタンとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="10055-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="10055-104">ユーザーが ENTER キーを押すたびに、フォーム上の他のコントロールにフォーカスがあるかどうかに関係なく、既定のボタンがクリックされます。</span><span class="sxs-lookup"><span data-stu-id="10055-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="10055-105">この例外は、フォーカスのあるコントロールが別のボタンである場合です。この場合、フォーカスがあるボタン (複数行のテキストボックス)、または ENTER キーをトラップするカスタムコントロールがクリックされます。</span><span class="sxs-lookup"><span data-stu-id="10055-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>

## <a name="to-designate-the-accept-button"></a><span data-ttu-id="10055-106">Accept ボタンを指定するには</span><span class="sxs-lookup"><span data-stu-id="10055-106">To designate the accept button</span></span>

1. <span data-ttu-id="10055-107">ボタンが存在するフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="10055-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="10055-108">**[プロパティ]** ウィンドウで、フォームの <xref:System.Windows.Forms.Form.AcceptButton%2A> プロパティを <xref:System.Windows.Forms.Button> コントロールの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="10055-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="10055-109">参照</span><span class="sxs-lookup"><span data-stu-id="10055-109">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="10055-110">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="10055-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="10055-111">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="10055-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="10055-112">方法: Windows フォームのボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="10055-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="10055-113">方法: デザイナーを使用して Windows フォームの Button コントロールをキャンセル ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="10055-113">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="10055-114">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="10055-114">Button Control</span></span>](button-control-windows-forms.md)
