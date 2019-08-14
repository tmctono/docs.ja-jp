---
title: '方法: 読み取り専用のテキストボックスを作成する (Windows フォーム)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 18d2f5ed2530957487ac25c3eb6240f8bc50a938
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971943"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="dbe29-102">方法: 読み取り専用のテキストボックスを作成する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="dbe29-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="dbe29-103">編集可能な Windows フォームテキストボックスを読み取り専用のコントロールに変換できます。</span><span class="sxs-lookup"><span data-stu-id="dbe29-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="dbe29-104">たとえば、テキストボックスには通常は編集されているが、現在はアプリケーションの状態によっては編集されていない値が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbe29-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="dbe29-105">読み取り専用のテキストボックスを作成するには</span><span class="sxs-lookup"><span data-stu-id="dbe29-105">To create a read-only text box</span></span>

1. <span data-ttu-id="dbe29-106">コントロールの<xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>プロパティをに`true`設定します。 <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="dbe29-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="dbe29-107">プロパティがに`true`設定されている場合でも、ユーザーはテキストボックス内のテキストをスクロールして強調表示することができ、変更は許可されません。</span><span class="sxs-lookup"><span data-stu-id="dbe29-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="dbe29-108">**Copy**コマンドはテキストボックスで機能しますが、**切り取り**と**貼り付け**のコマンドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="dbe29-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dbe29-109">プロパティ<xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>は、実行時のユーザーの操作にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="dbe29-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="dbe29-110">テキストボックスの内容は、テキストボックスのプロパティを変更すること<xref:System.Windows.Forms.TextBox.Text%2A>で、実行時にプログラムによって変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbe29-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbe29-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbe29-111">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="dbe29-112">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="dbe29-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="dbe29-113">方法: Windows フォーム TextBox コントロールでのカーソル位置の制御</span><span class="sxs-lookup"><span data-stu-id="dbe29-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="dbe29-114">方法: Windows フォーム TextBox コントロールを使用してパスワードテキストボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="dbe29-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="dbe29-115">方法: 文字列内に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="dbe29-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="dbe29-116">方法: Windows フォーム TextBox コントロールでのテキストの選択</span><span class="sxs-lookup"><span data-stu-id="dbe29-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="dbe29-117">方法: Windows フォーム TextBox コントロールで複数の行を表示する</span><span class="sxs-lookup"><span data-stu-id="dbe29-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="dbe29-118">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="dbe29-118">TextBox Control</span></span>](textbox-control-windows-forms.md)
