---
title: '方法: デザイナーで Windows フォーム ListView コントロールを使って項目を追加および削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 6e08a7013242b0dbb433e288c4f8d788cb4e143b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640457"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="e0358-102">方法: デザイナーで Windows フォーム ListView コントロールを使って項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="e0358-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="e0358-103">Windows フォームに項目を追加するプロセス<xref:System.Windows.Forms.ListView>コントロールは、主にアイテムを指定して、プロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e0358-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="e0358-104">追加またはリスト項目の削除は、いつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="e0358-104">Adding or removing list items can be done at any time.</span></span>  
  
 <span data-ttu-id="e0358-105">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="e0358-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="e0358-106">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0358-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0358-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0358-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e0358-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0358-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e0358-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0358-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="e0358-110">デザイナーを使用して項目を追加または削除</span><span class="sxs-lookup"><span data-stu-id="e0358-110">To add or remove items using the designer</span></span>  
  
1. <span data-ttu-id="e0358-111"><xref:System.Windows.Forms.ListView> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0358-111">Select the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
2. <span data-ttu-id="e0358-112">**プロパティ**ウィンドウで、をクリックして、**省略記号**(![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) ボタンを<xref:System.Windows.Forms.ListView.Items%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e0358-112">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="e0358-113">**ListViewItem コレクション エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0358-113">The **ListViewItem Collection Editor** appears.</span></span>  
  
3. <span data-ttu-id="e0358-114">項目を追加する をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0358-114">To add an item, click the **Add** button.</span></span> <span data-ttu-id="e0358-115">など、新しい項目のプロパティを設定することができますし、<xref:System.Windows.Forms.ListView.Text%2A>と<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e0358-115">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
4. <span data-ttu-id="e0358-116">項目を削除するを選択し、クリックして、**削除**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0358-116">To remove an item, select it and click the **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0358-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0358-117">See also</span></span>

- [<span data-ttu-id="e0358-118">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="e0358-118">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="e0358-119">方法: Windows フォーム ListView コントロールに列を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0358-119">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="e0358-120">方法: Windows フォーム ListView コントロールでの列にサブ項目を表示</span><span class="sxs-lookup"><span data-stu-id="e0358-120">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="e0358-121">方法: Windows フォーム ListView コントロールのアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="e0358-121">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="e0358-122">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0358-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="e0358-123">方法: Windows フォーム ListView コントロールに項目をグループ化</span><span class="sxs-lookup"><span data-stu-id="e0358-123">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
