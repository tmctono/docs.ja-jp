---
title: DataGridView コントロールのアーキテクチャ
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742527"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="5fb5e-102">DataGridView コントロールのアーキテクチャ (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="5fb5e-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="5fb5e-103"><xref:System.Windows.Forms.DataGridView> コントロールとその関連クラスは、表形式のデータを表示および編集するための柔軟で拡張可能なシステムとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="5fb5e-104">これらのクラスはすべて、<xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間に含まれており、すべて "DataGridView" プレフィックスで名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="5fb5e-105">アーキテクチャの要素</span><span class="sxs-lookup"><span data-stu-id="5fb5e-105">Architecture Elements</span></span>  
 <span data-ttu-id="5fb5e-106">プライマリ <xref:System.Windows.Forms.DataGridView> コンパニオンクラスは <xref:System.Windows.Forms.DataGridViewElement>から派生します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="5fb5e-107">次のオブジェクトモデルは、<xref:System.Windows.Forms.DataGridViewElement> 継承階層を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![DataGridViewElement オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="5fb5e-109"><xref:System.Windows.Forms.DataGridViewElement> クラスは、親 <xref:System.Windows.Forms.DataGridView> コントロールへの参照を提供し、<xref:System.Windows.Forms.DataGridViewElementStates> 列挙体の値の組み合わせを表す値を保持する <xref:System.Windows.Forms.DataGridViewElement.State%2A> プロパティを持ちます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="5fb5e-110">以下のセクションでは、<xref:System.Windows.Forms.DataGridView> コンパニオンクラスについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="5fb5e-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="5fb5e-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="5fb5e-112"><xref:System.Windows.Forms.DataGridViewElementStates> 列挙体には次の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="5fb5e-113">この列挙体の値はビットごとの論理演算子と組み合わせることができるため、<xref:System.Windows.Forms.DataGridViewElement.State%2A> プロパティは一度に複数の状態を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="5fb5e-114">たとえば、<xref:System.Windows.Forms.DataGridViewElement> は、同時に <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>、<xref:System.Windows.Forms.DataGridViewElementStates.Selected>、および <xref:System.Windows.Forms.DataGridViewElementStates.Visible>にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="5fb5e-115">セルとバンド</span><span class="sxs-lookup"><span data-stu-id="5fb5e-115">Cells and Bands</span></span>  
 <span data-ttu-id="5fb5e-116"><xref:System.Windows.Forms.DataGridView> コントロールは、セルとバンドの2つの基本的な種類のオブジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="5fb5e-117">すべてのセルは <xref:System.Windows.Forms.DataGridViewCell> 基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="5fb5e-118">2種類のバンド (<xref:System.Windows.Forms.DataGridViewColumn> と <xref:System.Windows.Forms.DataGridViewRow>) は、どちらも <xref:System.Windows.Forms.DataGridViewBand> 基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="5fb5e-119"><xref:System.Windows.Forms.DataGridView> コントロールは複数のクラスと相互運用しますが、最も一般的に発生するのは、<xref:System.Windows.Forms.DataGridViewCell>、<xref:System.Windows.Forms.DataGridViewColumn>、および <xref:System.Windows.Forms.DataGridViewRow>です。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="5fb5e-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="5fb5e-120">DataGridViewCell</span></span>  
 <span data-ttu-id="5fb5e-121">セルは、<xref:System.Windows.Forms.DataGridView>の相互作用の基本単位です。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="5fb5e-122">表示はセルの中央に配置され、多くの場合、データ入力はセルを通じて実行されます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="5fb5e-123"><xref:System.Windows.Forms.DataGridViewRow> クラスの <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> コレクションを使用してセルにアクセスできます。また、<xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> コレクションを使用して、選択したセルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5fb5e-124">次のオブジェクトモデルは、この使用方法を示し、<xref:System.Windows.Forms.DataGridViewCell> 継承階層を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![DataGridViewCell オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="5fb5e-126"><xref:System.Windows.Forms.DataGridViewCell> 型は抽象基本クラスであり、すべてのセル型が派生します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="5fb5e-127"><xref:System.Windows.Forms.DataGridViewCell> とその派生型は Windows フォームコントロールではなく、一部のホスト Windows フォームコントロールです。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="5fb5e-128">セルでサポートされる編集機能は、通常、ホストされるコントロールによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="5fb5e-129"><xref:System.Windows.Forms.DataGridViewCell> オブジェクトは、Windows フォームコントロールと同じように、独自の外観と描画機能を制御しません。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="5fb5e-130">代わりに、<xref:System.Windows.Forms.DataGridView> は <xref:System.Windows.Forms.DataGridViewCell> オブジェクトの外観を担います。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="5fb5e-131"><xref:System.Windows.Forms.DataGridView> コントロールのプロパティとイベントを操作することによって、セルの外観と動作に大きな影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="5fb5e-132"><xref:System.Windows.Forms.DataGridView> コントロールの機能を超えるカスタマイズに特別な要件がある場合は、<xref:System.Windows.Forms.DataGridViewCell> またはその子クラスの1つから派生する独自のクラスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="5fb5e-133"><xref:System.Windows.Forms.DataGridViewCell>から派生したクラスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="5fb5e-134">カスタムセルの種類</span><span class="sxs-lookup"><span data-stu-id="5fb5e-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="5fb5e-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="5fb5e-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="5fb5e-136"><xref:System.Windows.Forms.DataGridView> コントロールのアタッチされたデータストアのスキーマは、<xref:System.Windows.Forms.DataGridView> コントロールの列で表されます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="5fb5e-137"><xref:System.Windows.Forms.DataGridView> コントロールの列にアクセスするには、<xref:System.Windows.Forms.DataGridView.Columns%2A> コレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="5fb5e-138">選択した列にアクセスするには、<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> コレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="5fb5e-139">次のオブジェクトモデルは、この使用方法を示し、<xref:System.Windows.Forms.DataGridViewColumn> 継承階層を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![DataGridViewColumn オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="5fb5e-141">主なセル型には、対応する列の型があります。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="5fb5e-142">これらは、<xref:System.Windows.Forms.DataGridViewColumn> の基本クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="5fb5e-143"><xref:System.Windows.Forms.DataGridViewColumn>から派生したクラスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="5fb5e-144">カスタム列の型</span><span class="sxs-lookup"><span data-stu-id="5fb5e-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="5fb5e-145">DataGridView 編集コントロール</span><span class="sxs-lookup"><span data-stu-id="5fb5e-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="5fb5e-146">高度な編集機能をサポートするセルは、通常、Windows フォームコントロールから派生したホストされたコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="5fb5e-147">これらのコントロールは、<xref:System.Windows.Forms.IDataGridViewEditingControl> インターフェイスも実装します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="5fb5e-148">次のオブジェクトモデルは、これらのコントロールの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![DataGridView 編集コントロールオブジェクトモデルの階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="5fb5e-150"><xref:System.Windows.Forms.DataGridView> コントロールには、次の編集コントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="5fb5e-151">独自の編集コントロールを作成する方法については、「[方法: Windows フォーム DataGridView セルのコントロールをホスト](how-to-host-controls-in-windows-forms-datagridview-cells.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="5fb5e-152">次の表は、セルの種類、列の種類、および編集コントロールの関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="5fb5e-153">セルの種類</span><span class="sxs-lookup"><span data-stu-id="5fb5e-153">Cell type</span></span>|<span data-ttu-id="5fb5e-154">ホストされるコントロール</span><span class="sxs-lookup"><span data-stu-id="5fb5e-154">Hosted control</span></span>|<span data-ttu-id="5fb5e-155">列の型</span><span class="sxs-lookup"><span data-stu-id="5fb5e-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="5fb5e-156">N/A</span><span class="sxs-lookup"><span data-stu-id="5fb5e-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="5fb5e-157">N/A</span><span class="sxs-lookup"><span data-stu-id="5fb5e-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="5fb5e-158">N/A</span><span class="sxs-lookup"><span data-stu-id="5fb5e-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="5fb5e-159">N/A</span><span class="sxs-lookup"><span data-stu-id="5fb5e-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="5fb5e-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="5fb5e-160">DataGridViewRow</span></span>  
 <span data-ttu-id="5fb5e-161"><xref:System.Windows.Forms.DataGridViewRow> クラスは、<xref:System.Windows.Forms.DataGridView> コントロールがアタッチされているデータストアのレコードのデータフィールドを表示します。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="5fb5e-162"><xref:System.Windows.Forms.DataGridView.Rows%2A> コレクションを使用して、<xref:System.Windows.Forms.DataGridView> コントロールの行にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="5fb5e-163"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> コレクションを使用して、選択した行にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="5fb5e-164">次のオブジェクトモデルは、この使用方法を示し、<xref:System.Windows.Forms.DataGridViewRow> 継承階層を示しています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![DataGridViewRow オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="5fb5e-166"><xref:System.Windows.Forms.DataGridViewRow> クラスから独自の型を派生させることもできますが、通常は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="5fb5e-167"><xref:System.Windows.Forms.DataGridView> コントロールには、<xref:System.Windows.Forms.DataGridViewRow> オブジェクトの動作をカスタマイズするための行関連のイベントとプロパティがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="5fb5e-168"><xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> プロパティを有効にすると、新しい行を追加するための特殊な行が最後の行として表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="5fb5e-169">この行は <xref:System.Windows.Forms.DataGridView.Rows%2A> コレクションの一部ですが、注意が必要な特別な機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="5fb5e-170">詳細については、「 [Windows フォーム DataGridView コントロールでの新しいレコードの行の使用](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb5e-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb5e-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fb5e-171">See also</span></span>

- [<span data-ttu-id="5fb5e-172">DataGridView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5fb5e-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="5fb5e-173">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5fb5e-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5fb5e-174">Windows フォーム DataGridView コントロールにおける新規レコード行の使用</span><span class="sxs-lookup"><span data-stu-id="5fb5e-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
