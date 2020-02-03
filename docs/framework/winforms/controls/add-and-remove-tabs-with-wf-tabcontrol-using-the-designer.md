---
title: デザイナーを使用して TabControl のタブを追加および削除する
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 445342ffb3b53c880ac38da52076e0c0cb0a9f23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746287"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="ba6e6-102">方法 : デザイナーで Windows フォーム TabControl を使ってタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="ba6e6-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="ba6e6-103">フォームに <xref:System.Windows.Forms.TabControl> コントロールを配置すると、既定で2つのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba6e6-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="ba6e6-104">デザイナーを使用して、タブを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="ba6e6-104">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="ba6e6-105">次の手順では、<xref:System.Windows.Forms.TabControl> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="ba6e6-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="ba6e6-106">このようなプロジェクトの設定の詳細については、「[方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)する」および「[方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba6e6-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="ba6e6-107">デザイナーを使用してタブを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="ba6e6-107">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="ba6e6-108">コントロールのスマートタグで、 **[タブの追加]** または **[タブの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba6e6-108">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="ba6e6-109">または</span><span class="sxs-lookup"><span data-stu-id="ba6e6-109">-or-</span></span>

     <span data-ttu-id="ba6e6-110">**[プロパティ]** ウィンドウで、<xref:System.Windows.Forms.TabControl.TabPages%2A> プロパティの横にある省略記号ボタン ([...]) をクリックして、[](./media/visual-studio-ellipsis-button.png)プロパティウィンドウ] をクリックし、[ **TabPage コレクションエディター** **![] を**開きます。</span><span class="sxs-lookup"><span data-stu-id="ba6e6-110">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="ba6e6-111">**[追加]** または **[削除]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba6e6-111">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba6e6-112">参照</span><span class="sxs-lookup"><span data-stu-id="ba6e6-112">See also</span></span>

- [<span data-ttu-id="ba6e6-113">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="ba6e6-113">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="ba6e6-114">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ba6e6-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="ba6e6-115">方法: タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="ba6e6-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="ba6e6-116">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="ba6e6-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="ba6e6-117">方法: Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="ba6e6-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
