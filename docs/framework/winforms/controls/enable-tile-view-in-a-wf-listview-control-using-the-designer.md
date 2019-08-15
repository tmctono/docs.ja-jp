---
title: '方法: デザイナーを使って Windows フォーム ListView コントロールの "並べて表示" ビューを有効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040363"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="17fa4-102">方法: デザイナーを使って Windows フォーム ListView コントロールの "並べて表示" ビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="17fa4-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="17fa4-103"><xref:System.Windows.Forms.ListView>コントロールのタイルビュー機能を使用すると、グラフィカルな情報とテキスト情報の間に視覚的なバランスを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="17fa4-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="17fa4-104">並べて表示ビューの項目で表示されるテキスト情報は、詳細ビュー用に定義されている列情報と同じ情報です。</span><span class="sxs-lookup"><span data-stu-id="17fa4-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="17fa4-105">並べて表示ビューは、 <xref:System.Windows.Forms.ListView>コントロールのグループ化機能または挿入マーク機能と組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="17fa4-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="17fa4-106">タイルビューでは、次の図に示すように、32 x 32 アイコンと数行のテキストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="17fa4-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="17fa4-107">![ListView コントロールのタイルビュー](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "タイルビューのアイコンとテキスト")</span><span class="sxs-lookup"><span data-stu-id="17fa4-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="17fa4-108">タイルビューのプロパティとメソッドを使用すると、各項目に対して表示する列フィールドを指定したり、タイルビューウィンドウ内のすべての項目のサイズと外観をまとめて制御したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="17fa4-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="17fa4-109">わかりやすくするために、タイルのテキストの最初の行は常に項目の名前です。変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="17fa4-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="17fa4-110">次の手順では、 <xref:System.Windows.Forms.ListView>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="17fa4-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="17fa4-111">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="17fa4-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="17fa4-112">並べて表示ビューを [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] で使用できるのは、アプリケーションから <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> メソッドを呼び出した場合だけです。</span><span class="sxs-lookup"><span data-stu-id="17fa4-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="17fa4-113">旧バージョンのオペレーティング システムでは、並べて表示ビューに関するコードがすべて無効になり、<xref:System.Windows.Forms.ListView> コントロールは大きなアイコンのビューで表示されます。</span><span class="sxs-lookup"><span data-stu-id="17fa4-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="17fa4-114">詳細については、「 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17fa4-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="17fa4-115">デザイナーでタイルビューを設定するには</span><span class="sxs-lookup"><span data-stu-id="17fa4-115">To set tile view in the designer</span></span>

1. <span data-ttu-id="17fa4-116">Visual Studio で、フォーム上<xref:System.Windows.Forms.ListView>のコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="17fa4-116">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="17fa4-117">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.ListView.View%2A>プロパティを選択し、 **[タイル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="17fa4-117">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="17fa4-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="17fa4-118">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="17fa4-119">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="17fa4-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
