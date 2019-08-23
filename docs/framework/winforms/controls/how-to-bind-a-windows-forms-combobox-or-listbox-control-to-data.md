---
title: '方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922754"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="e0266-102">方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドする</span><span class="sxs-lookup"><span data-stu-id="e0266-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="e0266-103"><xref:System.Windows.Forms.ComboBox> と<xref:System.Windows.Forms.ListBox>をデータにバインドすると、データベース内のデータの参照、新しいデータの入力、既存のデータの編集などのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e0266-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="e0266-104">ComboBox または ListBox コントロールをバインドするには</span><span class="sxs-lookup"><span data-stu-id="e0266-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="e0266-105">`DataSource`プロパティをデータソースオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="e0266-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="e0266-106">使用できるデータソースに<xref:System.Windows.Forms.BindingSource>は、データへのバインド、データテーブル、データビュー、データセット、データビューマネージャー、配列、または<xref:System.Collections.IList>インターフェイスを実装する任意のクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0266-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="e0266-107">詳細については、「 [Windows フォームでサポートされるデータソース](../data-sources-supported-by-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0266-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="e0266-108">テーブルにバインドする場合は、 `DisplayMember`プロパティをデータソース内の列の名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0266-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="e0266-109">\- または -</span><span class="sxs-lookup"><span data-stu-id="e0266-109">\- or -</span></span>  
  
     <span data-ttu-id="e0266-110">にバインドする場合は<xref:System.Collections.IList>、表示メンバーをリスト内の型のパブリックプロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="e0266-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="e0266-111">など、 <xref:System.ComponentModel.IBindingList>インターフェイス<xref:System.Collections.ArrayList>を実装していないデータソースにバインドされている場合、データソースの更新時にバインドされたコントロールのデータは更新されません。</span><span class="sxs-lookup"><span data-stu-id="e0266-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="e0266-112">たとえば、に<xref:System.Collections.ArrayList>バインドされたコンボボックスがあり、 <xref:System.Collections.ArrayList>にデータが追加されている場合、これらの新しい項目はコンボボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e0266-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="e0266-113">ただし、コントロールがバインドされている<xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> <xref:System.Windows.Forms.BindingContext>クラスのインスタンスでメソッドと<xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A>メソッドを呼び出すことにより、コンボボックスを強制的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="e0266-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0266-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0266-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="e0266-115">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="e0266-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="e0266-116">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="e0266-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="e0266-117">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="e0266-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
