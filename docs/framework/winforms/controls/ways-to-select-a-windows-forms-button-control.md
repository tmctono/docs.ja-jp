---
title: Windows フォームの Button コントロールを選択する方法
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: f2881646a05d257044c6461f822a4c35a225f8c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759844"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="3bb12-102">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="3bb12-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="3bb12-103">次の方法で Windows フォームのボタンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3bb12-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="3bb12-104">マウスを使用して、ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bb12-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="3bb12-105">呼び出す、ボタンの<xref:System.Windows.Forms.Control.Click>コード内のイベント。</span><span class="sxs-lookup"><span data-stu-id="3bb12-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="3bb12-106">TAB キーを押し、ボタンにフォーカスを移動して、ボタンを選択し、space キーまたは ENTER キーを押して。</span><span class="sxs-lookup"><span data-stu-id="3bb12-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="3bb12-107">ボタンの (ALT + 下線付きの文字) のアクセス キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3bb12-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="3bb12-108">アクセス キーの詳細については、次を参照してください。[方法。Windows フォーム コントロールのアクセス キーを作成](how-to-create-access-keys-for-windows-forms-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="3bb12-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="3bb12-109">ボタンがフォームの"accept"ボタンの場合は、ENTER キーを押してボタンを選択、別のコントロールにフォーカスがある場合でも、その他のコントロールが別のボタンや複数行テキスト ボックスでは、enter キーをトラップするカスタム コントロールの場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="3bb12-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="3bb12-110">別のコントロールにフォーカスがある場合でも、ESC キーを押してボタンがフォームの「キャンセル」ボタンの場合に、ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3bb12-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="3bb12-111">呼び出す、<xref:System.Windows.Forms.Button.PerformClick%2A>メソッドをプログラムで、ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3bb12-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb12-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bb12-112">See also</span></span>

- [<span data-ttu-id="3bb12-113">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="3bb12-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="3bb12-114">方法: Windows フォームのボタン クリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="3bb12-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="3bb12-115">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="3bb12-115">Button Control</span></span>](button-control-windows-forms.md)
