---
title: ボタンを承認ボタンとして指定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142148"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="f8be2-102">方法 : Windows フォームの Button コントロールを承認ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="f8be2-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="f8be2-103">どの Windows フォームでも、コントロールを<xref:System.Windows.Forms.Button>既定のボタンとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="f8be2-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="f8be2-104">ユーザーが Enter キーを押すと、フォーム上の他のコントロールにフォーカスが置かねな場合でも、既定のボタンがクリックされます。</span><span class="sxs-lookup"><span data-stu-id="f8be2-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8be2-105">ただし、フォーカスのあるコントロールが別のボタンである場合は例外です 。</span><span class="sxs-lookup"><span data-stu-id="f8be2-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="f8be2-106">[同意] ボタンを指定するには</span><span class="sxs-lookup"><span data-stu-id="f8be2-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="f8be2-107">フォームの<xref:System.Windows.Forms.Form.AcceptButton%2A>プロパティを適切な<xref:System.Windows.Forms.Button>コントロールに設定します。</span><span class="sxs-lookup"><span data-stu-id="f8be2-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f8be2-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8be2-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="f8be2-109">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f8be2-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="f8be2-110">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="f8be2-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="f8be2-111">方法 : Windows フォームのボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="f8be2-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="f8be2-112">方法 : Windows フォームの Button コントロールをキャンセル ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="f8be2-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="f8be2-113">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="f8be2-113">Button Control</span></span>](button-control-windows-forms.md)
