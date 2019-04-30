---
title: '方法: Windows フォームの Button コントロールをキャンセル ボタンとして指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 8170190145e76a86f5343bc42b39be7fb9d61a0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010723"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="2e4d8-102">方法: Windows フォームの Button コントロールをキャンセル ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="2e4d8-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="2e4d8-103">任意の Windows フォームで指定することができます、<xref:System.Windows.Forms.Button>コントロールをキャンセル ボタン。</span><span class="sxs-lookup"><span data-stu-id="2e4d8-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="2e4d8-104">ユーザーがフォーム上の他のコントロールにフォーカスがあるか、ESC キーを押すと [キャンセル] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e4d8-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="2e4d8-105">このようなボタンは通常、ユーザーは、すばやく操作をコミットせずに操作を終了できるようにする設定します。</span><span class="sxs-lookup"><span data-stu-id="2e4d8-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="2e4d8-106">[キャンセル] ボタンを指定するには</span><span class="sxs-lookup"><span data-stu-id="2e4d8-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="2e4d8-107">フォームの設定<xref:System.Windows.Forms.Form.CancelButton%2A>プロパティを適切な<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="2e4d8-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2e4d8-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e4d8-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="2e4d8-109">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2e4d8-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="2e4d8-110">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="2e4d8-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="2e4d8-111">方法: Windows フォームのボタン クリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="2e4d8-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="2e4d8-112">方法: Windows フォームの Button を承認ボタンとして指定します。</span><span class="sxs-lookup"><span data-stu-id="2e4d8-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="2e4d8-113">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="2e4d8-113">Button Control</span></span>](button-control-windows-forms.md)
