---
title: '方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内にエラーを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: 3dbd2ccca607869a6f28bc5b3bd1c9f0769db9f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950082"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="f2e83-102">方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内にエラーを表示する</span><span class="sxs-lookup"><span data-stu-id="f2e83-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="f2e83-103">Windows フォーム<xref:System.Windows.Forms.ErrorProvider>コンポーネントを使用すると、データセットまたはその他のデータソース内の列のエラーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f2e83-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="f2e83-104"><xref:System.Windows.Forms.ErrorProvider>コンポーネントがフォームにデータエラーを表示するには、コントロールに直接関連付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f2e83-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="f2e83-105">データソースにバインドされると、同じデータソースにバインドされているコントロールの横にエラーアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2e83-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2e83-106">実行時にエラープロバイダーの<xref:System.Windows.Forms.ErrorProvider.DataSource%2A>プロパティと<xref:System.Windows.Forms.ErrorProvider.DataMember%2A>プロパティを変更した場合は、 <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>メソッドを使用して競合を回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2e83-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="f2e83-107">データエラーを表示するには</span><span class="sxs-lookup"><span data-stu-id="f2e83-107">To display data errors</span></span>  
  
1. <span data-ttu-id="f2e83-108">コンポーネントをデータテーブル内の特定の列にバインドします。</span><span class="sxs-lookup"><span data-stu-id="f2e83-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2. <span data-ttu-id="f2e83-109"><xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>プロパティをフォームに設定します。</span><span class="sxs-lookup"><span data-stu-id="f2e83-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3. <span data-ttu-id="f2e83-110">現在のレコードの位置を、列エラーを含む行に設定します。</span><span class="sxs-lookup"><span data-stu-id="f2e83-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f2e83-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2e83-111">See also</span></span>

- [<span data-ttu-id="f2e83-112">ErrorProvider コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="f2e83-112">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="f2e83-113">方法: Windows フォーム ErrorProvider コンポーネントを使用したフォーム検証のエラーアイコンの表示</span><span class="sxs-lookup"><span data-stu-id="f2e83-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](display-error-icons-for-form-validation-with-wf-errorprovider.md)
