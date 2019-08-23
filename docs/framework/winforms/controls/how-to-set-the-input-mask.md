---
title: '方法: 定型入力を設定する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949143"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="61ac1-102">方法: 定型入力を設定する</span><span class="sxs-lookup"><span data-stu-id="61ac1-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="61ac1-103">マスクされたテキストボックスコントロールは、ユーザー入力を受け入れたり拒否したりするための宣言構文をサポートする、強化されたテキストボックスコントロールです。</span><span class="sxs-lookup"><span data-stu-id="61ac1-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="61ac1-104">Mask プロパティを設定することによって、アプリケーションにカスタム検証ロジックを記述することなく、許容されるユーザー入力を指定できます。</span><span class="sxs-lookup"><span data-stu-id="61ac1-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="61ac1-105">詳細については、 <xref:System.Windows.Forms.MaskedTextBox>クラスの「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61ac1-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="61ac1-106">Mask プロパティを手動で設定する</span><span class="sxs-lookup"><span data-stu-id="61ac1-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="61ac1-107">Mask プロパティでサポートされている文字に慣れている場合は、手動で入力できます。</span><span class="sxs-lookup"><span data-stu-id="61ac1-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="61ac1-108">Mask プロパティでサポートされる文字の概要については、 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティの「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61ac1-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="61ac1-109">Mask プロパティを手動で設定するには</span><span class="sxs-lookup"><span data-stu-id="61ac1-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="61ac1-110">**デザイン**ビューで、を選択<xref:System.Windows.Forms.MaskedTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="61ac1-111">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="61ac1-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="61ac1-112">目的のマスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-112">Type the mask that you want.</span></span> <span data-ttu-id="61ac1-113">たとえば、「 `###`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="61ac1-114">[定型入力] ダイアログボックスの使用</span><span class="sxs-lookup"><span data-stu-id="61ac1-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="61ac1-115">[定型入力] ダイアログボックスには、定義済みの入力マスクがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="61ac1-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="61ac1-116">また、定義済みのマスクを変更したり、独自のマスクを手動で入力したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="61ac1-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="61ac1-117">[定型入力] ダイアログボックスを開くには</span><span class="sxs-lookup"><span data-stu-id="61ac1-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="61ac1-118">**デザイン**ビューで、を選択<xref:System.Windows.Forms.MaskedTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1. <span data-ttu-id="61ac1-119">スマートタグをクリックして、 **[MaskedTextBox タスク]** パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="61ac1-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2. <span data-ttu-id="61ac1-120">**[マスクの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61ac1-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="61ac1-121">\- または -</span><span class="sxs-lookup"><span data-stu-id="61ac1-121">\- or -</span></span>  
  
    1. <span data-ttu-id="61ac1-122">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2. <span data-ttu-id="61ac1-123">[プロパティ値] 列の省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="61ac1-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="61ac1-124">**[定型入力]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="61ac1-124">The **Input Mask** dialog box appears.</span></span>  
  
### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="61ac1-125">[定型入力] ダイアログボックスを使用するには</span><span class="sxs-lookup"><span data-stu-id="61ac1-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="61ac1-126">Optional一覧で、定義済みマスクのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="61ac1-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="61ac1-127">Optional **[マスク]** ボックスで、定義済みのマスクを編集します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="61ac1-128">Optional **[マスク]** ボックスに新しいマスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="61ac1-129">つまり、定義済みのマスクのいずれかを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="61ac1-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="61ac1-130">[プレビュー] ボックスに、ユーザーがに<xref:System.Windows.Forms.MaskedTextBox>表示する文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61ac1-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="61ac1-131">これらの文字は、ユーザーがデータを正しく入力するのに役立つガイドです。</span><span class="sxs-lookup"><span data-stu-id="61ac1-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="61ac1-132">**[ValidatingType を使用する]** チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="61ac1-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="61ac1-133">[ **ValidatingType を使用**する] チェックボックスは、ユーザーによるデータ入力の検証にデータ型を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="61ac1-134">詳細については、<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61ac1-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="61ac1-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61ac1-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="61ac1-136">マスクは、 **[プロパティ]** ウィンドウの**mask**プロパティに入力します。</span><span class="sxs-lookup"><span data-stu-id="61ac1-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ac1-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="61ac1-137">See also</span></span>

- [<span data-ttu-id="61ac1-138">チュートリアル: MaskedTextBox コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="61ac1-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
