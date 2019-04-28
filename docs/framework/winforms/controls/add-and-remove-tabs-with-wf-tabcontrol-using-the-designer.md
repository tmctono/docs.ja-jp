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
ms.openlocfilehash: 23fe9fa2b8405a6ebe66e8f0cee1d81d45f2395b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640372"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="3c2fc-102">方法: デザイナーで Windows フォーム TabControl を使ってタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="3c2fc-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="3c2fc-103">配置するとき、<xref:System.Windows.Forms.TabControl>コントロール フォームで、既定で 2 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="3c2fc-104">追加したり、デザイナーを使用してタブを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="3c2fc-105">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.TabControl>コントロール。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="3c2fc-106">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c2fc-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3c2fc-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3c2fc-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="3c2fc-110">追加またはデザイナーを使用してタブを削除するには</span><span class="sxs-lookup"><span data-stu-id="3c2fc-110">To add or remove a tab using the designer</span></span>  
  
- <span data-ttu-id="3c2fc-111">コントロールのスマート タグでは、次のようにクリックします**タブの追加**または**タブの削除。**</span><span class="sxs-lookup"><span data-stu-id="3c2fc-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="3c2fc-112">- または -</span><span class="sxs-lookup"><span data-stu-id="3c2fc-112">-or-</span></span>  
  
     <span data-ttu-id="3c2fc-113">**プロパティ**ウィンドウで、をクリックして、**省略記号**ボタン (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) 横<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティを開き、 **TabPage コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="3c2fc-114">をクリックして、**追加**または**削除**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c2fc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c2fc-115">See also</span></span>

- [<span data-ttu-id="3c2fc-116">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="3c2fc-116">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="3c2fc-117">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="3c2fc-117">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="3c2fc-118">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-118">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="3c2fc-119">方法: タブ ページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-119">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="3c2fc-120">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="3c2fc-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
