---
title: DataGrid コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: f50f32ad65dd621dee3847d72b5a186afcc4a86d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969154"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="5a88e-102">DataGrid コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="5a88e-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="5a88e-103"><xref:System.Windows.Forms.DataGridView> コントロールは、`DataGrid` コントロールに代わると共に追加の機能を提供します。ただし、`DataGrid` コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="5a88e-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="5a88e-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a88e-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="5a88e-105">Windows フォーム`DataGrid`コントロールは、ADO.NET データセットへのユーザーインターフェイスを提供し、表形式のデータを表示し、データソースの更新を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5a88e-105">The Windows Forms `DataGrid` control provides a user interface to ADO.NET datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="5a88e-106">`DataGrid` コントロールを有効なデータ ソースに対して設定すると、データの形式に基づいて列と行が作成されたコントロールが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a88e-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="5a88e-107">`DataGrid` コントロールを使用すると、1 つのテーブルまたは、複数のテーブル間の階層的なリレーションシップを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5a88e-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a88e-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a88e-108">In This Section</span></span>  
 [<span data-ttu-id="5a88e-109">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5a88e-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="5a88e-110">`DataGrid` コントロールの基本機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="5a88e-111">方法: デザイナーを使用して Windows フォーム DataGrid コントロールにテーブルと列を追加する</span><span class="sxs-lookup"><span data-stu-id="5a88e-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="5a88e-112">デザイナーを使用して `DataGrid` コントロールにテーブルと列を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="5a88e-113">方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する</span><span class="sxs-lookup"><span data-stu-id="5a88e-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="5a88e-114">プログラムによって `DataGrid` コントロールにテーブルと列を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="5a88e-115">方法: デザイナーを使用してデータソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="5a88e-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="5a88e-116">デザイナーを使用して、ADO.NET データセット`DataGrid`をコントロールにバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-116">Describes how to bind an ADO.NET dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="5a88e-117">方法: データソースへの Windows フォーム DataGrid コントロールのバインド</span><span class="sxs-lookup"><span data-stu-id="5a88e-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="5a88e-118">ADO.NET データセットを`DataGrid`コントロールにバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-118">Describes how to bind an ADO.NET dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="5a88e-119">方法: 実行時に表示されるデータを Windows フォーム DataGrid コントロールに変更する</span><span class="sxs-lookup"><span data-stu-id="5a88e-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="5a88e-120">`DataGrid` コントロール内でプログラムによってデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="5a88e-121">方法: デザイナーを使用して Windows フォーム DataGrid コントロールでマスター/詳細リストを作成する</span><span class="sxs-lookup"><span data-stu-id="5a88e-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="5a88e-122">デザイナーを使用して、親子のリレーションシップで結合されている 2 つのテーブルを、2 つの `DataGrid` コントロールに個別に表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="5a88e-123">方法: Windows フォーム DataGrid コントロールを使用してマスター/詳細リストを作成する</span><span class="sxs-lookup"><span data-stu-id="5a88e-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="5a88e-124">親子のリレーションシップで結合されている 2 つのテーブルを、2 つの `DataGrid` コントロールに個別に表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="5a88e-125">方法: Windows フォーム DataGrid コントロールの列を削除または非表示にする</span><span class="sxs-lookup"><span data-stu-id="5a88e-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="5a88e-126">`DataGrid` コントロール内で列を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="5a88e-127">方法: デザイナーを使用して Windows フォーム DataGrid コントロールの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="5a88e-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="5a88e-128">デザイナーを使用して、`DataGrid` コントロールの外観に関連するプロパティを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="5a88e-129">方法: Windows フォーム DataGrid コントロールの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="5a88e-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="5a88e-130">`DataGrid` コントロールの外観に関連するプロパティを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="5a88e-131">Windows フォームの DataGrid コントロール内の移動に使用できるキーボード ショートカット</span><span class="sxs-lookup"><span data-stu-id="5a88e-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="5a88e-132">`DataGrid` コントロール内の移動に使用できるキーボード ショートカットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="5a88e-133">方法: Windows フォーム DataGrid コントロールのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="5a88e-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="5a88e-134">ユーザーがクリックした `DataGrid` コントロール内のセルを確認する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="5a88e-135">方法: Windows フォーム DataGrid コントロールを使用した入力の検証</span><span class="sxs-lookup"><span data-stu-id="5a88e-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="5a88e-136">`DataGrid` コントロールにバインドされたデータセット内の入力データを検証する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5a88e-137">参照</span><span class="sxs-lookup"><span data-stu-id="5a88e-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="5a88e-138">クラスの概要につい<xref:System.Windows.Forms.DataGrid>て説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="5a88e-139">このプロパティを使用してコントロールをデータ<xref:System.Windows.Forms.DataGrid>にバインドする方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5a88e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a88e-140">Related Sections</span></span>  
 [<span data-ttu-id="5a88e-141">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="5a88e-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="5a88e-142">Windows フォームのデータ結合に関するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="5a88e-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a88e-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a88e-143">See also</span></span>

- [<span data-ttu-id="5a88e-144">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="5a88e-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="5a88e-145">Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて</span><span class="sxs-lookup"><span data-stu-id="5a88e-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
