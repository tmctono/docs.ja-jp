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
ms.openlocfilehash: b869898a20008343b6c6cbe4bc7e399fc86fb232
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054017"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="5b798-102">方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドする</span><span class="sxs-lookup"><span data-stu-id="5b798-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="5b798-103">バインドすることができます、<xref:System.Windows.Forms.ComboBox>と<xref:System.Windows.Forms.ListBox>データベース内のデータの参照などのタスクを実行するデータに新しいデータの入力または既存のデータを編集します。</span><span class="sxs-lookup"><span data-stu-id="5b798-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="5b798-104">ComboBox または ListBox コントロールにバインドするには</span><span class="sxs-lookup"><span data-stu-id="5b798-104">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="5b798-105">設定、`DataSource`プロパティをデータ ソース オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5b798-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="5b798-106">データ ソースには、<xref:System.Windows.Forms.BindingSource>データ、データ テーブル、データ ビュー、データセットにバインドするデータ マネージャー、配列、または表示を実装するクラス、<xref:System.Collections.IList>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5b798-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="5b798-107">詳細については、次を参照してください。 [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b798-107">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="5b798-108">テーブルにバインドする場合は、設定、`DisplayMember`プロパティをデータ ソース内の列の名前にします。</span><span class="sxs-lookup"><span data-stu-id="5b798-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="5b798-109">\- または -</span><span class="sxs-lookup"><span data-stu-id="5b798-109">\- or -</span></span>  
  
     <span data-ttu-id="5b798-110">バインドしている場合、 <xref:System.Collections.IList>、画面メンバー リスト内の型のパブリック プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5b798-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    >  <span data-ttu-id="5b798-111">実装されていないデータ ソースにバインドするかどうか、<xref:System.ComponentModel.IBindingList>インターフェイスなど、 <xref:System.Collections.ArrayList>、データ ソースが更新されたときに、バインドされたコントロールのデータは更新されません。</span><span class="sxs-lookup"><span data-stu-id="5b798-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="5b798-112">などがある場合、コンボ ボックスにバインドする<xref:System.Collections.ArrayList>にデータを追加し、 <xref:System.Collections.ArrayList>、コンボ ボックスではこれらの新しい項目は表示されません。</span><span class="sxs-lookup"><span data-stu-id="5b798-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="5b798-113">ただし、呼び出すことで更新するコンボ ボックスを強制することができます、<xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A>と<xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A>のインスタンスでメソッド、<xref:System.Windows.Forms.BindingContext>コントロールがバインドされるクラスします。</span><span class="sxs-lookup"><span data-stu-id="5b798-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b798-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b798-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="5b798-115">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="5b798-115">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="5b798-116">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="5b798-116">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="5b798-117">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="5b798-117">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
