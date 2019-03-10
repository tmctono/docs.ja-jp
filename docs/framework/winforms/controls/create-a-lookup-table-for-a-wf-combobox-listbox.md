---
title: '方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: eaa92c2b95d8dd8578b46e44a948127e201bb351
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724612"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="4953b-102">方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4953b-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="4953b-103">Windows フォーム上ではわかりやすい形式でデータを表示し、一方プログラムにはより意味のある形式でデータを格納すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4953b-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="4953b-104">たとえば、食品の注文書の場合、リスト ボックスにメニュー項目が名前で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4953b-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="4953b-105">一方、注文を記録するデータ テーブルには、食品を表す一意の ID 番号が含まれることになります。</span><span class="sxs-lookup"><span data-stu-id="4953b-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="4953b-106">次の表は、食品の注文書データを格納および表示する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="4953b-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="4953b-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="4953b-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="4953b-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="4953b-108">OrderID</span></span>|<span data-ttu-id="4953b-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="4953b-109">ItemID</span></span>|<span data-ttu-id="4953b-110">数量</span><span class="sxs-lookup"><span data-stu-id="4953b-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="4953b-111">4085</span><span class="sxs-lookup"><span data-stu-id="4953b-111">4085</span></span>|<span data-ttu-id="4953b-112">12</span><span class="sxs-lookup"><span data-stu-id="4953b-112">12</span></span>|<span data-ttu-id="4953b-113">1</span><span class="sxs-lookup"><span data-stu-id="4953b-113">1</span></span>|  
|<span data-ttu-id="4953b-114">4086</span><span class="sxs-lookup"><span data-stu-id="4953b-114">4086</span></span>|<span data-ttu-id="4953b-115">13</span><span class="sxs-lookup"><span data-stu-id="4953b-115">13</span></span>|<span data-ttu-id="4953b-116">3</span><span class="sxs-lookup"><span data-stu-id="4953b-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="4953b-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="4953b-117">ItemTable</span></span>  
  
|<span data-ttu-id="4953b-118">ID</span><span class="sxs-lookup"><span data-stu-id="4953b-118">ID</span></span>|<span data-ttu-id="4953b-119">名前</span><span class="sxs-lookup"><span data-stu-id="4953b-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="4953b-120">12</span><span class="sxs-lookup"><span data-stu-id="4953b-120">12</span></span>|<span data-ttu-id="4953b-121">ポテト</span><span class="sxs-lookup"><span data-stu-id="4953b-121">Potato</span></span>|  
|<span data-ttu-id="4953b-122">13</span><span class="sxs-lookup"><span data-stu-id="4953b-122">13</span></span>|<span data-ttu-id="4953b-123">チキン</span><span class="sxs-lookup"><span data-stu-id="4953b-123">Chicken</span></span>|  
  
 <span data-ttu-id="4953b-124">このシナリオでは、1 つのテーブルで**OrderDetailsTable**、表示と保存には、実際の情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="4953b-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="4953b-125">しかし、スペースを節約するために、これはかなり謎めいた方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="4953b-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="4953b-126">その他のテーブル**ItemTable**、どの id 番号がどの食品名には実際の食品の注文について何も同等外観に関連する情報のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4953b-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="4953b-127">**ItemTable**に接続されている、 <xref:System.Windows.Forms.ComboBox>、 <xref:System.Windows.Forms.ListBox>、または<xref:System.Windows.Forms.CheckedListBox>3 つのプロパティを制御します。</span><span class="sxs-lookup"><span data-stu-id="4953b-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="4953b-128">`DataSource`プロパティには、このテーブルの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4953b-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="4953b-129">`DisplayMember`プロパティには、コントロール (食品名) に表示する、テーブルのデータ列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4953b-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="4953b-130">`ValueMember`プロパティに格納されている情報 (ID 番号) を持つ、テーブルのデータ列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4953b-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="4953b-131">**OrderDetailsTable**経由でアクセス、そのバインディング コレクションにより、コントロールに接続されている、<xref:System.Windows.Forms.Control.DataBindings%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4953b-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="4953b-132">コントロールのプロパティは、データ ソース内の特定のデータ メンバー (ID 番号の列) に接続するバインディング オブジェクトをコレクションに追加すると (、 **OrderDetailsTable**)。</span><span class="sxs-lookup"><span data-stu-id="4953b-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="4953b-133">コントロールで選択がなされる際、このテーブルはフォーム入力が保存される場所です。</span><span class="sxs-lookup"><span data-stu-id="4953b-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="4953b-134">ルックアップ テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="4953b-134">To create a lookup table</span></span>  
  
1.  <span data-ttu-id="4953b-135">フォームに <xref:System.Windows.Forms.ComboBox>、<xref:System.Windows.Forms.ListBox>、または <xref:System.Windows.Forms.CheckedListBox> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="4953b-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2.  <span data-ttu-id="4953b-136">データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="4953b-136">Connect to your data source.</span></span>  
  
3.  <span data-ttu-id="4953b-137">2 つのテーブル間のデータ リレーションシップを確立します。</span><span class="sxs-lookup"><span data-stu-id="4953b-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="4953b-138">参照してください[DataRelation オブジェクトの概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="4953b-138">See [Introduction to DataRelation Objects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4.  <span data-ttu-id="4953b-139">次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4953b-139">Set the following properties.</span></span> <span data-ttu-id="4953b-140">これらはコードまたはデザイナーで設定できます。</span><span class="sxs-lookup"><span data-stu-id="4953b-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="4953b-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4953b-141">Property</span></span>|<span data-ttu-id="4953b-142">設定</span><span class="sxs-lookup"><span data-stu-id="4953b-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="4953b-143">どの ID 番号がどの項目に相当するかについての情報を含むテーブル。</span><span class="sxs-lookup"><span data-stu-id="4953b-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="4953b-144">これは、前のシナリオで`ItemTable`します。</span><span class="sxs-lookup"><span data-stu-id="4953b-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="4953b-145">コントロールに表示するデータ ソース テーブルの列。</span><span class="sxs-lookup"><span data-stu-id="4953b-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="4953b-146">これは、前のシナリオで`"Name"`(コードで設定するには引用符を使用)。</span><span class="sxs-lookup"><span data-stu-id="4953b-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="4953b-147">格納された情報を含むデータ ソース テーブルの列。</span><span class="sxs-lookup"><span data-stu-id="4953b-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="4953b-148">これは、前のシナリオで`"ID"`(コードで設定するには引用符を使用)。</span><span class="sxs-lookup"><span data-stu-id="4953b-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5.  <span data-ttu-id="4953b-149">プロシージャで <xref:System.Windows.Forms.ControlBindingsCollection> クラスの <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> メソッドを呼び出して、フォーム入力を記録するテーブルにコントロールの <xref:System.Windows.Forms.ListControl.SelectedValue%2A> プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4953b-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="4953b-150">行うこともできますこのコードでは、代わりに、デザイナーでコントロールのアクセスすることによって<xref:System.Windows.Forms.Control.DataBindings%2A>プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="4953b-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="4953b-151">これは、前のシナリオで`OrderDetailsTable`、列と`"ItemID"`します。</span><span class="sxs-lookup"><span data-stu-id="4953b-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4953b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="4953b-152">See also</span></span>
- [<span data-ttu-id="4953b-153">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="4953b-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="4953b-154">ListBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4953b-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4953b-155">ComboBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4953b-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="4953b-156">CheckedListBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4953b-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4953b-157">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="4953b-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
