---
title: Label コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: cc38b0f3ded9e3c2a5a4146eb6bb474921d1e19f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210092"
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="e1166-102">Label コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="e1166-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="e1166-103">Windows フォーム<xref:System.Windows.Forms.Label>テキストまたはユーザーが編集できないイメージを表示するコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1166-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="e1166-104">フォーム上のオブジェクトの識別に使用されます — 特定コントロールの説明をクリックした場合などを提供する、または実行時イベントまたはアプリケーションのプロセスへの応答の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="e1166-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="e1166-105">たとえば、ラベルを使用して、テキスト ボックス、リスト ボックス、コンボ ボックス、および具合にわかりやすいキャプションを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e1166-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="e1166-106">実行時に、イベントへの応答では、ラベルによって表示されるテキストを変更するコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1166-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="e1166-107">たとえば、アプリケーションでは、変更を処理するまでに数分かかる、ラベル内で処理ステータス メッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e1166-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="e1166-108">ラベル コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="e1166-108">Working with the Label Control</span></span>  
 <span data-ttu-id="e1166-109"><xref:System.Windows.Forms.Label>コントロールがフォーカスを受け取ることはできません、他のコントロールへのアクセス キーの作成にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1166-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="e1166-110">ユーザーをアクセス キーと ALT キーを押して、その他のコントロールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1166-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="e1166-111">詳細については、次を参照してください。 [Windows のフォーム コントロールのアクセス キーを作成する](how-to-create-access-keys-for-windows-forms-controls.md)と[方法。Windows フォームの Label コントロールでのアクセス キーを作成](how-to-create-access-keys-with-windows-forms-label-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1166-111">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="e1166-112">ラベルに表示するキャプションが含まれている、<xref:System.Windows.Forms.Label.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e1166-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="e1166-113"><xref:System.Windows.Forms.Label.TextAlign%2A>プロパティでは、ラベル内のテキストの配置を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e1166-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="e1166-114">詳細については、「[方法 :によって表示されるテキストを設定、Windows フォーム コントロール](how-to-set-the-text-displayed-by-a-windows-forms-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1166-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1166-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1166-115">See also</span></span>

- <xref:System.Windows.Forms.Label>
- [<span data-ttu-id="e1166-116">方法: 内容に合わせて Windows フォーム Label コントロールをサイズします。</span><span class="sxs-lookup"><span data-stu-id="e1166-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="e1166-117">方法: Windows フォームの Label コントロールでのアクセス キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1166-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
