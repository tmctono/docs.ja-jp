---
title: DataGridView コントロールの概要 (Windows フォーム)
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
ms.openlocfilehash: 4db2a8b0e30a6bb3db0c5c629d868bc01dc15a8c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648081"
---
# <a name="datagridview-control-overview-windows-forms"></a><span data-ttu-id="d4ea7-102">DataGridView コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d4ea7-102">DataGridView Control Overview (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="d4ea7-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="d4ea7-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="d4ea7-105"><xref:System.Windows.Forms.DataGridView>コントロールを表示し、さまざまな種類のデータ ソースから表形式のデータを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-105">With the <xref:System.Windows.Forms.DataGridView> control, you can display and edit tabular data from many different kinds of data sources.</span></span>  
  
 <span data-ttu-id="d4ea7-106">データ バインド、<xref:System.Windows.Forms.DataGridView>コントロールは簡単かつ直感的なおよび設定だけでは多くの場合、<xref:System.Windows.Forms.DataGridView.DataSource%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-106">Binding data to the <xref:System.Windows.Forms.DataGridView> control is straightforward and intuitive, and in many cases it is as simple as setting the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span> <span data-ttu-id="d4ea7-107">複数のリストまたはテーブルを含むデータ ソースにバインドする場合は、設定、<xref:System.Windows.Forms.DataGridView.DataMember%2A>プロパティをリストまたはテーブルにバインドするを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-107">When you bind to a data source that contains multiple lists or tables, set the <xref:System.Windows.Forms.DataGridView.DataMember%2A> property to a string that specifies the list or table to bind to.</span></span>  
  
 <span data-ttu-id="d4ea7-108"><xref:System.Windows.Forms.DataGridView>コントロールの次の一覧で説明されているクラスのインスタンスにバインドするための標準の Windows フォーム データ バインディング モデルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-108">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to instances of classes described in the following list:</span></span>  
  
- <span data-ttu-id="d4ea7-109">実装するクラス、 <xref:System.Collections.IList> 1 次元配列を含むインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-109">Any class that implements the <xref:System.Collections.IList> interface, including one-dimensional arrays.</span></span>  
  
- <span data-ttu-id="d4ea7-110">実装するクラス、<xref:System.ComponentModel.IListSource>インターフェイスなど、<xref:System.Data.DataTable>と<xref:System.Data.DataSet>クラス。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-110">Any class that implements the <xref:System.ComponentModel.IListSource> interface, such as the <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes.</span></span>  
  
- <span data-ttu-id="d4ea7-111">実装するクラス、<xref:System.ComponentModel.IBindingList>インターフェイスなど、<xref:System.ComponentModel.BindingList%601>クラス。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-111">Any class that implements the <xref:System.ComponentModel.IBindingList> interface, such as the <xref:System.ComponentModel.BindingList%601> class.</span></span>  
  
- <span data-ttu-id="d4ea7-112">実装するクラス、<xref:System.ComponentModel.IBindingListView>インターフェイスなど、<xref:System.Windows.Forms.BindingSource>クラス。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-112">Any class that implements the <xref:System.ComponentModel.IBindingListView> interface, such as the <xref:System.Windows.Forms.BindingSource> class.</span></span>  
  
 <span data-ttu-id="d4ea7-113"><xref:System.Windows.Forms.DataGridView>コントロールは、これらのインターフェイスによって返されるオブジェクトのパブリック プロパティまたはによって返されるプロパティのコレクションにデータ バインディングをサポートしている、<xref:System.ComponentModel.ICustomTypeDescriptor>インターフェイスを実装して、返されたオブジェクトの場合。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-113">The <xref:System.Windows.Forms.DataGridView> control supports data binding to the public properties of the objects returned by these interfaces or to the properties collection returned by an <xref:System.ComponentModel.ICustomTypeDescriptor> interface, if implemented on the returned objects.</span></span>  
  
 <span data-ttu-id="d4ea7-114">通常、バインド、<xref:System.Windows.Forms.BindingSource>コンポーネントおよび bind、<xref:System.Windows.Forms.BindingSource>コンポーネントを別にデータ ソースまたはビジネス オブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-114">Typically, you will bind to a <xref:System.Windows.Forms.BindingSource> component and bind the <xref:System.Windows.Forms.BindingSource> component to another data source or populate it with business objects.</span></span> <span data-ttu-id="d4ea7-115"><xref:System.Windows.Forms.BindingSource>コンポーネントが優先されるデータ ソースでさまざまなデータ ソースにバインドでき、自動的に多くのデータ バインドの問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-115">The <xref:System.Windows.Forms.BindingSource> component is the preferred data source because it can bind to a wide variety of data sources and can resolve many data binding issues automatically.</span></span> <span data-ttu-id="d4ea7-116">詳細については、次を参照してください。 [BindingSource コンポーネント](bindingsource-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-116">For more information, see [BindingSource Component](bindingsource-component.md).</span></span>  
  
 <span data-ttu-id="d4ea7-117"><xref:System.Windows.Forms.DataGridView>コントロールはでも使用できます*バインドされていない*ない基になるデータ ストアとのモード。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-117">The <xref:System.Windows.Forms.DataGridView> control can also be used in *unbound* mode, with no underlying data store.</span></span> <span data-ttu-id="d4ea7-118">非結合を使用するコード例については<xref:System.Windows.Forms.DataGridView>コントロールを参照してください[チュートリアル。作成、バインドされていない Windows フォーム DataGridView コントロール](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-118">For a code example that uses an unbound <xref:System.Windows.Forms.DataGridView> control, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="d4ea7-119"><xref:System.Windows.Forms.DataGridView>コントロール、構成可能かつ拡張可能なおよび多くのプロパティ、メソッド、およびその外観と動作をカスタマイズするイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-119">The <xref:System.Windows.Forms.DataGridView> control is highly configurable and extensible, and it provides many properties, methods, and events to customize its appearance and behavior.</span></span> <span data-ttu-id="d4ea7-120">表形式のデータを表示するには、Windows フォーム アプリケーションを設定する場合は、使用を検討して、<xref:System.Windows.Forms.DataGridView>前に他のユーザー コントロール (たとえば、 <xref:System.Windows.Forms.DataGrid>)。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-120">When you want your Windows Forms application to display tabular data, consider using the <xref:System.Windows.Forms.DataGridView> control before others (for example, <xref:System.Windows.Forms.DataGrid>).</span></span> <span data-ttu-id="d4ea7-121">読み取り専用の値を小さなグリッドを表示する場合、または数百万件のレコードのテーブルを編集するユーザーを有効にする場合、<xref:System.Windows.Forms.DataGridView>コントロールで、簡単にプログラミング可能なメモリ効率の高いソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-121">If you are displaying a small grid of read-only values, or if you are enabling a user to edit a table with millions of records, the <xref:System.Windows.Forms.DataGridView> control will provide you with a readily programmable, memory-efficient solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4ea7-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d4ea7-122">In This Section</span></span>  
 [<span data-ttu-id="d4ea7-123">DataGridView コントロール テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="d4ea7-123">DataGridView Control Technology Summary</span></span>](datagridview-control-technology-summary-windows-forms.md)  
 <span data-ttu-id="d4ea7-124">要約<xref:System.Windows.Forms.DataGridView>概念と、関連するクラスの使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-124">Summarizes <xref:System.Windows.Forms.DataGridView> control concepts and the use of related classes.</span></span>  
  
 [<span data-ttu-id="d4ea7-125">DataGridView コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d4ea7-125">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)  
 <span data-ttu-id="d4ea7-126">アーキテクチャについて説明します、<xref:System.Windows.Forms.DataGridView>コントロール、その型の階層と継承構造を説明します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-126">Describes the architecture of the <xref:System.Windows.Forms.DataGridView> control, explaining its type hierarchy and inheritance structure.</span></span>  
  
 [<span data-ttu-id="d4ea7-127">DataGridView コントロールのシナリオ</span><span class="sxs-lookup"><span data-stu-id="d4ea7-127">DataGridView Control Scenarios</span></span>](datagridview-control-scenarios-windows-forms.md)  
 <span data-ttu-id="d4ea7-128">最も一般的なシナリオについて説明します<xref:System.Windows.Forms.DataGridView>コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-128">Describes the most common scenarios in which <xref:System.Windows.Forms.DataGridView> controls are used.</span></span>  
  
 [<span data-ttu-id="d4ea7-129">DataGridView コントロールのコード ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="d4ea7-129">DataGridView Control Code Directory</span></span>](datagridview-control-code-directory-windows-forms.md)  
 <span data-ttu-id="d4ea7-130">さまざまなドキュメントのコード例へのリンクを提供します。<xref:System.Windows.Forms.DataGridView>タスク。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-130">Provides links to code examples in the documentation for various <xref:System.Windows.Forms.DataGridView> tasks.</span></span> <span data-ttu-id="d4ea7-131">コード例はタスクの種類ごとに分類されています。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-131">These examples are categorized by task type.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4ea7-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4ea7-132">Related Sections</span></span>  
 [<span data-ttu-id="d4ea7-133">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="d4ea7-133">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4ea7-134">Windows フォームで列の型について説明します<xref:System.Windows.Forms.DataGridView>コントロール情報を表示したり変更したり、情報を追加できるようにするために使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-134">Discusses the column types in the Windows Forms <xref:System.Windows.Forms.DataGridView> control used to display information and allow users to modify or add information.</span></span>  
  
 [<span data-ttu-id="d4ea7-135">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="d4ea7-135">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4ea7-136">コントロールに手動でデータを組み込む方法と、外部データ ソースからデータを取得する方法について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-136">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="d4ea7-137">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="d4ea7-137">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4ea7-138"><xref:System.Windows.Forms.DataGridView> のセルおよび行のカスタム描画と、セル、列、および行の派生型の作成について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-138">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="d4ea7-139">Windows フォーム DataGridView コントロールでのパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="d4ea7-139">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4ea7-140">大量のデータを扱うときのパフォーマンスの問題を避けるために、このコントロールを効率的に使用する方法について説明するトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="d4ea7-140">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ea7-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4ea7-141">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d4ea7-142">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="d4ea7-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="d4ea7-143">Windows フォーム DataGridView コントロールの既定の機能</span><span class="sxs-lookup"><span data-stu-id="d4ea7-143">Default Functionality in the Windows Forms DataGridView Control</span></span>](default-functionality-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d4ea7-144">Windows フォーム DataGridView コントロールの既定のキーボード処理とマウス処理</span><span class="sxs-lookup"><span data-stu-id="d4ea7-144">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
