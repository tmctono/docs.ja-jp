---
title: '方法: デザイナーを使用して Windows フォームの Button コントロールを承認ボタンとして指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: e0eaa90c8450888ea325470db5d4adae555f8d82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972329"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="d8f92-102">方法: デザイナーを使用して Windows フォームの Button コントロールを承認ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="d8f92-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="d8f92-103">任意の Windows フォームで指定することができます、<xref:System.Windows.Forms.Button>コントロールを承認ボタン、既定のボタンとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d8f92-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="d8f92-104">ユーザーが ENTER キーを押すと、フォームの他のコントロールにフォーカスがあるの既定のボタンがクリックされました。</span><span class="sxs-lookup"><span data-stu-id="d8f92-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="d8f92-105">フォーカスを持つコントロールが別のボタン例外:、フォーカスのあるボタンをクリックする場合、-複数行テキスト ボックス、または ENTER キーをトラップするカスタム コントロール。</span><span class="sxs-lookup"><span data-stu-id="d8f92-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8f92-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8f92-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d8f92-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8f92-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d8f92-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8f92-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="d8f92-109">同意する ボタンを指定するには</span><span class="sxs-lookup"><span data-stu-id="d8f92-109">To designate the accept button</span></span>  
  
1. <span data-ttu-id="d8f92-110">ボタンが存在するフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8f92-110">Select the form on which the button resides.</span></span>  
  
2. <span data-ttu-id="d8f92-111">**プロパティ**ウィンドウで、設定フォームの<xref:System.Windows.Forms.Form.AcceptButton%2A>プロパティを<xref:System.Windows.Forms.Button>コントロールの名前。</span><span class="sxs-lookup"><span data-stu-id="d8f92-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f92-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8f92-112">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="d8f92-113">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="d8f92-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="d8f92-114">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="d8f92-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="d8f92-115">方法: Windows フォームのボタン クリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="d8f92-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- <span data-ttu-id="d8f92-116">[方法: デザイナーを使用して、[キャンセル] ボタンとして Windows フォームの Button を指定します。](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)</span><span class="sxs-lookup"><span data-stu-id="d8f92-116">[How to: Designate a Windows Forms Button as the Cancel Button Using the Designer](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)</span></span>
- [<span data-ttu-id="d8f92-117">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="d8f92-117">Button Control</span></span>](button-control-windows-forms.md)
