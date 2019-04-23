---
title: '方法: Windows フォーム GroupBox コントロールを使用してコントロールをグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: d2bad0020d18cd262bc2fe3489a00209308bd7b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335876"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="655b1-102">方法: Windows フォーム GroupBox コントロールを使用してコントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="655b1-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="655b1-103">Windows フォーム<xref:System.Windows.Forms.GroupBox>コントロールを使用すると、その他のコントロールをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="655b1-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="655b1-104">コントロールをグループ化の 3 つの理由があります。</span><span class="sxs-lookup"><span data-stu-id="655b1-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="655b1-105">わかりやすいユーザー インターフェイスに関連するフォーム要素の視覚的にグループ化を作成します。</span><span class="sxs-lookup"><span data-stu-id="655b1-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="655b1-106">(たとえばのラジオ ボタン) のプログラムによるグループ化を作成します。</span><span class="sxs-lookup"><span data-stu-id="655b1-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="655b1-107">デザイン時に単位として、コントロールを移動します。</span><span class="sxs-lookup"><span data-stu-id="655b1-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="655b1-108">コントロールのグループを作成するには</span><span class="sxs-lookup"><span data-stu-id="655b1-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="655b1-109">描画を<xref:System.Windows.Forms.GroupBox>フォーム上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="655b1-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="655b1-110">グループ ボックスで、各グループ ボックス内を描画するには、他のコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="655b1-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="655b1-111">グループ ボックスで囲むしたい既存のコントロールの場合は、すべてのコントロールを選択して、選択、クリップボードに切り取ります、<xref:System.Windows.Forms.GroupBox>コントロールし、グループ ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="655b1-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="655b1-112">グループ ボックスにドラッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="655b1-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="655b1-113">設定、<xref:System.Windows.Forms.GroupBox.Text%2A>に適切なキャプション グループ ボックスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="655b1-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655b1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="655b1-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="655b1-115">GroupBox コントロール</span><span class="sxs-lookup"><span data-stu-id="655b1-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
