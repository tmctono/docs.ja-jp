---
title: DataGridView コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
ms.openlocfilehash: 74de5b449525be9ff93fcbef0ddabd041470177c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742486"
---
# <a name="datagridview-control-overview-windows-forms"></a><span data-ttu-id="c4df6-102">DataGridView コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="c4df6-102">DataGridView Control Overview (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="c4df6-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4df6-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="c4df6-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4df6-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="c4df6-105"><xref:System.Windows.Forms.DataGridView> コントロールを使用すると、さまざまな種類のデータソースの表形式データを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="c4df6-105">With the <xref:System.Windows.Forms.DataGridView> control, you can display and edit tabular data from many different kinds of data sources.</span></span>  
  
 <span data-ttu-id="c4df6-106"><xref:System.Windows.Forms.DataGridView> コントロールにデータをバインドするのは簡単で直観的です。多くの場合、<xref:System.Windows.Forms.DataGridView.DataSource%2A> プロパティを設定するのと同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="c4df6-106">Binding data to the <xref:System.Windows.Forms.DataGridView> control is straightforward and intuitive, and in many cases it is as simple as setting the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span> <span data-ttu-id="c4df6-107">複数のリストまたはテーブルを含むデータソースにバインドする場合は、バインド先のリストまたはテーブルを指定する文字列に <xref:System.Windows.Forms.DataGridView.DataMember%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-107">When you bind to a data source that contains multiple lists or tables, set the <xref:System.Windows.Forms.DataGridView.DataMember%2A> property to a string that specifies the list or table to bind to.</span></span>  
  
 <span data-ttu-id="c4df6-108"><xref:System.Windows.Forms.DataGridView> コントロールは、標準の Windows フォームデータバインディングモデルをサポートするため、次の一覧に示すクラスのインスタンスにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="c4df6-108">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to instances of classes described in the following list:</span></span>  
  
- <span data-ttu-id="c4df6-109"><xref:System.Collections.IList> インターフェイスを実装する任意のクラス (1 次元配列を含む)。</span><span class="sxs-lookup"><span data-stu-id="c4df6-109">Any class that implements the <xref:System.Collections.IList> interface, including one-dimensional arrays.</span></span>  
  
- <span data-ttu-id="c4df6-110"><xref:System.ComponentModel.IListSource> インターフェイスを実装する任意のクラス (<xref:System.Data.DataTable> や <xref:System.Data.DataSet> クラスなど)。</span><span class="sxs-lookup"><span data-stu-id="c4df6-110">Any class that implements the <xref:System.ComponentModel.IListSource> interface, such as the <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes.</span></span>  
  
- <span data-ttu-id="c4df6-111"><xref:System.ComponentModel.IBindingList> インターフェイスを実装する任意のクラス (<xref:System.ComponentModel.BindingList%601> クラスなど)。</span><span class="sxs-lookup"><span data-stu-id="c4df6-111">Any class that implements the <xref:System.ComponentModel.IBindingList> interface, such as the <xref:System.ComponentModel.BindingList%601> class.</span></span>  
  
- <span data-ttu-id="c4df6-112"><xref:System.ComponentModel.IBindingListView> インターフェイスを実装する任意のクラス (<xref:System.Windows.Forms.BindingSource> クラスなど)。</span><span class="sxs-lookup"><span data-stu-id="c4df6-112">Any class that implements the <xref:System.ComponentModel.IBindingListView> interface, such as the <xref:System.Windows.Forms.BindingSource> class.</span></span>  
  
 <span data-ttu-id="c4df6-113"><xref:System.Windows.Forms.DataGridView> コントロールは、これらのインターフェイスによって返されるオブジェクトのパブリックプロパティへのデータバインディング、または返されたオブジェクトに実装されている場合は <xref:System.ComponentModel.ICustomTypeDescriptor> インターフェイスによって返される properties コレクションへのデータバインディングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c4df6-113">The <xref:System.Windows.Forms.DataGridView> control supports data binding to the public properties of the objects returned by these interfaces or to the properties collection returned by an <xref:System.ComponentModel.ICustomTypeDescriptor> interface, if implemented on the returned objects.</span></span>  
  
 <span data-ttu-id="c4df6-114">通常は、<xref:System.Windows.Forms.BindingSource> コンポーネントにバインドし、<xref:System.Windows.Forms.BindingSource> コンポーネントを別のデータソースにバインドするか、ビジネスオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-114">Typically, you will bind to a <xref:System.Windows.Forms.BindingSource> component and bind the <xref:System.Windows.Forms.BindingSource> component to another data source or populate it with business objects.</span></span> <span data-ttu-id="c4df6-115"><xref:System.Windows.Forms.BindingSource> コンポーネントは、さまざまなデータソースにバインドできるため、データバインディングに関する多くの問題を自動的に解決できるため、推奨されるデータソースです。</span><span class="sxs-lookup"><span data-stu-id="c4df6-115">The <xref:System.Windows.Forms.BindingSource> component is the preferred data source because it can bind to a wide variety of data sources and can resolve many data binding issues automatically.</span></span> <span data-ttu-id="c4df6-116">詳細については、「 [BindingSource コンポーネント](bindingsource-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4df6-116">For more information, see [BindingSource Component](bindingsource-component.md).</span></span>  
  
 <span data-ttu-id="c4df6-117"><xref:System.Windows.Forms.DataGridView> コントロールは、基になるデータストアのない*非バインド*モードでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4df6-117">The <xref:System.Windows.Forms.DataGridView> control can also be used in *unbound* mode, with no underlying data store.</span></span> <span data-ttu-id="c4df6-118">バインドされていない <xref:System.Windows.Forms.DataGridView> コントロールを使用するコード例については、「チュートリアル: バインドされていない[Windows フォーム DataGridView コントロールの作成](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4df6-118">For a code example that uses an unbound <xref:System.Windows.Forms.DataGridView> control, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="c4df6-119"><xref:System.Windows.Forms.DataGridView> コントロールは、高度な構成と拡張が可能で、外観と動作をカスタマイズするための多数のプロパティ、メソッド、およびイベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c4df6-119">The <xref:System.Windows.Forms.DataGridView> control is highly configurable and extensible, and it provides many properties, methods, and events to customize its appearance and behavior.</span></span> <span data-ttu-id="c4df6-120">Windows フォームアプリケーションで表形式のデータを表示する場合は、他のコントロール (たとえば、<xref:System.Windows.Forms.DataGrid>) の前に <xref:System.Windows.Forms.DataGridView> コントロールを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c4df6-120">When you want your Windows Forms application to display tabular data, consider using the <xref:System.Windows.Forms.DataGridView> control before others (for example, <xref:System.Windows.Forms.DataGrid>).</span></span> <span data-ttu-id="c4df6-121">読み取り専用の値を持つ小さいグリッドを表示する場合、またはユーザーが何百万ものレコードを含むテーブルを編集できるようにする場合は、<xref:System.Windows.Forms.DataGridView> 制御によって、簡単にプログラミング可能なメモリ効率の高いソリューションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c4df6-121">If you are displaying a small grid of read-only values, or if you are enabling a user to edit a table with millions of records, the <xref:System.Windows.Forms.DataGridView> control will provide you with a readily programmable, memory-efficient solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4df6-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c4df6-122">In This Section</span></span>  
 [<span data-ttu-id="c4df6-123">DataGridView コントロール テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="c4df6-123">DataGridView Control Technology Summary</span></span>](datagridview-control-technology-summary-windows-forms.md)  
 <span data-ttu-id="c4df6-124"><xref:System.Windows.Forms.DataGridView> コントロールの概念と関連クラスの使用についてまとめます。</span><span class="sxs-lookup"><span data-stu-id="c4df6-124">Summarizes <xref:System.Windows.Forms.DataGridView> control concepts and the use of related classes.</span></span>  
  
 [<span data-ttu-id="c4df6-125">DataGridView コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c4df6-125">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)  
 <span data-ttu-id="c4df6-126">型階層と継承構造を説明する <xref:System.Windows.Forms.DataGridView> コントロールのアーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-126">Describes the architecture of the <xref:System.Windows.Forms.DataGridView> control, explaining its type hierarchy and inheritance structure.</span></span>  
  
 [<span data-ttu-id="c4df6-127">DataGridView コントロールのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c4df6-127">DataGridView Control Scenarios</span></span>](datagridview-control-scenarios-windows-forms.md)  
 <span data-ttu-id="c4df6-128"><xref:System.Windows.Forms.DataGridView> コントロールを使用する最も一般的なシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-128">Describes the most common scenarios in which <xref:System.Windows.Forms.DataGridView> controls are used.</span></span>  
  
 [<span data-ttu-id="c4df6-129">DataGridView コントロールのコード ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="c4df6-129">DataGridView Control Code Directory</span></span>](datagridview-control-code-directory-windows-forms.md)  
 <span data-ttu-id="c4df6-130">さまざまな <xref:System.Windows.Forms.DataGridView> タスクに関するドキュメントのコード例へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-130">Provides links to code examples in the documentation for various <xref:System.Windows.Forms.DataGridView> tasks.</span></span> <span data-ttu-id="c4df6-131">コード例はタスクの種類ごとに分類されています。</span><span class="sxs-lookup"><span data-stu-id="c4df6-131">These examples are categorized by task type.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c4df6-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4df6-132">Related Sections</span></span>  
 [<span data-ttu-id="c4df6-133">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="c4df6-133">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c4df6-134">情報を表示し、ユーザーが情報を変更または追加できるようにするために使用される、Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロール内の列の型について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-134">Discusses the column types in the Windows Forms <xref:System.Windows.Forms.DataGridView> control used to display information and allow users to modify or add information.</span></span>  
  
 [<span data-ttu-id="c4df6-135">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="c4df6-135">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c4df6-136">コントロールに手動でデータを組み込む方法と、外部データ ソースからデータを取得する方法について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-136">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="c4df6-137">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c4df6-137">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c4df6-138"><xref:System.Windows.Forms.DataGridView> のセルおよび行のカスタム描画と、セル、列、および行の派生型の作成について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-138">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="c4df6-139">Windows フォーム DataGridView コントロールでのパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="c4df6-139">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c4df6-140">大量のデータを扱うときのパフォーマンスの問題を避けるために、このコントロールを効率的に使用する方法について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="c4df6-140">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4df6-141">参照</span><span class="sxs-lookup"><span data-stu-id="c4df6-141">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="c4df6-142">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="c4df6-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="c4df6-143">Windows フォーム DataGridView コントロールの既定の機能</span><span class="sxs-lookup"><span data-stu-id="c4df6-143">Default Functionality in the Windows Forms DataGridView Control</span></span>](default-functionality-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c4df6-144">Windows フォーム DataGridView コントロールの既定のキーボード処理とマウス処理</span><span class="sxs-lookup"><span data-stu-id="c4df6-144">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
