---
title: DataGridView コントロールのシナリオ (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: 7350b0da19650b99bcfd456f93e994492a56d7e3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648089"
---
# <a name="datagridview-control-scenarios-windows-forms"></a><span data-ttu-id="d2b38-102">DataGridView コントロールのシナリオ (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d2b38-102">DataGridView Control Scenarios (Windows Forms)</span></span>
<span data-ttu-id="d2b38-103"><xref:System.Windows.Forms.DataGridView>コントロール、さまざまなデータ ソースから表形式のデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-103">With the <xref:System.Windows.Forms.DataGridView> control, you can display tabular data from a variety of data sources.</span></span> <span data-ttu-id="d2b38-104">単純な用途は、手動で設定できる、<xref:System.Windows.Forms.DataGridView>コントロールから直接データを操作します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-104">For simple uses, you can manually populate a <xref:System.Windows.Forms.DataGridView> and manipulate the data directly through the control.</span></span> <span data-ttu-id="d2b38-105">通常、ただし、外部データ ソースにデータを格納してコントロールにバインドして、<xref:System.Windows.Forms.BindingSource>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d2b38-105">Typically, however, you will store your data in an external data source and bind the control to it through a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="d2b38-106">このトピックでは、一部を実行する一般的なシナリオについて説明します、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d2b38-106">This topic describes some of the common scenarios that involve the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a><span data-ttu-id="d2b38-107">シナリオ 1:少量のデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-107">Scenario 1: Displaying Small Amounts of Data</span></span>  
 <span data-ttu-id="d2b38-108">表示する外部データ ソースにデータを格納する必要はありません、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d2b38-108">You do not have to store your data in an external data source to display it in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d2b38-109">少量のデータを使用する場合は、自分でコントロールを設定し、コントロールを通じてデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-109">If you are working with a small amount of data, you can populate the control yourself and manipulate the data through the control.</span></span> <span data-ttu-id="d2b38-110">これは呼び出されます*非バインド モード*します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-110">This is called *unbound mode*.</span></span> <span data-ttu-id="d2b38-111">詳細については、「[方法 :バインドされていない Windows フォーム DataGridView コントロールの作成](how-to-create-an-unbound-windows-forms-datagridview-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="d2b38-111">For more information, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="d2b38-112">シナリオの要点</span><span class="sxs-lookup"><span data-stu-id="d2b38-112">Scenario Key Points</span></span>  
  
- <span data-ttu-id="d2b38-113">非バインド モード設定コントロールを手動でします。</span><span class="sxs-lookup"><span data-stu-id="d2b38-113">In unbound mode, you populate the control manually.</span></span>  
  
- <span data-ttu-id="d2b38-114">非バインド モードは、読み取り専用データが少ない場合に特に適しています。</span><span class="sxs-lookup"><span data-stu-id="d2b38-114">Unbound mode is particularly suited for small amounts of read-only data.</span></span>  
  
- <span data-ttu-id="d2b38-115">非バインド モードはスプレッドシート形式または値の数がテーブルにも適しています。</span><span class="sxs-lookup"><span data-stu-id="d2b38-115">Unbound mode is also suited for spreadsheet-like or sparsely populated tables.</span></span>  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a><span data-ttu-id="d2b38-116">シナリオ 2:表示し、外部データ ソースに格納されたデータの更新</span><span class="sxs-lookup"><span data-stu-id="d2b38-116">Scenario 2: Viewing and Updating Data Stored in an External Data Source</span></span>  
 <span data-ttu-id="d2b38-117">使用することができます、<xref:System.Windows.Forms.DataGridView>ユーザーを通じて、データベース テーブルまたはビジネス オブジェクトのコレクションなどのデータ ソースに保持されるデータにアクセスできるユーザー インターフェイス (UI) コントロールです。</span><span class="sxs-lookup"><span data-stu-id="d2b38-117">You can use the <xref:System.Windows.Forms.DataGridView> control as a user interface (UI) through which users can access data kept in a data source such as a database table or a collection of business objects.</span></span> <span data-ttu-id="d2b38-118">詳細については、「[方法 :バインド データを Windows フォーム DataGridView コントロール](how-to-bind-data-to-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-118">For more information, see [How to: Bind Data to the Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="d2b38-119">シナリオの要点</span><span class="sxs-lookup"><span data-stu-id="d2b38-119">Scenario Key Points</span></span>  
  
- <span data-ttu-id="d2b38-120">バインド モードでは、データ ソースへの接続、データ ソースのプロパティまたはデータベースの列に基づく列を自動的に生成およびコントロールを自動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-120">Bound mode lets you connect to a data source, automatically generate columns based on the data source properties or database columns, and automatically populate the control.</span></span>  
  
- <span data-ttu-id="d2b38-121">バインド モードは、負荷の高いユーザー データとやり取りに適しています。</span><span class="sxs-lookup"><span data-stu-id="d2b38-121">Bound mode is suited for heavy user interaction with data.</span></span> <span data-ttu-id="d2b38-122">表示、データを書式設定することができ、ユーザー指定のデータをデータ ソースによって予期される形式に解析できます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-122">Data can be formatted for display, and user-specified data can be parsed into the format expected by the data source.</span></span> <span data-ttu-id="d2b38-123">ユーザーに警告およびエラーのあるセルを修正できるように、エラーおよびデータベースの制約のエラーの書式設定データ エントリを検出できます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-123">Data entry formatting errors and database constraint errors can be detected so that users can be warned and erroneous cells can be corrected.</span></span>  
  
- <span data-ttu-id="d2b38-124">列の並べ替えなどの追加機能は、フリーズ、および並べ替えは、ワークフローに最も便利な方法でデータを表示するユーザーに有効にします。</span><span class="sxs-lookup"><span data-stu-id="d2b38-124">Additional functionality such as column sorting, freezing, and reordering enable users to view data in the way most convenient for their workflow.</span></span>  
  
- <span data-ttu-id="d2b38-125">クリップボードのサポートでは、他のアプリケーションへのアプリケーションからデータをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-125">Clipboard support enables users to copy data from your application into other applications.</span></span>  
  
## <a name="scenario-3-advanced-data"></a><span data-ttu-id="d2b38-126">シナリオ 3:高度なデータ</span><span class="sxs-lookup"><span data-stu-id="d2b38-126">Scenario 3: Advanced Data</span></span>  
 <span data-ttu-id="d2b38-127">実装することで、コントロールとデータ間の相互作用を管理するには、標準的なデータ バインディング モデルが解決されない特別なニーズがあれば、*仮想モード*します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-127">If you have special needs that the standard data binding model does not address, you can manage the interaction between the control and your data by implementing *virtual mode*.</span></span> <span data-ttu-id="d2b38-128">仮想モード手段の情報とセルのコントロール要求について使用できる 1 つまたは複数のイベント ハンドラーの実装の実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="d2b38-128">Implementing virtual mode means implementing one or more event handlers that let the control request information about cells as the information is needed.</span></span>  
  
 <span data-ttu-id="d2b38-129">たとえば、大量のデータを使用する場合、最適な効率性を確保する仮想モードを実装します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-129">For example, if you work with large amounts of data, you may want to implement virtual mode to ensure optimal efficiency.</span></span> <span data-ttu-id="d2b38-130">仮想モードも別のデータ ソースから取得した列と共に表示する非バインド列の値を維持するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-130">Virtual mode is also useful for maintaining the values of unbound columns that you display along with columns retrieved from another data source.</span></span>  
  
 <span data-ttu-id="d2b38-131">仮想モードの詳細については、次を参照してください。[チュートリアル。仮想モードの実装で、Windows フォーム DataGridView コントロール](implementing-virtual-mode-wf-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-131">For more information about virtual mode, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="d2b38-132">シナリオの要点</span><span class="sxs-lookup"><span data-stu-id="d2b38-132">Scenario Key Points</span></span>  
  
- <span data-ttu-id="d2b38-133">仮想モードは、パフォーマンスを微調整する必要がある場合は、非常に大量のデータを表示するために適しています。</span><span class="sxs-lookup"><span data-stu-id="d2b38-133">Virtual mode is suited for displaying very large amounts of data when you need to fine-tune performance.</span></span>  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a><span data-ttu-id="d2b38-134">シナリオ 4:行と列を自動的にサイズ変更</span><span class="sxs-lookup"><span data-stu-id="d2b38-134">Scenario 4: Automatically Resizing Rows and Columns</span></span>  
 <span data-ttu-id="d2b38-135">定期的に更新するデータを表示するときにすべてのコンテンツが表示されていることを確認する行と列を自動的に変更できます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-135">When you display data that is regularly updated, you can automatically resize rows and columns to ensure that all content is visible.</span></span> <span data-ttu-id="d2b38-136"><xref:System.Windows.Forms.DataGridView>コントロールは、有効または無効にする手動のサイズ変更、特定の時点でサイズをプログラムで変更できるようにするいくつかのオプションを提供します。 または、自動的にサイズ変更されるたびに、変更をコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="d2b38-136">The <xref:System.Windows.Forms.DataGridView> control provides several options that let you enable or disable manual resizing, resize programmatically at specific times, or resize automatically whenever content changes.</span></span> <span data-ttu-id="d2b38-137">詳細については、次を参照してください。 [Windows フォームの DataGridView コントロールのサイズ変更オプション](sizing-options-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-137">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="d2b38-138">シナリオの要点</span><span class="sxs-lookup"><span data-stu-id="d2b38-138">Scenario Key Points</span></span>  
  
- <span data-ttu-id="d2b38-139">手動のサイズを変更すると、セルの高さと幅を調整するユーザーができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-139">Manual resizing enables users to adjust cell heights and widths.</span></span>  
  
- <span data-ttu-id="d2b38-140">自動サイズ変更するには、セルの内容がクリップされないように、セルのサイズを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-140">Automatic resizing enables you to maintain cell sizes so that cell content is never clipped.</span></span>  
  
- <span data-ttu-id="d2b38-141">プログラムによるサイズ変更するには、継続的な自動サイズ変更のパフォーマンスの低下を回避するために特定の時点でのセルのサイズを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-141">Programmatic resizing enables you to resize cells at specific times to avoid the performance penalty of continuous automatic resizing.</span></span>  
  
## <a name="scenario-5-simple-customization"></a><span data-ttu-id="d2b38-142">シナリオ 5:単純なカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d2b38-142">Scenario 5: Simple Customization</span></span>  
 <span data-ttu-id="d2b38-143"><xref:System.Windows.Forms.DataGridView>コントロールには、その基本的な外観と動作を変更するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d2b38-143">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to alter its basic appearance and behavior.</span></span> <span data-ttu-id="d2b38-144">詳細については、次を参照してください。 [Windows フォームの DataGridView コントロールのセル スタイル](cell-styles-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-144">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="d2b38-145">シナリオの要点</span><span class="sxs-lookup"><span data-stu-id="d2b38-145">Scenario Key Points</span></span>  
  
- <span data-ttu-id="d2b38-146"><xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトを使用して、色、フォント、書式設定、および複数のレベルと、コントロールの個々 の要素の位置情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-146"><xref:System.Windows.Forms.DataGridViewCellStyle> objects let you provide color, font, formatting, and positioning information at multiple levels and for individual elements of the control.</span></span>  
  
- <span data-ttu-id="d2b38-147">セル スタイルを階層化し、コードを再利用することができます、複数の要素によって共有されることができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-147">Cell styles can be layered and shared by multiple elements, letting you reuse code.</span></span>  
  
## <a name="scenario-6-advanced-customization"></a><span data-ttu-id="d2b38-148">シナリオ 6:高度なカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d2b38-148">Scenario 6: Advanced Customization</span></span>  
 <span data-ttu-id="d2b38-149"><xref:System.Windows.Forms.DataGridView>コントロールの外観と動作をカスタマイズするためのさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-149">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to customize its appearance and behavior.</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="d2b38-150">シナリオの要点</span><span class="sxs-lookup"><span data-stu-id="d2b38-150">Scenario Key Points</span></span>  
  
- <span data-ttu-id="d2b38-151">セルの描画コードを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-151">You can provide your own cell painting code.</span></span> <span data-ttu-id="d2b38-152">詳細については、「[方法 :Windows フォームの DataGridView コントロール内のセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-152">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="d2b38-153">独自の行の描画を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-153">You can provide your own row painting.</span></span> <span data-ttu-id="d2b38-154">たとえば、複数の列にまたがるコンテンツを含む行を作成するこれは、役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-154">This is useful, for example, to create rows with content that spans multiple columns.</span></span> <span data-ttu-id="d2b38-155">詳細については、「[方法 :Windows フォームの DataGridView コントロール内の行の外観をカスタマイズ](customize-the-appearance-of-rows-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-155">For more information, see [How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control](customize-the-appearance-of-rows-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="d2b38-156">セルの外観をカスタマイズする、独自のセルと列のクラスを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-156">You can implement your own cell and column classes to customize cell appearance.</span></span> <span data-ttu-id="d2b38-157">詳細については、「[方法 :セルのカスタマイズし、列で、Windows フォーム DataGridView コントロールのそれぞれの動作と外観を拡張することによって](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-157">For more information, see [How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).</span></span>  
  
- <span data-ttu-id="d2b38-158">組み込みの列の型によって提供されるもの以外のホスト コントロールに、独自のセルと列のクラスを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b38-158">You can implement your own cell and column classes to host controls other than the ones provided by the built-in column types.</span></span> <span data-ttu-id="d2b38-159">詳細については、「[方法 :Windows フォーム DataGridView Cells コントロールをホスト](how-to-host-controls-in-windows-forms-datagridview-cells.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2b38-159">For more information, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b38-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2b38-160">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d2b38-161">DataGridView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="d2b38-161">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
