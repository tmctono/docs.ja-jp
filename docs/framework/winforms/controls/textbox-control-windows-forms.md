---
title: TextBox コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
ms.openlocfilehash: b687f83562b3a6f9dd5993f2af1c55ffe6dc8042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932510"
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="caed5-102">TextBox コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="caed5-102">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="caed5-103">Windows フォームのテキスト ボックスは、ユーザーからの入力を取得する、またはテキストを表示するに使用されます。</span><span class="sxs-lookup"><span data-stu-id="caed5-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="caed5-104">`TextBox`コントロールもできる読み取り専用ですが、通常、編集可能なテキストに使用します。</span><span class="sxs-lookup"><span data-stu-id="caed5-104">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="caed5-105">テキスト ボックスでは、複数の行を表示、テキスト、コントロールのサイズをラップ、および基本的な書式設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="caed5-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="caed5-106">`TextBox`コントロールがテキスト コントロールに表示または入力の 1 つの形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="caed5-106">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="caed5-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="caed5-107">In This Section</span></span>  
 [<span data-ttu-id="caed5-108">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="caed5-108">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="caed5-109">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="caed5-109">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="caed5-110">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御します。</span><span class="sxs-lookup"><span data-stu-id="caed5-110">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="caed5-111">エディット コントロールがフォーカスをまず取得時にカーソルが表示される場所を指定するための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="caed5-111">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="caed5-112">方法: Windows フォーム TextBox コントロールでパスワード テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="caed5-112">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="caed5-113">テキスト ボックスに入力した内容を非表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="caed5-113">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="caed5-114">方法: 読み取り専用テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="caed5-114">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="caed5-115">テキスト ボックスの内容が変更されないようにする方法をについて説明します。</span><span class="sxs-lookup"><span data-stu-id="caed5-115">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="caed5-116">方法: 文字列に引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="caed5-116">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="caed5-117">テキスト ボックスの文字列に引用符を追加するについて説明します。</span><span class="sxs-lookup"><span data-stu-id="caed5-117">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="caed5-118">方法: Windows フォームの TextBox コントロールでテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="caed5-118">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="caed5-119">テキスト ボックス内のテキストを強調表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="caed5-119">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="caed5-120">方法: Windows フォームの TextBox コントロールで複数の行を表示します。</span><span class="sxs-lookup"><span data-stu-id="caed5-120">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="caed5-121">スクロール可能なテキスト ボックスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="caed5-121">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="caed5-122">参照</span><span class="sxs-lookup"><span data-stu-id="caed5-122">Reference</span></span>  
 <span data-ttu-id="caed5-123"><xref:System.Windows.Forms.TextBox> クラス</span><span class="sxs-lookup"><span data-stu-id="caed5-123"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="caed5-124">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="caed5-124">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="caed5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="caed5-125">Related Sections</span></span>  
 [<span data-ttu-id="caed5-126">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="caed5-126">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="caed5-127">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="caed5-127">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
