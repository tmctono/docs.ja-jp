---
title: '方法: Windows フォーム ErrorProvider コンポーネントを使用してフォーム妥当性検査でエラー アイコンを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: 9487d4f82878ffefe17c576b16f654293ef01106
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316506"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="e171c-102">方法: Windows フォーム ErrorProvider コンポーネントを使用してフォーム妥当性検査でエラー アイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="e171c-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="e171c-103">Windows フォームを使用する<xref:System.Windows.Forms.ErrorProvider>無効なデータが入力されたときにエラー アイコンを表示するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="e171c-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="e171c-104">それらの間のタブし、検証コードを呼び出すためにフォーム上の少なくとも 2 つのコントロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="e171c-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="e171c-105">コントロールの値が有効でないときに、エラー アイコンを表示するには</span><span class="sxs-lookup"><span data-stu-id="e171c-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="e171c-106">2 つのコントロールを追加-たとえば、テキスト ボックス: Windows フォームに。</span><span class="sxs-lookup"><span data-stu-id="e171c-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="e171c-107">追加、<xref:System.Windows.Forms.ErrorProvider>コンポーネントをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="e171c-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="e171c-108">最初のコントロールを選択し、コードを追加してその<xref:System.Windows.Forms.Control.Validating>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="e171c-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="e171c-109">このコードを正常に実行するためには、プロシージャは、イベントに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e171c-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="e171c-110">詳細については、「[方法 :Windows フォームの実行時にイベント ハンドラーを作成](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)です。</span><span class="sxs-lookup"><span data-stu-id="e171c-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="e171c-111">次のコードは、ユーザーが入力したデータの有効性をテストします。データが有効でない場合、<xref:System.Windows.Forms.ErrorProvider.SetError%2A>メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e171c-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="e171c-112">最初の引数、<xref:System.Windows.Forms.ErrorProvider.SetError%2A>メソッドでは、横にアイコンを表示するコントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="e171c-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="e171c-113">2 番目の引数は、表示するエラー テキストです。</span><span class="sxs-lookup"><span data-stu-id="e171c-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="e171c-114">(Visual c#、 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターで、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="e171c-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="e171c-115">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e171c-115">Run the project.</span></span> <span data-ttu-id="e171c-116">最初のコントロールとし、2 番目のタブには、(この例では、数値以外) では無効なデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="e171c-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="e171c-117">エラー アイコンが表示されたら、エラー テキストを表示するマウス ポインターでポイントします。</span><span class="sxs-lookup"><span data-stu-id="e171c-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e171c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e171c-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="e171c-119">ErrorProvider コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="e171c-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="e171c-120">方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内のエラーの表示</span><span class="sxs-lookup"><span data-stu-id="e171c-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
