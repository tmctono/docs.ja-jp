---
title: ComboBox または ListBox コントロールをデータにバインドする
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
ms.openlocfilehash: 99d9b53b32d6faae888b134d4ed486980c05a75b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742033"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="69a48-102">方法 : Windows フォームの ComboBox または ListBox コントロールをデータにバインドする</span><span class="sxs-lookup"><span data-stu-id="69a48-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="69a48-103"><xref:System.Windows.Forms.ComboBox> と <xref:System.Windows.Forms.ListBox> をデータにバインドして、データベース内のデータの参照、新しいデータの入力、既存のデータの編集などのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="69a48-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="69a48-104">ComboBox または ListBox コントロールをバインドするには</span><span class="sxs-lookup"><span data-stu-id="69a48-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="69a48-105">`DataSource` プロパティをデータソースオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="69a48-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="69a48-106">データソースとしては、データ、データテーブル、データビュー、データセット、データビューマネージャー、配列、または <xref:System.Collections.IList> インターフェイスを実装する任意のクラスにバインドされた <xref:System.Windows.Forms.BindingSource> があります。</span><span class="sxs-lookup"><span data-stu-id="69a48-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="69a48-107">詳細については、「 [Windows フォームでサポートされるデータソース](../data-sources-supported-by-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a48-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="69a48-108">テーブルにバインドする場合は、`DisplayMember` プロパティをデータソース内の列の名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="69a48-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="69a48-109">\- または</span><span class="sxs-lookup"><span data-stu-id="69a48-109">\- or -</span></span>  
  
     <span data-ttu-id="69a48-110"><xref:System.Collections.IList>にバインドする場合は、表示メンバーをリスト内の型のパブリックプロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="69a48-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="69a48-111"><xref:System.Collections.ArrayList>などの <xref:System.ComponentModel.IBindingList> インターフェイスを実装していないデータソースにバインドされている場合、データソースの更新時にバインドされたコントロールのデータは更新されません。</span><span class="sxs-lookup"><span data-stu-id="69a48-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="69a48-112">たとえば、<xref:System.Collections.ArrayList> にバインドされたコンボボックスがあり、データが <xref:System.Collections.ArrayList>に追加されている場合、これらの新しい項目はコンボボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="69a48-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="69a48-113">ただし、コントロールがバインドされている <xref:System.Windows.Forms.BindingContext> クラスのインスタンスで <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> および <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> メソッドを呼び出すことによって、コンボボックスを強制的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="69a48-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a48-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="69a48-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="69a48-115">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="69a48-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="69a48-116">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="69a48-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="69a48-117">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="69a48-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
