---
title: '方法: Windows フォームで Windows エクスプローラー スタイルのインターフェイスを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: db2c5431dfb0156c1508a18ef13d2af80eb4981b
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039534"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="8f736-102">方法: Windows フォームで Windows エクスプローラー スタイルのインターフェイスを作成する</span><span class="sxs-lookup"><span data-stu-id="8f736-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="8f736-103">Windows Explorer は、アプリケーションのユーザーインターフェイスの一般的な選択肢であり、その準備が整っているためです。</span><span class="sxs-lookup"><span data-stu-id="8f736-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>

 <span data-ttu-id="8f736-104">Windows エクスプローラーは、基本的<xref:System.Windows.Forms.TreeView>にはコントロール<xref:System.Windows.Forms.ListView>であり、別のパネルのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="8f736-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="8f736-105">パネルはスプリッターによってサイズ変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8f736-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="8f736-106">このコントロールの配置は、情報を表示および参照するために非常に効果的です。</span><span class="sxs-lookup"><span data-stu-id="8f736-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>

 <span data-ttu-id="8f736-107">次の手順では、Windows エクスプローラーのようなフォームでコントロールを配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f736-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="8f736-108">Windows Explorer アプリケーションのファイル参照機能を追加する方法については説明しません。</span><span class="sxs-lookup"><span data-stu-id="8f736-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>

## <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="8f736-109">Windows エクスプローラースタイルの Windows フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="8f736-109">To create a Windows Explorer-style Windows Form</span></span>

1. <span data-ttu-id="8f736-110">新しい Windows アプリケーションプロジェクトを作成します ([**ファイル** > ] [**新しい** > **プロジェクト** > ] **[ビジュアルC# ]** または**Visual Basic** > **クラシックデスクトップ** > ) **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="8f736-110">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="8f736-111">**ツールボックス**から:</span><span class="sxs-lookup"><span data-stu-id="8f736-111">From the **Toolbox**:</span></span>

    1. <span data-ttu-id="8f736-112">コントロールを<xref:System.Windows.Forms.SplitContainer>フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8f736-112">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>

    2. <span data-ttu-id="8f736-113">コントロールを<xref:System.Windows.Forms.TreeView> **SplitterPanel1** (Panel1 とマークされた<xref:System.Windows.Forms.SplitContainer>コントロールのパネル) にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8f736-113">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>

    3. <span data-ttu-id="8f736-114">コントロールを<xref:System.Windows.Forms.ListView> **SplitterPanel2** (Panel2 とマークされた<xref:System.Windows.Forms.SplitContainer>コントロールのパネル) にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8f736-114">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>

3. <span data-ttu-id="8f736-115">CTRL キーを押しながら3つのコントロールをすべて選択し、順番にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f736-115">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="8f736-116"><xref:System.Windows.Forms.SplitContainer>コントロールを選択するときは、パネルではなくスプリッターバーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f736-116">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8f736-117">**[編集]** メニューの **[すべて選択]** コマンドを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8f736-117">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="8f736-118">その場合、次の手順で必要なプロパティは、 **[プロパティ]** ウィンドウに表示されません。</span><span class="sxs-lookup"><span data-stu-id="8f736-118">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>

4. <span data-ttu-id="8f736-119">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.SplitContainer.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="8f736-119">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="8f736-120">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f736-120">Press F5 to run the application.</span></span>

     <span data-ttu-id="8f736-121">フォームには、Windows エクスプローラーと同様の2つの部分で構成されるユーザーインターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f736-121">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8f736-122">スプリッターをドラッグすると、パネル自体のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="8f736-122">When you drag the splitter, the panels resize themselves.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f736-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f736-123">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="8f736-124">方法: Windows フォームを使用してマルチペインユーザーインターフェイスを作成する</span><span class="sxs-lookup"><span data-stu-id="8f736-124">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="8f736-125">方法: 分割ウィンドウでのサイズ変更および配置動作の定義</span><span class="sxs-lookup"><span data-stu-id="8f736-125">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="8f736-126">方法: ウィンドウを水平方向に分割する</span><span class="sxs-lookup"><span data-stu-id="8f736-126">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="8f736-127">SplitContainer コントロール</span><span class="sxs-lookup"><span data-stu-id="8f736-127">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
