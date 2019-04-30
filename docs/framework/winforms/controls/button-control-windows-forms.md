---
title: Button コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- buttons
- Button control [Windows Forms]
ms.assetid: d38bc40c-8040-4f19-9e88-2c665b0ab80b
ms.openlocfilehash: a71079b45259aab54480a5b97c09844b73be1661
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961591"
---
# <a name="button-control-windows-forms"></a><span data-ttu-id="46c66-102">Button コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="46c66-102">Button Control (Windows Forms)</span></span>
<span data-ttu-id="46c66-103">Windows フォームの `Button` コントロールを使用すると、ユーザーはそれをクリックしてアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="46c66-103">The Windows Forms `Button` control allows the user to click it to perform an action.</span></span> <span data-ttu-id="46c66-104">`Button` コントロールには、テキストとイメージの両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="46c66-104">The `Button` control can display both text and images.</span></span> <span data-ttu-id="46c66-105">ボタンをクリックすると、ボタンを実際に押して離したかのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="46c66-105">When the button is clicked, it looks as if it is being pushed in and released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46c66-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="46c66-106">In This Section</span></span>  
 [<span data-ttu-id="46c66-107">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="46c66-107">Button Control Overview</span></span>](button-control-overview-windows-forms.md)  
 <span data-ttu-id="46c66-108">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="46c66-108">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="46c66-109">方法: Windows フォームのボタン クリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="46c66-109">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)  
 <span data-ttu-id="46c66-110">Windows フォームでのボタンの基本的な使用法について説明します。</span><span class="sxs-lookup"><span data-stu-id="46c66-110">Explains the most basic use of a button on a Windows Form.</span></span>  
  
 [<span data-ttu-id="46c66-111">方法: Windows フォームの Button を承認ボタンとして指定します。</span><span class="sxs-lookup"><span data-stu-id="46c66-111">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 <span data-ttu-id="46c66-112">`Button` コントロールを承認ボタン (既定のボタン) として設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="46c66-112">Explains how to designate a `Button` control to be the accept button, also known as the default button.</span></span>  
  
 [<span data-ttu-id="46c66-113">方法: Windows フォームの Button をキャンセル ボタンとして指定します。</span><span class="sxs-lookup"><span data-stu-id="46c66-113">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 <span data-ttu-id="46c66-114">`Button` コントロールをキャンセル ボタンとして設定する方法を説明します。このボタンは、ユーザーが Esc キーを押すとクリックされます</span><span class="sxs-lookup"><span data-stu-id="46c66-114">Explains how to designate a `Button` control to be the cancel button, which is clicked whenever the user presses the ESC key.</span></span>  
  
 [<span data-ttu-id="46c66-115">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="46c66-115">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)  
 <span data-ttu-id="46c66-116">ボタンを選択する方法の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="46c66-116">Lists methods of selecting a button.</span></span>  
  
 <span data-ttu-id="46c66-117">参照してください[方法。Windows フォームの Button をデザイナーの使用を承認ボタンとして指定](designate-a-wf-button-as-the-accept-button-using-the-designer.md)と[方法。Windows フォームの Button をデザイナーを使用して、[キャンセル] ボタンとして指定](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="46c66-117">Also see [How to: Designate a Windows Forms Button as the Accept Button Using the Designer](designate-a-wf-button-as-the-accept-button-using-the-designer.md) and [How to: Designate a Windows Forms Button as the Cancel Button Using the Designer](designate-a-wf-button-as-the-cancel-button-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="46c66-118">参照</span><span class="sxs-lookup"><span data-stu-id="46c66-118">Reference</span></span>  
 <span data-ttu-id="46c66-119"><xref:System.Windows.Forms.Button> クラス</span><span class="sxs-lookup"><span data-stu-id="46c66-119"><xref:System.Windows.Forms.Button> class</span></span>  
 <span data-ttu-id="46c66-120">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="46c66-120">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46c66-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="46c66-121">Related Sections</span></span>  
 [<span data-ttu-id="46c66-122">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="46c66-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="46c66-123">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="46c66-123">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 <span data-ttu-id="46c66-124">参照してください[ダイアログ ボックスへのユーザー入力](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1s9ws53w(v=vs.100))と[方法。ダイアログ ボックスを閉じて、ユーザー入力を保持](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/65ad5907(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="46c66-124">Also see [User Input to Dialog Boxes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1s9ws53w(v=vs.100)) and [How to: Close Dialog Boxes and Retain User Input](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/65ad5907(v=vs.100)).</span></span>
