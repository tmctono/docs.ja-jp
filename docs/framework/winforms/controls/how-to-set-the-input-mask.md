---
title: '方法: 定型入力を設定する'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06eaf68fef167d63e6f8404dd5049f5445881d24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331469"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="53179-102">方法: 定型入力を設定する</span><span class="sxs-lookup"><span data-stu-id="53179-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="53179-103">マスクされたテキスト ボックス コントロールは、許可または拒否のユーザー入力の宣言の構文をサポートする強化されたテキスト ボックス コントロールです。</span><span class="sxs-lookup"><span data-stu-id="53179-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="53179-104">Mask プロパティを設定して、アプリケーションで任意のカスタム検証ロジックを記述することがなく、使用可能なユーザー入力を指定できます。</span><span class="sxs-lookup"><span data-stu-id="53179-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="53179-105">詳細については、の「解説」を参照してください、<xref:System.Windows.Forms.MaskedTextBox>クラス。</span><span class="sxs-lookup"><span data-stu-id="53179-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="53179-106">Mask プロパティを手動で設定</span><span class="sxs-lookup"><span data-stu-id="53179-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="53179-107">Mask プロパティをサポートする文字に精通する場合は、手動で入力することができます。</span><span class="sxs-lookup"><span data-stu-id="53179-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="53179-108">Mask プロパティをサポートする、文字の概要については、「解説」を参照してください、<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="53179-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="53179-109">Mask プロパティを手動で設定するには</span><span class="sxs-lookup"><span data-stu-id="53179-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="53179-110">**デザイン**ビューで、<xref:System.Windows.Forms.MaskedTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="53179-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="53179-111">**プロパティ**ウィンドウで、検索、<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="53179-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="53179-112">使用するマスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="53179-112">Type the mask that you want.</span></span> <span data-ttu-id="53179-113">たとえば、「 `###`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="53179-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="53179-114">[定型入力] ダイアログ ボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="53179-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="53179-115">[定型入力] ダイアログ ボックスでは、いくつか定義済みの入力マスクを提供します。</span><span class="sxs-lookup"><span data-stu-id="53179-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="53179-116">定義済みのマスクを変更または、独自のマスクを手動で入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="53179-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="53179-117">定型入力 ダイアログ ボックスを開きます</span><span class="sxs-lookup"><span data-stu-id="53179-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="53179-118">**デザイン**ビューで、<xref:System.Windows.Forms.MaskedTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="53179-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="53179-119">[スマート タグを開く] をクリックして、 **MaskedTextBox タスク**パネル。</span><span class="sxs-lookup"><span data-stu-id="53179-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="53179-120">クリックして**マスクを設定する**します。</span><span class="sxs-lookup"><span data-stu-id="53179-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="53179-121">\- または -</span><span class="sxs-lookup"><span data-stu-id="53179-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="53179-122">**プロパティ**ウィンドウで、<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="53179-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="53179-123">プロパティの値列の省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53179-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="53179-124">**定型入力** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53179-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="53179-125">定型入力 ダイアログ ボックスを使用するには</span><span class="sxs-lookup"><span data-stu-id="53179-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="53179-126">(省略可能)一覧で定義済みのマスクのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53179-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="53179-127">(省略可能)定義済みのマスクを編集、**マスク**ボックス。</span><span class="sxs-lookup"><span data-stu-id="53179-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="53179-128">(省略可能)新しいマスクを入力、**マスク**ボックス。</span><span class="sxs-lookup"><span data-stu-id="53179-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="53179-129">定義済みのマスクのいずれかを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="53179-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53179-130">[プレビュー] ボックスでユーザーに表示される文字の表示、<xref:System.Windows.Forms.MaskedTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="53179-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="53179-131">これらの文字は、データを正しく入力するユーザーを支援するガイドです。</span><span class="sxs-lookup"><span data-stu-id="53179-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="53179-132">オンまたはオフ、**使用 ValidatingType**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="53179-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="53179-133">**使用 ValidatingType**  チェック ボックスは、ユーザーがデータ入力を検証するデータ型を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="53179-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="53179-134">詳細については、<xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="53179-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="53179-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53179-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="53179-136">マスクを入力、**マスク**プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="53179-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53179-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="53179-137">See also</span></span>

- [<span data-ttu-id="53179-138">チュートリアル: MaskedTextBox コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="53179-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
