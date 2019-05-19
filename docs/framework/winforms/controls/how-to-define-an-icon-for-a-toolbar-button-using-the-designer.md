---
title: '方法: デザイナーを使って ToolBar ボタンのアイコンを定義する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: f8fe28a7827c0f69f80a3078d604b1818f4134ac
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877414"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="23fe8-102">方法: デザイナーを使って ToolBar ボタンのアイコンを定義する</span><span class="sxs-lookup"><span data-stu-id="23fe8-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="23fe8-103">
  <xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="23fe8-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="23fe8-104"><xref:System.Windows.Forms.ToolBar> ボタンは、ユーザーがそれらに含まれるを簡単に識別のアイコンを表示できません。</span><span class="sxs-lookup"><span data-stu-id="23fe8-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="23fe8-105">これは画像を追加することによって実現、<xref:System.Windows.Forms.ImageList>コンポーネントと関連付けること、<xref:System.Windows.Forms.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="23fe8-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
 <span data-ttu-id="23fe8-106">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.ToolBar>コントロールと<xref:System.Windows.Forms.ImageList>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="23fe8-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="23fe8-107">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="23fe8-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23fe8-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="23fe8-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="23fe8-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23fe8-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="23fe8-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23fe8-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="23fe8-111">デザイン時にツール バー ボタンのアイコンを設定するには</span><span class="sxs-lookup"><span data-stu-id="23fe8-111">To set an icon for a toolbar button at design time</span></span>  
  
1. <span data-ttu-id="23fe8-112">イメージを追加、<xref:System.Windows.Forms.ImageList>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="23fe8-112">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="23fe8-113">詳細については、「[方法 :デザイナーを使って ImageList イメージを追加または](how-to-add-or-remove-imagelist-images-with-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="23fe8-113">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>  
  
2. <span data-ttu-id="23fe8-114">選択、<xref:System.Windows.Forms.ToolBar>フォーム上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="23fe8-114">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>  
  
3. <span data-ttu-id="23fe8-115">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.ToolBar>コントロールの<xref:System.Windows.Forms.ToolBar.ImageList%2A>プロパティを<xref:System.Windows.Forms.ImageList>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="23fe8-115">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
4.  <span data-ttu-id="23fe8-116">をクリックして、<xref:System.Windows.Forms.ToolBar>コントロールの<xref:System.Windows.Forms.ToolBar.Buttons%2A>プロパティを選択し、省略記号ボタン (![. Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) ボタンをクリックする、**ツールバー ・ ボタン コレクションエディター**します。</span><span class="sxs-lookup"><span data-stu-id="23fe8-116">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
5. <span data-ttu-id="23fe8-117">使用して、**追加**にボタンを追加するボタン、<xref:System.Windows.Forms.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="23fe8-117">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
6. <span data-ttu-id="23fe8-118">**プロパティ**ウィンドウの右側にあるペインに表示される、**ツールバー ・ ボタン コレクション エディター**、設定、<xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>一覧で、値の 1 つは、各ツール バー ボタンのプロパティを追加したイメージの描画、<xref:System.Windows.Forms.ImageList>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="23fe8-118">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23fe8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="23fe8-119">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="23fe8-120">方法: ツール バー ボタンのメニュー イベントのトリガー</span><span class="sxs-lookup"><span data-stu-id="23fe8-120">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="23fe8-121">ToolBar コントロール</span><span class="sxs-lookup"><span data-stu-id="23fe8-121">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="23fe8-122">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="23fe8-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
