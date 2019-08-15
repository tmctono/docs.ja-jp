---
title: '方法: デザイナーを使用して Windows フォーム コントロールのアクセス キーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039523"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="c8898-102">方法: デザイナーを使用して Windows フォーム コントロールのアクセス キーを作成する</span><span class="sxs-lookup"><span data-stu-id="c8898-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="c8898-103">*アクセスキー*は、メニュー、メニュー項目、またはボタンなどのコントロールのラベルのテキスト内の下線付きの文字です。</span><span class="sxs-lookup"><span data-stu-id="c8898-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="c8898-104">これにより、ユーザーは ALT キーを定義済みのアクセスキーと組み合わせて押すことで、ボタンを "クリック" できます。</span><span class="sxs-lookup"><span data-stu-id="c8898-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="c8898-105">たとえば、ボタンがフォームを印刷するためのプロシージャを実行し、その`Text`プロパティが "print" に設定されている場合、文字 "p" の前にアンパサンド (&) を追加すると、実行時にボタンのテキストに文字 "p" が下線付きで表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8898-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="c8898-106">ユーザーは、ALT + P キーを押して、ボタンに関連付けられているコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c8898-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="c8898-107">フォーカスを受け取ることができないコントロールのアクセスキーを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="c8898-107">You cannot have an access key for a control that cannot receive focus.</span></span>

## <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="c8898-108">コントロールのアクセスキーを作成するには</span><span class="sxs-lookup"><span data-stu-id="c8898-108">To create an access key for a control</span></span>

1. <span data-ttu-id="c8898-109">**[プロパティ]** ウィンドウで、 `Text`プロパティを、アクセスキーにする文字の前にアンパサンド (&) を含む文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8898-109">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="c8898-110">たとえば、文字 "P" をアクセスキーとして設定するには、「 **& Print** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c8898-110">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8898-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8898-111">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="c8898-112">方法: Windows フォームボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="c8898-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="c8898-113">方法: Windows フォームコントロールによって表示されるテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="c8898-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="c8898-114">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="c8898-114">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
