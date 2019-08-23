---
title: 組み込みのオーナー描画サポートを備えたコントロール
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: f0d4b99f9ee0134fc7334a941dd5ef4fd7ba3df3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930190"
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="419ce-102">組み込みのオーナー描画サポートを備えたコントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="419ce-103">Windows フォームのオーナー描画 (カスタム描画とも呼ばれます) は、特定のコントロールの外観を変更するための手法です。</span><span class="sxs-lookup"><span data-stu-id="419ce-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="419ce-104">このトピックの "コントロール" という語は、 <xref:System.Windows.Forms.Control>または<xref:System.ComponentModel.Component>から派生したクラスを意味するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="419ce-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="419ce-105">通常、コントロールの外観を決定するためになど<xref:System.Windows.Forms.Control.BackColor%2A>のプロパティ設定を使用して、ウィンドウの描画を自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="419ce-106">オーナー描画では、描画プロセスを引き継いで、プロパティでは設定できない外観の要素を変更できます。</span><span class="sxs-lookup"><span data-stu-id="419ce-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="419ce-107">たとえば、多くのコントロールでは表示されるテキストの色を設定できますが、1 つの色に制限されます。</span><span class="sxs-lookup"><span data-stu-id="419ce-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="419ce-108">オーナー描画では、テキストの一部分を黒で表示し、別の部分を赤で表示する、といったことができます。</span><span class="sxs-lookup"><span data-stu-id="419ce-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="419ce-109">実際には、オーナー描画はフォームでのグラフィックスの描画に似ています。</span><span class="sxs-lookup"><span data-stu-id="419ce-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="419ce-110">たとえば、フォームの<xref:System.Windows.Forms.Control.Paint>イベントのハンドラーでグラフィックスメソッドを使用して`ListBox`コントロールをエミュレートすることができますが、すべてのユーザー操作を処理する独自のコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419ce-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="419ce-111">オーナー描画では、コントロールは独自のコードを使って内容を描画しますが、それ以外については組み込み機能がすべて保持されます。</span><span class="sxs-lookup"><span data-stu-id="419ce-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="419ce-112">グラフィックス メソッドを使うと、コントロール内の各項目を描画したり、各項目の一部だけカスタマイズして他の部分は既定の外観を使ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="419ce-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="419ce-113">Windows フォーム コントロールでのオーナー描画</span><span class="sxs-lookup"><span data-stu-id="419ce-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="419ce-114">オーナー描画をサポートしているコントロールでオーナー描画を実行するには、通常、1 つのプロパティを設定し、1 つまたは複数のイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="419ce-115">オーナー描画をサポートしているほとんどのコントロールには、コントロールの描画時に描画関連のイベントが発生するかどうかを示す `OwnerDraw` または `DrawMode` プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="419ce-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="419ce-116">`OwnerDraw` または `DrawMode` プロパティを持たないコントロールには、自動的に発生する描画イベントを提供する `DataGridView` コントロールと、独自の描画関連イベントを持つ外部レンダリング クラスを使って描画される `ToolStrip` コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="419ce-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="419ce-117">さまざまな種類の描画イベントがありますが、標準的な描画イベントはコントロール内の 1 つの項目を描画するために発生します。</span><span class="sxs-lookup"><span data-stu-id="419ce-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="419ce-118">イベント ハンドラーは、描画される項目に関する情報と、その描画に使用できるツールを含む、`EventArgs` オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="419ce-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="419ce-119">たとえば、このオブジェクトには通常、親コレクション内の項目のインデックス番号、項目<xref:System.Drawing.Rectangle>の表示境界を示す、 <xref:System.Drawing.Graphics>および描画メソッドを呼び出すためのオブジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="419ce-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="419ce-120">一部のイベントの `EventArgs` オブジェクトでは、項目に関する追加情報と、背景やフォーカス四角形などの項目の一部分を既定で描画するために呼び出すことができるメソッドが提供されます。</span><span class="sxs-lookup"><span data-stu-id="419ce-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="419ce-121">オーナー描画のカスタマイズを含む再利用可能なコントロールを作成するには、オーナー描画をサポートするコントロール クラスから派生する新しいクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="419ce-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="419ce-122">描画イベントを処理するのではなく、新しいクラスの適切な `On`<*イベント名*> メソッドのオーバーライドにオーナー描画のコードを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="419ce-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="419ce-123">この場合、コントロールのユーザーがオーナー描画イベントを処理して追加のカスタマイズを提供できるように、基底クラスの `On`<*イベント名*> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="419ce-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="419ce-124">次の Windows フォーム コントロールは、すべてのバージョンの .NET Framework でオーナー描画をサポートします。</span><span class="sxs-lookup"><span data-stu-id="419ce-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <span data-ttu-id="419ce-125"><xref:System.Windows.Forms.MenuItem>(および<xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu>で使用)</span><span class="sxs-lookup"><span data-stu-id="419ce-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
- <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="419ce-126">次のコントロールは、.NET Framework 2.0 でのみ所有者の描画をサポートします。</span><span class="sxs-lookup"><span data-stu-id="419ce-126">The following controls support owner drawing only in .NET Framework 2.0:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="419ce-127">次のコントロールはオーナー描画をサポートしており、.NET Framework 2.0 で新しく追加されています。</span><span class="sxs-lookup"><span data-stu-id="419ce-127">The following controls support owner drawing and are new in .NET Framework 2.0:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="419ce-128">以下のセクションでは、これらの各コントロールについてさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="419ce-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="419ce-129">ListBox コントロールと ComboBox コントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="419ce-130">コントロールとコントロールを使用すると<xref:System.Windows.Forms.ComboBox> 、コントロール内の個々の項目を1つのサイズで、またはさまざまなサイズで描画できます。 <xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="419ce-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="419ce-131">コントロールはコントロール<xref:System.Windows.Forms.ListBox>から派生しますが、オーナー描画をサポートしていません。 <xref:System.Windows.Forms.CheckedListBox></span><span class="sxs-lookup"><span data-stu-id="419ce-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="419ce-132">各項目を同じサイズで描画するには`DrawMode` 、プロパティ<xref:System.Windows.Forms.DrawMode.OwnerDrawFixed>をに設定`DrawItem`し、イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="419ce-133">異なるサイズを使用して各項目を描画する`DrawMode`には<xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> 、プロパティをに`MeasureItem`設定`DrawItem`し、イベントとイベントの両方を処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="419ce-134">`MeasureItem` イベントを使うと、項目の `DrawItem` イベントが発生する前に、その項目のサイズを指定できます。</span><span class="sxs-lookup"><span data-stu-id="419ce-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="419ce-135">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-135">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [<span data-ttu-id="419ce-136">方法: ComboBox コントロールでの可変サイズのテキストの作成</span><span class="sxs-lookup"><span data-stu-id="419ce-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="419ce-137">MenuItem コンポーネント</span><span class="sxs-lookup"><span data-stu-id="419ce-137">MenuItem Component</span></span>  
 <span data-ttu-id="419ce-138">コンポーネントは、コンポーネント<xref:System.Windows.Forms.MainMenu>または<xref:System.Windows.Forms.ContextMenu>コンポーネントの1つのメニュー項目を表します。 <xref:System.Windows.Forms.MenuItem></span><span class="sxs-lookup"><span data-stu-id="419ce-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="419ce-139">を描画<xref:System.Windows.Forms.MenuItem>するには、 `OwnerDraw`その`DrawItem`プロパティ`true`をに設定し、イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="419ce-140">`DrawItem` イベントが発生する前にメニュー項目のサイズをカスタマイズするには、項目の`MeasureItem` イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="419ce-141">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-141">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="419ce-142">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-142">TabControl Control</span></span>  
 <span data-ttu-id="419ce-143"><xref:System.Windows.Forms.TabControl>コントロールを使用すると、コントロールに個々のタブを描画できます。</span><span class="sxs-lookup"><span data-stu-id="419ce-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="419ce-144">オーナー描画は、タブのみに影響します。<xref:System.Windows.Forms.TabPage>コンテンツは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="419ce-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="419ce-145">で<xref:System.Windows.Forms.TabControl>各タブを描画するには、 `DrawMode` `DrawItem`プロパティを<xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed>に設定し、イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="419ce-146">このイベントは、コントロールにタブが表示されている場合にのみ、タブごとに 1 回発生します。</span><span class="sxs-lookup"><span data-stu-id="419ce-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="419ce-147">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-147">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="419ce-148">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="419ce-148">ToolTip Component</span></span>  
 <span data-ttu-id="419ce-149"><xref:System.Windows.Forms.ToolTip>コンポーネントを使用すると、表示されるときにツールヒント全体を描画できます。</span><span class="sxs-lookup"><span data-stu-id="419ce-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="419ce-150">を描画<xref:System.Windows.Forms.ToolTip>するには、 `OwnerDraw`その`Draw`プロパティ`true`をに設定し、イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="419ce-151">イベント<xref:System.Windows.Forms.ToolTip>が発生`Draw`する前にのサイズをカスタマイズするには`Popup` 、イベントを処理<xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A>し、イベントハンドラーのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="419ce-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="419ce-152">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-152">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="419ce-153">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-153">ListView Control</span></span>  
 <span data-ttu-id="419ce-154"><xref:System.Windows.Forms.ListView>コントロールを使用すると、コントロールに個々の項目、サブ項目、および列ヘッダーを描画できます。</span><span class="sxs-lookup"><span data-stu-id="419ce-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="419ce-155">コントロールのオーナー描画を有効にするには、`OwnerDraw` プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="419ce-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="419ce-156">コントロール内の各項目を描画するには、`DrawItem` イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="419ce-157"><xref:System.Windows.Forms.ListView.View%2A>プロパティがに<xref:System.Windows.Forms.View.Details>設定されている場合に、コントロール内の各サブ項目または`DrawSubItem`列`DrawColumnHeader`ヘッダーを描画するには、イベントおよびイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="419ce-158">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-158">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="419ce-159">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-159">TreeView Control</span></span>  
 <span data-ttu-id="419ce-160"><xref:System.Windows.Forms.TreeView>コントロールを使用すると、コントロールに個々のノードを描画できます。</span><span class="sxs-lookup"><span data-stu-id="419ce-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="419ce-161">各ノードに表示されているテキストのみを描画`DrawMode`するに<xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText>は、プロパティ`DrawNode`をに設定し、イベントを処理してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="419ce-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="419ce-162">各ノードのすべての要素を描画するに`DrawMode`は、 <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll>プロパティをに`DrawNode`設定し、イベントを処理して必要な要素を描画します。たとえば、テキスト、アイコン、チェックボックス、プラス記号とマイナス記号、ノードを接続する線などです。</span><span class="sxs-lookup"><span data-stu-id="419ce-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="419ce-163">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-163">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="419ce-164">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-164">DataGridView Control</span></span>  
 <span data-ttu-id="419ce-165"><xref:System.Windows.Forms.DataGridView>コントロールを使用すると、コントロールに個々のセルと行を描画できます。</span><span class="sxs-lookup"><span data-stu-id="419ce-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="419ce-166">個別のセルを描画するには、`CellPainting` イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="419ce-167">個別の行または行の要素を描画するには、`RowPrePaint` イベントと `RowPostPaint` イベントの一方または両方を処理します。</span><span class="sxs-lookup"><span data-stu-id="419ce-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="419ce-168">`RowPrePaint` イベントは行内のセルが描画される前に発生し、`RowPostPaint` イベントはセルが描画された後で発生します。</span><span class="sxs-lookup"><span data-stu-id="419ce-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="419ce-169">両方のイベントと `CellPainting` イベントを処理して、行の背景、個々のセル、行の前景を個別に描画できます。または、必要な部分については個別にカスタマイズを提供し、行の他の要素には既定の表示を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="419ce-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="419ce-170">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-170">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [<span data-ttu-id="419ce-171">方法: Windows フォーム DataGridView コントロールでのセルの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="419ce-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [<span data-ttu-id="419ce-172">方法: Windows フォーム DataGridView コントロールでの行の外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="419ce-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="419ce-173">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-173">ToolStrip Control</span></span>  
 <span data-ttu-id="419ce-174"><xref:System.Windows.Forms.ToolStrip>また、派生したコントロールを使用すると、外観の任意の側面をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="419ce-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="419ce-175"><xref:System.Windows.Forms.ToolStrip>コントロールのカスタム表示を提供するには`Renderer` 、 <xref:System.Windows.Forms.ToolStrip>、 <xref:System.Windows.Forms.ToolStripManager>、 <xref:System.Windows.Forms.ToolStripPanel>、または<xref:System.Windows.Forms.ToolStripContentPanel>のプロパティを`ToolStripRenderer`オブジェクトに設定し、によって提供される多数の描画イベントの1つ以上を処理します。`ToolStripRenderer`クラス。</span><span class="sxs-lookup"><span data-stu-id="419ce-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="419ce-176">または、特定`Renderer` <xref:System.Windows.Forms.ToolStripProfessionalRenderer> <xref:System.Windows.Forms.ToolStripSystemRenderer> `ToolStripRenderer`の`On` *EventName*メソッドを実装またはオーバーライドする、、またはから派生した独自のクラスのインスタンスにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="419ce-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="419ce-177">サンプル コードなど詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="419ce-177">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [<span data-ttu-id="419ce-178">方法: Windows フォームで ToolStrip コントロールのカスタムレンダラーを作成して設定する</span><span class="sxs-lookup"><span data-stu-id="419ce-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [<span data-ttu-id="419ce-179">方法: ToolStrip コントロールのカスタム描画</span><span class="sxs-lookup"><span data-stu-id="419ce-179">How to: Custom Draw a ToolStrip Control</span></span>](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="419ce-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="419ce-180">See also</span></span>

- [<span data-ttu-id="419ce-181">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="419ce-181">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
