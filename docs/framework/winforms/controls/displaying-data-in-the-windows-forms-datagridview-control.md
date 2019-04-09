---
title: Windows フォーム DataGridView コントロールでのデータの表示
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: c153d422470ff20491567aed70557e461dc2b4e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168637"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d40a1-102">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="d40a1-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d40a1-103">`DataGridView`のさまざまな外部データ ソースからデータを表示するコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="d40a1-104">または、コントロールに行と列を追加し、データを手動で設定できます。</span><span class="sxs-lookup"><span data-stu-id="d40a1-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="d40a1-105">データ ソースにコントロールをバインドすると、データ ソースのスキーマに基づいて、自動的に列を生成できます。</span><span class="sxs-lookup"><span data-stu-id="d40a1-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="d40a1-106">すると同様これらの列が表示されない場合は、非表示にするに削除、または再配置します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="d40a1-107">データ ソースから発生しない補足的なデータを表示するバインドされていない列を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d40a1-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="d40a1-108">(など、負の数値の背景色を変更するか、文字列の値を置換する必要がありますが、データを表示する書式設定の表示をカスタマイズすることもさらに、標準の形式 (通貨の形式の場合) などを使用して、データを表示することができます。対応するイメージ)。</span><span class="sxs-lookup"><span data-stu-id="d40a1-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d40a1-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d40a1-109">In This Section</span></span>  
 [<span data-ttu-id="d40a1-110">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="d40a1-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d40a1-111">コントロールにデータを設定するためのオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="d40a1-112">Windows フォーム DataGridView コントロールでのデータの書式設定</span><span class="sxs-lookup"><span data-stu-id="d40a1-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d40a1-113">セルの表示値を書式設定オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="d40a1-114">チュートリアル: バインドされていない Windows フォーム DataGridView コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="d40a1-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d40a1-115">コントロールにデータを手動で設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="d40a1-116">方法: データを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="d40a1-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d40a1-117">バインドすることによってコントロールにデータを設定する方法について説明します、`BindingSource`データベースから取得した情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="d40a1-118">方法: データバインドされた Windows フォーム DataGridView コントロールに列を自動生成する</span><span class="sxs-lookup"><span data-stu-id="d40a1-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="d40a1-119">バインドされたデータ ソースに基づく列を自動的に生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="d40a1-120">方法: Windows フォーム DataGridView コントロールから自動生成された列を削除する</span><span class="sxs-lookup"><span data-stu-id="d40a1-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="d40a1-121">非表示またはバインドされたデータ ソースから自動的に生成された列を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="d40a1-122">方法: Windows フォーム DataGridView コントロールの列の順序を変更する</span><span class="sxs-lookup"><span data-stu-id="d40a1-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d40a1-123">バインドされたデータ ソースから自動的に生成された列を並べ替える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="d40a1-124">方法: データバインドされた Windows フォーム DataGridView コントロールに非バインド列を追加する</span><span class="sxs-lookup"><span data-stu-id="d40a1-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="d40a1-125">バインドされていない、追加の列を表示することで、バインドされたデータ ソースからデータを補完する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="d40a1-126">方法: オブジェクトを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="d40a1-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="d40a1-127">各オブジェクトが独自の行で表示されるように、任意のオブジェクトのコレクションにコントロールをバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="d40a1-128">方法: Windows フォームの DataGridView 行にバインドされたオブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="d40a1-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="d40a1-129">コントロールの特定の行にバインドされているオブジェクトを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="d40a1-130">チュートリアル: Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームを作成する</span><span class="sxs-lookup"><span data-stu-id="d40a1-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="d40a1-131">2 つの関連するデータベース テーブルからデータを表示する方法について説明しますように値を 1 つに`DataGridView`コントロールが別のコントロールで現在選択されている行に依存します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="d40a1-132">方法: Windows フォーム DataGridView コントロールのデータの書式設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="d40a1-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d40a1-133">処理する方法について説明します、<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>イベントの値に応じてセルの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d40a1-134">参照</span><span class="sxs-lookup"><span data-stu-id="d40a1-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d40a1-135"><xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="d40a1-136">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.DataSource%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d40a1-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="d40a1-137"><xref:System.Windows.Forms.BindingSource> コンポーネントのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d40a1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d40a1-138">Related Sections</span></span>  
 [<span data-ttu-id="d40a1-139">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="d40a1-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d40a1-140">コントロールのデータに対してユーザーが実行できる追加および修正の仕方を変更する方法を説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="d40a1-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40a1-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="d40a1-141">See also</span></span>

- [<span data-ttu-id="d40a1-142">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="d40a1-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="d40a1-143">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="d40a1-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
