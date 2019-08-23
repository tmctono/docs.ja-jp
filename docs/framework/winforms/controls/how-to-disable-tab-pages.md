---
title: '方法: タブ ページを無効化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 888228c28dce591b237be16b6a321afee0105208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967150"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="3ecda-102">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="3ecda-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="3ecda-103">場合によっては、Windows フォームアプリケーション内で使用できるデータへのアクセスを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ecda-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="3ecda-104">この例の1つとして、タブコントロールのタブページにデータが表示されている場合があります。管理者は、ゲストまたは下位レベルのユーザーから制限するタブページに関する情報を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="3ecda-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="3ecda-105">プログラムによってタブページを無効にするには</span><span class="sxs-lookup"><span data-stu-id="3ecda-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="3ecda-106">タブコントロールの<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3ecda-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="3ecda-107">これは、ユーザーが1つのタブから次のタブに切り替えたときに発生するイベントです。</span><span class="sxs-lookup"><span data-stu-id="3ecda-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="3ecda-108">資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ecda-108">Check credentials.</span></span> <span data-ttu-id="3ecda-109">表示される情報に応じて、ユーザーがタブを表示できるようにする前に、ユーザーがログインしたユーザー名または他の形式の資格情報を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3ecda-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="3ecda-110">ユーザーが適切な資格情報を持っている場合は、クリックされたタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ecda-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="3ecda-111">ユーザーが適切な資格情報を持っていない場合は、メッセージボックスまたはその他のユーザーインターフェイスを表示して、アクセス権がないことを示し、最初のタブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="3ecda-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3ecda-112">実稼働アプリケーションにこの機能を実装する場合は、フォームの<xref:System.Windows.Forms.Form.Load>イベント中にこの資格情報の確認を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ecda-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="3ecda-113">これにより、ユーザーインターフェイスを表示する前にタブを非表示にすることができます。これは、プログラミングの方法としてははるかに簡潔です。</span><span class="sxs-lookup"><span data-stu-id="3ecda-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="3ecda-114">次に示す方法 (資格情報を確認し、 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged>イベント中にタブを無効にする) は、説明を目的としています。</span><span class="sxs-lookup"><span data-stu-id="3ecda-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="3ecda-115">2つ以上のタブページがある場合は、必要に応じて、元のタブページとは異なるタブページを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ecda-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="3ecda-116">次の例では、 <xref:System.Windows.Forms.CheckBox>資格情報を確認する代わりにコントロールを使用しています。タブへのアクセス条件はアプリケーションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3ecda-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="3ecda-117">イベントが発生すると、資格情報の確認が true (つまり、チェックボックスがオン) になっており、選択し`TabPage2`たタブが ( `TabPage2`この例では機密情報が含まれているタブ)、が表示されます。 <xref:System.Windows.Forms.TabControl.SelectedIndexChanged></span><span class="sxs-lookup"><span data-stu-id="3ecda-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="3ecda-118">それ以外`TabPage3`の場合は、が表示され、適切なアクセス特権がないことを示すメッセージボックスがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ecda-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="3ecda-119">次のコードは、 <xref:System.Windows.Forms.CheckBox>コントロール (`CredentialCheck`) <xref:System.Windows.Forms.TabControl>と、3つのタブページを持つコントロールを持つフォームを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3ecda-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="3ecda-120">(ビジュアルC#、ビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="3ecda-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3ecda-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ecda-121">See also</span></span>

- [<span data-ttu-id="3ecda-122">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="3ecda-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="3ecda-123">方法: タブページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="3ecda-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="3ecda-124">方法: Windows フォーム TabControl を使用してタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="3ecda-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="3ecda-125">方法: Windows フォーム TabControl の外観を変更する</span><span class="sxs-lookup"><span data-stu-id="3ecda-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
