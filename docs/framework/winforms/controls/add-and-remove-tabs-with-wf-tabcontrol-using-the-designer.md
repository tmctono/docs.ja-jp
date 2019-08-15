---
title: '方法: デザイナーで Windows フォーム TabControl を使ってタブを追加および削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: da9a9d40529a1902c58f67d6a8696d8906eb34c9
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040061"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="6ab5d-102">方法: デザイナーで Windows フォーム TabControl を使ってタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="6ab5d-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="6ab5d-103">フォームにコントロールを<xref:System.Windows.Forms.TabControl>配置すると、既定で2つのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab5d-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="6ab5d-104">デザイナーを使用して、タブを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6ab5d-104">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="6ab5d-105">次の手順では、 <xref:System.Windows.Forms.TabControl>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ab5d-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="6ab5d-106">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6ab5d-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="6ab5d-107">デザイナーを使用してタブを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="6ab5d-107">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="6ab5d-108">コントロールのスマートタグで、 **[タブの追加]** または **[タブの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ab5d-108">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="6ab5d-109">\- または -</span><span class="sxs-lookup"><span data-stu-id="6ab5d-109">-or-</span></span>

     <span data-ttu-id="6ab5d-110">**[プロパティ]** ウィンドウで、プロパティの<xref:System.Windows.Forms.TabControl.TabPages%2A>横に![ある省略記号ボタン ([...] プロパティウィンドウ](./media/visual-studio-ellipsis-button.png)) をクリックして、 **[TabPage コレクションエディター]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6ab5d-110">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="6ab5d-111">**[追加]** または **[削除]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ab5d-111">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ab5d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ab5d-112">See also</span></span>

- [<span data-ttu-id="6ab5d-113">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="6ab5d-113">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="6ab5d-114">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6ab5d-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="6ab5d-115">方法: タブページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="6ab5d-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="6ab5d-116">方法: タブページを無効にする</span><span class="sxs-lookup"><span data-stu-id="6ab5d-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="6ab5d-117">方法: Windows フォーム TabControl の外観を変更する</span><span class="sxs-lookup"><span data-stu-id="6ab5d-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
