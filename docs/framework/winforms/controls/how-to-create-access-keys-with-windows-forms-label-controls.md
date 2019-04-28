---
title: '方法: Windows フォームの Label コントロールでアクセス キーを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: ffe4bf6fb29e82b04938e2ba9a2d9d21e5eabcde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747109"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="5ae02-102">方法: Windows フォームの Label コントロールでアクセス キーを作成する</span><span class="sxs-lookup"><span data-stu-id="5ae02-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="5ae02-103">Windows フォーム<xref:System.Windows.Forms.Label>他のコントロールのアクセス キーを定義するコントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ae02-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="5ae02-104">ラベル コントロールにアクセス キーを定義するときに、ユーザーは、ALT キーとそれに続くタブ オーダー内でコントロールにフォーカスを移動する指定した文字に押すことができます。</span><span class="sxs-lookup"><span data-stu-id="5ae02-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="5ae02-105">ラベルは、フォーカスを受け取ることはできません、ために、タブ オーダー内で次のコントロールに自動的にフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="5ae02-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="5ae02-106">この手法を使用して、テキスト ボックス、コンボ ボックス、リスト ボックス、およびデータ グリッドをアクセス キーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5ae02-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="5ae02-107">ラベルを持つコントロールに、アクセス キーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="5ae02-107">To assign an access key to a control with a label</span></span>  
  
1. <span data-ttu-id="5ae02-108">最初に、ラベルを描画し、その他のコントロールを描きます。</span><span class="sxs-lookup"><span data-stu-id="5ae02-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="5ae02-109">- または -</span><span class="sxs-lookup"><span data-stu-id="5ae02-109">-or-</span></span>  
  
     <span data-ttu-id="5ae02-110">任意の順序で、コントロールを描画し、設定、<xref:System.Windows.Forms.Control.TabIndex%2A>を他のコントロールより 1 少ない数のラベルのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="5ae02-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2. <span data-ttu-id="5ae02-111">ラベルの設定<xref:System.Windows.Forms.Label.UseMnemonic%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="5ae02-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="5ae02-112">アンパサンド (&) は、ラベルの<xref:System.Windows.Forms.Label.Text%2A>ラベルのアクセス キーを割り当てるプロパティを。</span><span class="sxs-lookup"><span data-stu-id="5ae02-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="5ae02-113">詳細については、次を参照してください。 [Windows のフォーム コントロールのアクセス キーを作成する](how-to-create-access-keys-for-windows-forms-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ae02-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5ae02-114">アクセス キーの作成に使用するのではなく、ラベル コントロールにアンパサンドを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="5ae02-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="5ae02-115">これは、アンパサンドがデータに含まれるレコード セット内のフィールドにラベル コントロールをバインドする場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ae02-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="5ae02-116">ラベル コントロールでは、アンパサンドを表示するには、設定、<xref:System.Windows.Forms.Label.UseMnemonic%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="5ae02-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="5ae02-117">アンパサンドを表示しても、アクセス キーがある場合は、設定、<xref:System.Windows.Forms.Label.UseMnemonic%2A>プロパティを`true`とアクセス キーは 1 つのアンパサンド (&)、アンパサンドを 2 つのアンパサンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="5ae02-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5ae02-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ae02-118">See also</span></span>

- [<span data-ttu-id="5ae02-119">方法: 内容に合わせて Windows フォーム Label コントロールをサイズします。</span><span class="sxs-lookup"><span data-stu-id="5ae02-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="5ae02-120">Label コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5ae02-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="5ae02-121">Label コントロール</span><span class="sxs-lookup"><span data-stu-id="5ae02-121">Label Control</span></span>](label-control-windows-forms.md)
