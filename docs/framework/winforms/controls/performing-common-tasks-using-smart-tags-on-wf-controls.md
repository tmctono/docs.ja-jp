---
title: 'チュートリアル: Windows フォーム コントロールのスマート タグを使用した共通タスクの実行'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211417"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="d7463-102">チュートリアル: Windows フォーム コントロールのスマート タグを使用した共通タスクの実行</span><span class="sxs-lookup"><span data-stu-id="d7463-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>

<span data-ttu-id="d7463-103">Windows フォーム アプリケーションのフォームとコントロールを作成するときは、繰り返し実行する多くのタスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7463-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="d7463-104">これらは、発生する、一般的に実行されるタスクの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="d7463-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="d7463-105">追加またはでタブを削除する、<xref:System.Windows.Forms.TabControl>します。</span><span class="sxs-lookup"><span data-stu-id="d7463-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="d7463-106">コントロールは、その親にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="d7463-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="d7463-107">向きの変更、<xref:System.Windows.Forms.SplitContainer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d7463-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="d7463-108">開発のスピード、多くのコントロールは、デザイン時に 1 つのジェスチャで上記のような一般的なタスクを実行するための状況依存のメニューにはスマート タグを提供します。</span><span class="sxs-lookup"><span data-stu-id="d7463-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="d7463-109">これらのタスクが呼び出されます*スマート タグの動詞*します。</span><span class="sxs-lookup"><span data-stu-id="d7463-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="d7463-110">スマート タグは、有効期間にわたって、デザイナーでコントロールのインスタンスに接続されたままし、常に利用します。</span><span class="sxs-lookup"><span data-stu-id="d7463-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

<span data-ttu-id="d7463-111">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="d7463-111">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="d7463-112">Windows フォーム プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d7463-112">Creating a Windows Forms project</span></span>

- <span data-ttu-id="d7463-113">スマート タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7463-113">Using smart tags</span></span>

- <span data-ttu-id="d7463-114">有効にして、スマート タグを無効化</span><span class="sxs-lookup"><span data-stu-id="d7463-114">Enabling and Disabling Smart Tags</span></span>

<span data-ttu-id="d7463-115">終了すると、これらの重要なレイアウト機能が果たす役割について理解できます。</span><span class="sxs-lookup"><span data-stu-id="d7463-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d7463-116">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d7463-116">Create the project</span></span>

<span data-ttu-id="d7463-117">最初にプロジェクトを作成し、フォームを設定します。</span><span class="sxs-lookup"><span data-stu-id="d7463-117">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="d7463-118">Visual Studio で、"SmartTagsExample"と呼ばれる Windows ベースのアプリケーション プロジェクトを作成します (**ファイル** > **新規** > **プロジェクト** >  **Visual C#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="d7463-118">In Visual Studio, create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="d7463-119">フォームを選択、 **Windows フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="d7463-119">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="d7463-120">スマート タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7463-120">Use smart tags</span></span>

<span data-ttu-id="d7463-121">スマート タグは、提供するコントロールのデザイン時に常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7463-121">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="d7463-122">ドラッグ、<xref:System.Windows.Forms.TabControl>から、**ツールボックス**フォームにします。</span><span class="sxs-lookup"><span data-stu-id="d7463-122">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="d7463-123">スマート タグ グリフに注意してください (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) のサイド バイ サイドで表示される、<xref:System.Windows.Forms.TabControl>します。</span><span class="sxs-lookup"><span data-stu-id="d7463-123">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="d7463-124">スマート タグ グリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7463-124">Click the smart-tag glyph.</span></span> <span data-ttu-id="d7463-125">グリフの横に表示されるショートカット メニューで、選択、**タブの追加**項目。</span><span class="sxs-lookup"><span data-stu-id="d7463-125">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="d7463-126">新しいタブ ページが追加されたことを確認、<xref:System.Windows.Forms.TabControl>します。</span><span class="sxs-lookup"><span data-stu-id="d7463-126">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="d7463-127"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d7463-127">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="d7463-128">スマート タグ グリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7463-128">Click the smart-tag glyph.</span></span> <span data-ttu-id="d7463-129">グリフの横に表示されるショートカット メニューで、選択、**列の追加**項目。</span><span class="sxs-lookup"><span data-stu-id="d7463-129">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="d7463-130">新しい列が追加されたことを確認、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d7463-130">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="d7463-131"><xref:System.Windows.Forms.SplitContainer> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d7463-131">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="d7463-132">スマート タグ グリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7463-132">Click the smart-tag glyph.</span></span> <span data-ttu-id="d7463-133">グリフの横に表示されるショートカット メニューで、選択、**水平分割の向き**項目。</span><span class="sxs-lookup"><span data-stu-id="d7463-133">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="d7463-134">観察、<xref:System.Windows.Forms.SplitContainer>コントロールのスプリッター バーが水平方向します。</span><span class="sxs-lookup"><span data-stu-id="d7463-134">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7463-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7463-135">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="d7463-136">[チュートリアル: Windows フォーム コンポーネントにスマート タグの追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d7463-136">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
