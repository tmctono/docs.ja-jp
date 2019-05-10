---
title: '方法: デザイナーで Windows フォーム DataGrid コントロールを使用してマスター/詳細リストを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 46825eeb2befab7f11a87451da53a773a6ce2ad2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648223"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a><span data-ttu-id="a069b-102">方法: デザイナーで Windows フォーム DataGrid コントロールを使用してマスター/詳細リストを作成する</span><span class="sxs-lookup"><span data-stu-id="a069b-102">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="a069b-103">
  <xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="a069b-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a069b-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a069b-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="a069b-105">場合、<xref:System.Data.DataSet>は一連の関連テーブルの 2 つ使用できます<xref:System.Windows.Forms.DataGrid>マスター/詳細形式でデータを表示するコントロール。</span><span class="sxs-lookup"><span data-stu-id="a069b-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master-detail format.</span></span> <span data-ttu-id="a069b-106">1 つ<xref:System.Windows.Forms.DataGrid>マスター グリッドに指定し、2 つ目は詳細グリッドに指定します。</span><span class="sxs-lookup"><span data-stu-id="a069b-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="a069b-107">マスター リストのエントリを選択すると、すべての関連する子エントリ、詳細の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a069b-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="a069b-108">たとえば場合、 <xref:System.Data.DataSet> Customers テーブルと関連する Orders テーブルを含むマスター グリッドに Customers テーブルと Orders テーブル詳細グリッドに指定します。</span><span class="sxs-lookup"><span data-stu-id="a069b-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="a069b-109">マスター グリッドから顧客を選択すると、すべての Orders テーブルでは、その顧客に関連付けられている注文の詳細グリッドで表示されます。</span><span class="sxs-lookup"><span data-stu-id="a069b-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
 <span data-ttu-id="a069b-110">次の手順が必要です、 **Windows アプリケーション**プロジェクト (**ファイル** > **新規** > **プロジェクト** >  **Visual c#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="a069b-110">The following procedure requires a **Windows Application** project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a069b-111">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a069b-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a069b-112">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a069b-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a069b-113">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a069b-113">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a><span data-ttu-id="a069b-114">デザイナーでマスター/詳細リストを作成するには</span><span class="sxs-lookup"><span data-stu-id="a069b-114">To create a master-details list in the designer</span></span>  
  
1. <span data-ttu-id="a069b-115">2 つ追加<xref:System.Windows.Forms.DataGrid>フォームのコントロール。</span><span class="sxs-lookup"><span data-stu-id="a069b-115">Add two <xref:System.Windows.Forms.DataGrid> controls to the form.</span></span> <span data-ttu-id="a069b-116">詳細については、「[方法 :Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="a069b-116">For more information, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="a069b-117">Visual Studio 2005 で、<xref:System.Windows.Forms.DataGrid>制御されていない、**ツールボックス**既定。</span><span class="sxs-lookup"><span data-stu-id="a069b-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="a069b-118">詳細については、「[方法 :項目をツールボックスに追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a069b-118">For more information, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a069b-119">次の手順は Visual Studio 2005 では、使用に適用されない、**データ ソース**デザイン時のデータ バインディングのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a069b-119">The following steps are not applicable to Visual Studio 2005, which uses the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="a069b-120">詳細については、次を参照してください。 [Visual Studio でのデータ コントロールをバインド](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)と[方法。表示では、データ フォーム アプリケーションを Windows に関連する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="a069b-120">For more information, see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) and [How to: Display Related Data in a Windows Forms Application](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).</span></span>  
  
2. <span data-ttu-id="a069b-121">2 つ以上のテーブルをドラッグして**サーバー エクスプ ローラー**をフォームにします。</span><span class="sxs-lookup"><span data-stu-id="a069b-121">Drag two or more tables from **Server Explorer** to the form.</span></span>  
  
3. <span data-ttu-id="a069b-122">**データ**メニューの **データセットの生成**します。</span><span class="sxs-lookup"><span data-stu-id="a069b-122">From the **Data** menu, select **Generate DataSet**.</span></span>  
  
4. <span data-ttu-id="a069b-123">XML デザイナーを使用してテーブル間のリレーションシップを設定します。</span><span class="sxs-lookup"><span data-stu-id="a069b-123">Set the relationships between the tables using the XML Designer.</span></span> <span data-ttu-id="a069b-124">詳細については、次を参照してください。"する方法。作成の XML スキーマとデータセットからの一対多リレーションシップ"msdn します。</span><span class="sxs-lookup"><span data-stu-id="a069b-124">For details, see "How to: Create One-to-Many Relationships in XML Schemas and Datasets" on MSDN.</span></span>  
  
5. <span data-ttu-id="a069b-125">選択して、リレーションシップを保存**すべて保存**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="a069b-125">Save the relationships by selecting **Save All** from the **File** menu.</span></span>  
  
6. <span data-ttu-id="a069b-126">構成、<xref:System.Windows.Forms.DataGrid>マスター グリッドを次のように指定するコントロール。</span><span class="sxs-lookup"><span data-stu-id="a069b-126">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the master grid, as follows:</span></span>  
  
    1. <span data-ttu-id="a069b-127">選択、<xref:System.Data.DataSet>でドロップダウン リストから、<xref:System.Windows.Forms.DataGrid.DataSource%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a069b-127">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2. <span data-ttu-id="a069b-128">マスター テーブル (たとえば、"Customers") でドロップダウン リストから選択、<xref:System.Windows.Forms.DataGrid.DataMember%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a069b-128">Select the master table (for example, "Customers") from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span>  
  
7. <span data-ttu-id="a069b-129">構成、<xref:System.Windows.Forms.DataGrid>詳細グリッドを次のように指定するコントロール。</span><span class="sxs-lookup"><span data-stu-id="a069b-129">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the details grid, as follows:</span></span>  
  
    1. <span data-ttu-id="a069b-130">選択、<xref:System.Data.DataSet>でドロップダウン リストから、<xref:System.Windows.Forms.DataGrid.DataSource%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a069b-130">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2. <span data-ttu-id="a069b-131">ドロップダウン リストからマスター/詳細テーブル間のリレーションシップ (たとえば、"Customers.CustOrd") を選択して、<xref:System.Windows.Forms.DataGrid.DataMember%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a069b-131">Select the relationship (for example, "Customers.CustOrd") between the master and detail tables from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span> <span data-ttu-id="a069b-132">リレーションシップを表示するには、プラス記号をクリックして、ノードを展開します (**+**) ドロップダウン リストのマスター テーブルの横にサインオンします。</span><span class="sxs-lookup"><span data-stu-id="a069b-132">In order to see the relationship, expand the node by clicking on the plus (**+**) sign next to the master table in the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a069b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a069b-133">See also</span></span>

- [<span data-ttu-id="a069b-134">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="a069b-134">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="a069b-135">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a069b-135">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="a069b-136">方法: Windows フォームの DataGrid コントロールをデータ ソースにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a069b-136">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [<span data-ttu-id="a069b-137">Visual Studio でのデータへのコントロールのバインド</span><span class="sxs-lookup"><span data-stu-id="a069b-137">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
