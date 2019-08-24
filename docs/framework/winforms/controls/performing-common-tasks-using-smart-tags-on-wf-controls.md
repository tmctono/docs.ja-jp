---
title: 'チュートリアル: Windows フォーム コントロールのスマート タグを使用した共通タスクの実行'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015758"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="3b065-102">チュートリアル: スマートタグを使用した一般的なタスクの実行</span><span class="sxs-lookup"><span data-stu-id="3b065-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="3b065-103">Windows フォームアプリケーションのフォームとコントロールを構築する際には、繰り返し実行する多くのタスクがあります。</span><span class="sxs-lookup"><span data-stu-id="3b065-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="3b065-104">次に、一般的に実行されるタスクをいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="3b065-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="3b065-105">でのタブの追加または<xref:System.Windows.Forms.TabControl>削除。</span><span class="sxs-lookup"><span data-stu-id="3b065-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="3b065-106">コントロールをその親にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="3b065-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="3b065-107"><xref:System.Windows.Forms.SplitContainer>コントロールの向きを変更する。</span><span class="sxs-lookup"><span data-stu-id="3b065-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="3b065-108">開発を高速化するために、多くのコントロールにスマートタグが用意されています。これは、デザイン時に1つのジェスチャでこのような一般的なタスクを実行できるようにする、状況依存のメニューです。</span><span class="sxs-lookup"><span data-stu-id="3b065-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="3b065-109">これらのタスクは*スマートタグ動詞*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3b065-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="3b065-110">スマートタグは、デザイナーの有効期間中はコントロールインスタンスにアタッチされたままであり、常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b065-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="3b065-111">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3b065-111">Create the project</span></span>

<span data-ttu-id="3b065-112">最初にプロジェクトを作成し、フォームを設定します。</span><span class="sxs-lookup"><span data-stu-id="3b065-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="3b065-113">Visual Studio で、 **SmartTagsExample**という名前の Windows ベースのアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b065-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="3b065-114">**Windows フォームデザイナー**でフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b065-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="3b065-115">スマートタグを使用する</span><span class="sxs-lookup"><span data-stu-id="3b065-115">Use smart tags</span></span>

<span data-ttu-id="3b065-116">スマートタグは、デザイン時に、それらを提供するコントロールで常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b065-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="3b065-117"><xref:System.Windows.Forms.TabControl> **ツールボックス**からフォームにをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3b065-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="3b065-118">の横![に表示](./media/vs-winformsmttagglyph.gif)されるスマートタググリフ (スマートタググリフ) に注意してください。<xref:System.Windows.Forms.TabControl></span><span class="sxs-lookup"><span data-stu-id="3b065-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="3b065-119">スマートタググリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b065-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="3b065-120">グリフの横に表示されるショートカットメニューで、 **[タブの追加]** 項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b065-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="3b065-121">新しいタブページがに<xref:System.Windows.Forms.TabControl>追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b065-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="3b065-122"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3b065-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="3b065-123">スマートタググリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b065-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="3b065-124">グリフの横に表示されるショートカットメニューで、 **[列の追加]** 項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b065-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="3b065-125"><xref:System.Windows.Forms.TableLayoutPanel>コントロールに新しい列が追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b065-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="3b065-126"><xref:System.Windows.Forms.SplitContainer> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3b065-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="3b065-127">スマートタググリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b065-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="3b065-128">グリフの横に表示されるショートカットメニューで、 **[横スプリッターの方向]** 項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b065-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="3b065-129"><xref:System.Windows.Forms.SplitContainer>コントロールのスプリッターバーが水平方向に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b065-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b065-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b065-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
