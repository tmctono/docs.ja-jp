---
title: GroupBox コントロールを使用したコントロールのグループ化
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736657"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="f88c2-102">方法 : Windows フォーム GroupBox コントロールを使用してコントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="f88c2-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="f88c2-103">Windows フォーム <xref:System.Windows.Forms.GroupBox> コントロールは、他のコントロールをグループ化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f88c2-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="f88c2-104">コントロールをグループ化する理由は3つあります。</span><span class="sxs-lookup"><span data-stu-id="f88c2-104">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="f88c2-105">クリアユーザーインターフェイスに関連するフォーム要素の視覚的なグループ化を作成するには</span><span class="sxs-lookup"><span data-stu-id="f88c2-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="f88c2-106">プログラムによるグループ化 (オプションボタンなど) を作成する場合は。</span><span class="sxs-lookup"><span data-stu-id="f88c2-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="f88c2-107">デザイン時にコントロールを1つの単位として移動する場合は。</span><span class="sxs-lookup"><span data-stu-id="f88c2-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="f88c2-108">コントロールのグループを作成するには</span><span class="sxs-lookup"><span data-stu-id="f88c2-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="f88c2-109">フォームに <xref:System.Windows.Forms.GroupBox> コントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="f88c2-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="f88c2-110">グループボックスに他のコントロールを追加し、それぞれをグループボックス内に描画します。</span><span class="sxs-lookup"><span data-stu-id="f88c2-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="f88c2-111">グループボックスに含める既存のコントロールがある場合は、すべてのコントロールを選択してクリップボードに貼り付け、<xref:System.Windows.Forms.GroupBox> コントロールを選択して、グループボックスに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f88c2-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="f88c2-112">また、[グループ] ボックスにドラッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f88c2-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="f88c2-113">グループボックスの [<xref:System.Windows.Forms.GroupBox.Text%2A>] プロパティを適切なキャプションに設定します。</span><span class="sxs-lookup"><span data-stu-id="f88c2-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88c2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f88c2-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="f88c2-115">GroupBox コントロール</span><span class="sxs-lookup"><span data-stu-id="f88c2-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
