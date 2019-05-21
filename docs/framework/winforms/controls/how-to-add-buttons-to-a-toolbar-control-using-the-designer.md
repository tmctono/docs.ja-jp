---
title: '方法: デザイナーを使って ToolBar コントロールにボタンを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: ed479c04db094b5fc0c42bfecbfe5a7753c16358
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960185"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a><span data-ttu-id="2e16d-102">方法: デザイナーを使って ToolBar コントロールにボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="2e16d-102">How to: Add Buttons to a ToolBar Control Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="2e16d-103">
  <xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="2e16d-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="2e16d-104">不可欠な部分、<xref:System.Windows.Forms.ToolBar>コントロールは、ボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="2e16d-105">メニュー コマンドに簡単にアクセスを提供するこれらを使用できますか、または、メニュー構造では使用できないユーザーにコマンドを公開するアプリケーションのユーザー インターフェイスの別の領域に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="2e16d-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>

<span data-ttu-id="2e16d-106">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="2e16d-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control.</span></span> <span data-ttu-id="2e16d-107">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2e16d-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e16d-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2e16d-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e16d-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2e16d-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e16d-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="to-add-buttons-at-design-time"></a><span data-ttu-id="2e16d-111">デザイン時にボタンを追加するには</span><span class="sxs-lookup"><span data-stu-id="2e16d-111">To add buttons at design time</span></span>

1. <span data-ttu-id="2e16d-112"><xref:System.Windows.Forms.ToolBar> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-112">Select the <xref:System.Windows.Forms.ToolBar> control.</span></span>

2. <span data-ttu-id="2e16d-113">**プロパティ**ウィンドウで、をクリックして、<xref:System.Windows.Forms.ToolBar.Buttons%2A>プロパティを選択し、クリックして、**省略記号**(![Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…).](./media/visual-studio-ellipsis-button.png))ボタンをクリックする、**ツールバー ・ ボタン コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-113">In the **Properties** window, click the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it and click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

3. <span data-ttu-id="2e16d-114">使用して、**追加**と**削除**ボタンの追加し、削除 ボタンから、<xref:System.Windows.Forms.ToolBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="2e16d-114">Use the **Add** and **Remove** buttons to add and remove buttons from the <xref:System.Windows.Forms.ToolBar> control.</span></span>

4. <span data-ttu-id="2e16d-115">各ボタンのプロパティを構成、**プロパティ**エディターの右側にあるペインに表示されるウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2e16d-115">Configure the properties of the individual buttons in the **Properties** window that appears in the pane on the right side of the editor.</span></span> <span data-ttu-id="2e16d-116">次の表では、考慮すべき重要なプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-116">The following table shows some important properties to consider.</span></span>

    |<span data-ttu-id="2e16d-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2e16d-117">Property</span></span>|<span data-ttu-id="2e16d-118">説明</span><span class="sxs-lookup"><span data-stu-id="2e16d-118">Description</span></span>|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|<span data-ttu-id="2e16d-119">ドロップダウン ツール バー ボタンに表示されるメニューを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-119">Sets the menu to be displayed in the drop-down toolbar button.</span></span> <span data-ttu-id="2e16d-120">ツール バー ボタンの<xref:System.Windows.Forms.ToolBarButton.Style%2A>にプロパティを設定する必要があります<xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-120">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span></span> <span data-ttu-id="2e16d-121">このプロパティは、のインスタンスを受け取り、<xref:System.Windows.Forms.ContextMenu>クラスとして参照します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-121">This property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|<span data-ttu-id="2e16d-122">トグル スタイルのツール バー ボタンが部分的に押されているかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-122">Sets whether a toggle-style toolbar button is partially pushed.</span></span> <span data-ttu-id="2e16d-123">ツール バー ボタンの<xref:System.Windows.Forms.ToolBarButton.Style%2A>にプロパティを設定する必要があります<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-123">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|<span data-ttu-id="2e16d-124">トグル スタイルのツール バー ボタンが押された状態では現在あるかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-124">Sets whether a toggle-style toolbar button is currently in the pushed state.</span></span> <span data-ttu-id="2e16d-125">ツール バー ボタンの<xref:System.Windows.Forms.ToolBarButton.Style%2A>にプロパティを設定する必要があります<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>または<xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-125">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> or <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|<span data-ttu-id="2e16d-126">ツール バー ボタンのスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-126">Sets the style of the toolbar button.</span></span> <span data-ttu-id="2e16d-127">内の値のいずれかを指定する必要があります、<xref:System.Windows.Forms.ToolBarButtonStyle>列挙体。</span><span class="sxs-lookup"><span data-stu-id="2e16d-127">Must be one of the values in the <xref:System.Windows.Forms.ToolBarButtonStyle> enumeration.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|<span data-ttu-id="2e16d-128">ボタンによって表示される文字列。</span><span class="sxs-lookup"><span data-stu-id="2e16d-128">The text string displayed by the button.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|<span data-ttu-id="2e16d-129">ボタンのツールヒントとして表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="2e16d-129">The text that appears as a ToolTip for the button.</span></span>|

5. <span data-ttu-id="2e16d-130">をクリックして**OK**をダイアログ ボックスを閉じて、指定したパネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-130">Click **OK** to close the dialog box and create the panels you specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e16d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e16d-131">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="2e16d-132">方法: ツール バー ボタンのアイコンを定義します。</span><span class="sxs-lookup"><span data-stu-id="2e16d-132">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="2e16d-133">方法: ツール バー ボタンのメニュー イベントのトリガー</span><span class="sxs-lookup"><span data-stu-id="2e16d-133">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="2e16d-134">ToolBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2e16d-134">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)
- [<span data-ttu-id="2e16d-135">ToolBar コントロール</span><span class="sxs-lookup"><span data-stu-id="2e16d-135">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
