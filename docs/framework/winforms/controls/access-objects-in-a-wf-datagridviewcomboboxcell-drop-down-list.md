---
title: DataGridViewComboBoxCell ドロップダウンリストのオブジェクトにアクセスする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746315"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="4a7d6-102">方法 : Windows フォームの DataGridViewComboBoxCell ドロップダウン リストのオブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="4a7d6-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="4a7d6-103"><xref:System.Windows.Forms.ComboBox> コントロールと同様に、<xref:System.Windows.Forms.DataGridViewComboBoxColumn> と <xref:System.Windows.Forms.DataGridViewComboBoxCell> の種類を使用すると、任意のオブジェクトをドロップダウンリストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="4a7d6-104">この機能を使用すると、対応するオブジェクトを別のコレクションに格納しなくても、ドロップダウンリストで複雑な状態を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="4a7d6-105"><xref:System.Windows.Forms.ComboBox> コントロールとは異なり、<xref:System.Windows.Forms.DataGridView> 型には、現在選択されているオブジェクトを取得するための <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> プロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="4a7d6-106">代わりに、<xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> または <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> プロパティをビジネスオブジェクトのプロパティの名前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="4a7d6-107">ユーザーが選択を行うと、ビジネスオブジェクトの指定されたプロパティによって、セル <xref:System.Windows.Forms.DataGridViewCell.Value%2A> プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="4a7d6-108">セル値を使用してビジネスオブジェクトを取得するには、`ValueMember` プロパティに、ビジネスオブジェクト自体への参照を返すプロパティが指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="4a7d6-109">したがって、ビジネスオブジェクトの型がコントロールの下にない場合は、継承によって型を拡張することによって、このようなプロパティを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="4a7d6-110">次の手順では、ビジネスオブジェクトを使用してドロップダウンリストを設定し、セル <xref:System.Windows.Forms.DataGridViewCell.Value%2A> プロパティを使用してオブジェクトを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="4a7d6-111">ドロップダウンリストにビジネスオブジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="4a7d6-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="4a7d6-112">新しい <xref:System.Windows.Forms.DataGridViewComboBoxColumn> を作成し、その <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> コレクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="4a7d6-113">または、[列 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>] プロパティをビジネスオブジェクトのコレクションに設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="4a7d6-114">ただし、コレクション内に対応するビジネスオブジェクトを作成しなくても、ドロップダウンリストに "未割り当て" を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="4a7d6-115"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> プロパティと <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="4a7d6-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> は、ドロップダウンリストに表示するビジネスオブジェクトのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="4a7d6-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> は、ビジネスオブジェクトへの参照を返すプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="4a7d6-118">ビジネスオブジェクト型に、現在のインスタンスへの参照を返すプロパティが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="4a7d6-119">このプロパティには、前の手順で <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> に割り当てられた値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="4a7d6-120">現在選択されているビジネスオブジェクトを取得するには</span><span class="sxs-lookup"><span data-stu-id="4a7d6-120">To retrieve the currently selected business object</span></span>  
  
- <span data-ttu-id="4a7d6-121">セル <xref:System.Windows.Forms.DataGridViewCell.Value%2A> プロパティを取得し、ビジネスオブジェクト型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="4a7d6-122">使用例</span><span class="sxs-lookup"><span data-stu-id="4a7d6-122">Example</span></span>  
 <span data-ttu-id="4a7d6-123">完全な例では、ドロップダウンリストでビジネスオブジェクトを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="4a7d6-124">この例では、<xref:System.Windows.Forms.DataGridView> コントロールが `Task` オブジェクトのコレクションにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="4a7d6-125">各 `Task` オブジェクトには、そのタスクに現在割り当てられている `Employee` オブジェクトを示す `AssignedTo` プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="4a7d6-126">`Assigned To` 列には、割り当てられた各従業員の `Name` プロパティ値が表示されます。また、`Task.AssignedTo` プロパティ値が `null`場合は、"未割り当て" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="4a7d6-127">この例の動作を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="4a7d6-128">ドロップダウンリストから別の値を選択するか、コンボボックスのセルで CTRL + 0 キーを押して、[`Assigned To`] 列の割り当てを変更します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="4a7d6-129">現在の割り当てを表示するには、[`Generate Report`] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="4a7d6-130">これは、`Assigned To` 列の変更によって `tasks` コレクションが自動的に更新されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="4a7d6-131">`Request Status` ボタンをクリックして、その行の現在の `Employee` オブジェクトの `RequestStatus` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="4a7d6-132">これは、選択したオブジェクトが正常に取得されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4a7d6-133">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="4a7d6-133">Compiling the Code</span></span>  
 <span data-ttu-id="4a7d6-134">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-134">This example requires:</span></span>  
  
- <span data-ttu-id="4a7d6-135">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="4a7d6-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a7d6-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a7d6-136">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [<span data-ttu-id="4a7d6-137">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="4a7d6-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
