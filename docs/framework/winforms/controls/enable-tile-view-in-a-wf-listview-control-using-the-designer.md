---
title: '方法: デザイナーを使って Windows フォーム ListView コントロールの "並べて表示" ビューを有効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: f8c8a1b2e3d2adfa7daadd609051ffc304150efe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972121"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="0c5cb-102">方法: デザイナーを使って Windows フォーム ListView コントロールの "並べて表示" ビューを有効にする</span><span class="sxs-lookup"><span data-stu-id="0c5cb-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="0c5cb-103">並べて表示ビュー機能、<xref:System.Windows.Forms.ListView>コントロールでは、グラフィカルとテキストの情報をバランスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="0c5cb-104">並べて表示ビューの項目で表示されるテキスト情報は、詳細ビュー用に定義されている列情報と同じ情報です。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="0c5cb-105">グループ化またはカーソルのいずれかと組み合わせて、並べて表示ビューはマークの機能、<xref:System.Windows.Forms.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="0c5cb-106">並べて表示ビューでは、次の図のように、32 x 32 アイコンと数行のテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>  
  
 <span data-ttu-id="0c5cb-107">![ListView コントロール内のタイル ビュー](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "タイル表示のアイコンとテキスト")</span><span class="sxs-lookup"><span data-stu-id="0c5cb-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>  
  
 <span data-ttu-id="0c5cb-108">並べて表示ビューのプロパティとメソッドを使用すると、各項目を表示して、まとめてサイズとタイル ビュー ウィンドウ内のすべての項目の外観を制御する列フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="0c5cb-109">わかりやすくするために、タイル内のテキストの最初の行は常に、項目の名前です。変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>  
  
 <span data-ttu-id="0c5cb-110">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="0c5cb-111">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c5cb-112">並べて表示ビューを [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] で使用できるのは、アプリケーションから <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> メソッドを呼び出した場合だけです。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0c5cb-113">旧バージョンのオペレーティング システムでは、並べて表示ビューに関するコードがすべて無効になり、<xref:System.Windows.Forms.ListView> コントロールは大きなアイコンのビューで表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="0c5cb-114">詳細については、「 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="0c5cb-115">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0c5cb-116">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0c5cb-117">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-117">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="0c5cb-118">並べて表示ビューをデザイナーで設定するには</span><span class="sxs-lookup"><span data-stu-id="0c5cb-118">To set tile view in the designer</span></span>  
  
1. <span data-ttu-id="0c5cb-119">選択、<xref:System.Windows.Forms.ListView>フォーム上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-119">Select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>  
  
2. <span data-ttu-id="0c5cb-120">**プロパティ**ウィンドウで、<xref:System.Windows.Forms.ListView.View%2A>プロパティ選択**タイル**します。</span><span class="sxs-lookup"><span data-stu-id="0c5cb-120">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5cb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c5cb-121">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="0c5cb-122">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="0c5cb-122">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
