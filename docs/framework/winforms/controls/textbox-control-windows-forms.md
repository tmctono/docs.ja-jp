---
title: TextBox コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
ms.openlocfilehash: 7bdca52e62b6e7b014d28478b291a1157486527b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742785"
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="f04aa-102">TextBox コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="f04aa-102">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="f04aa-103">Windows フォームテキストボックスを使用して、ユーザーからの入力を取得したり、テキストを表示したりします。</span><span class="sxs-lookup"><span data-stu-id="f04aa-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="f04aa-104">`TextBox` コントロールは、通常、編集可能なテキストに使用されますが、読み取り専用にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f04aa-104">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="f04aa-105">テキストボックスでは、複数の行を表示したり、テキストをコントロールのサイズに折り返したり、基本的な書式を追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="f04aa-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="f04aa-106">`TextBox` コントロールでは、コントロールに表示または入力されるテキストに対して1つの形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f04aa-106">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f04aa-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f04aa-107">In This Section</span></span>  
 [<span data-ttu-id="f04aa-108">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f04aa-108">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="f04aa-109">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-109">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="f04aa-110">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="f04aa-110">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="f04aa-111">エディットコントロールがフォーカスを取得するときに挿入ポイントが表示される位置を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-111">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="f04aa-112">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="f04aa-112">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="f04aa-113">テキストボックスに入力された内容を非表示にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-113">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="f04aa-114">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="f04aa-114">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="f04aa-115">テキストボックスの内容が変更されないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-115">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="f04aa-116">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="f04aa-116">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="f04aa-117">テキストボックス内の文字列に引用符を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-117">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="f04aa-118">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="f04aa-118">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="f04aa-119">テキストボックス内のテキストを強調表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-119">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="f04aa-120">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="f04aa-120">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="f04aa-121">テキストボックスをスクロール可能にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-121">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f04aa-122">リファレンス</span><span class="sxs-lookup"><span data-stu-id="f04aa-122">Reference</span></span>  
 <span data-ttu-id="f04aa-123"><xref:System.Windows.Forms.TextBox> クラス</span><span class="sxs-lookup"><span data-stu-id="f04aa-123"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="f04aa-124">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-124">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f04aa-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f04aa-125">Related Sections</span></span>  
 [<span data-ttu-id="f04aa-126">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="f04aa-126">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="f04aa-127">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="f04aa-127">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
