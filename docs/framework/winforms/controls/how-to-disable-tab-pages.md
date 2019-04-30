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
ms.openlocfilehash: 21592fdd74c43d40310e0fcbc96af6565a42e08b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013453"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="71b56-102">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="71b56-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="71b56-103">状況によっては、Windows フォーム アプリケーション内で使用できるデータ アクセスを制限するされます。</span><span class="sxs-lookup"><span data-stu-id="71b56-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="71b56-104">タブ コントロールのタブ ページに表示されるデータがある場合をこの 1 つの例として使用することがあります。管理者には、ゲストまたは低いレベルのユーザーを制限するタブ ページの情報があります。</span><span class="sxs-lookup"><span data-stu-id="71b56-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="71b56-105">タブ ページをプログラムで無効にするには</span><span class="sxs-lookup"><span data-stu-id="71b56-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="71b56-106">タブ コントロールを処理するコード<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>イベント。</span><span class="sxs-lookup"><span data-stu-id="71b56-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="71b56-107">これは、ユーザーが 1 つのタブ、[次へ] を切り替えるときに発生するイベントです。</span><span class="sxs-lookup"><span data-stu-id="71b56-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="71b56-108">資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="71b56-108">Check credentials.</span></span> <span data-ttu-id="71b56-109">によって表示される情報は、タブを表示するユーザーを許可する前に、ユーザーがログインに使用するユーザー名またはその他の何らかの形式の資格情報を確認することがあります。</span><span class="sxs-lookup"><span data-stu-id="71b56-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="71b56-110">ユーザーに適切な資格情報がある場合は、クリックされたタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="71b56-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="71b56-111">ユーザーは、適切な資格情報を持っていない場合メッセージ ボックスを表示またはのユーザー インターフェイスであることを示すがありません、アクセスして、最初のタブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="71b56-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71b56-112">フォームの中にこの資格情報のチェックを実行するには、実稼働アプリケーションでこの機能を実装するときに<xref:System.Windows.Forms.Form.Load>イベント。</span><span class="sxs-lookup"><span data-stu-id="71b56-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="71b56-113">これによって、プログラミングよりはるかにより明確な方法は、すべてのユーザー インターフェイスが表示される前に、タブを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="71b56-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="71b56-114">以下で使用する方法 (資格情報を確認し、中に、タブを無効にすると、<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>イベント) は、例示を目的として。</span><span class="sxs-lookup"><span data-stu-id="71b56-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="71b56-115">必要に応じて、3 つ以上のタブ ページがある場合は、元の別のタブ ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="71b56-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="71b56-116">次の例で、<xref:System.Windows.Forms.CheckBox>コントロールはアプリケーションによって異なりますが、タブへのアクセスの条件として、資格情報を確認する代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="71b56-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="71b56-117">ときに、<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>資格情報のチェックが true の場合、イベントが発生します (つまり、チェック ボックスをオン)、[選択] タブで、 `TabPage2` (この例では、機密情報をタブ)、し`TabPage2`が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71b56-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="71b56-118">それ以外の場合、`TabPage3`表示をユーザーに適切なアクセス特権がないことを示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71b56-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="71b56-119">次のコードでフォームを前提としています、<xref:System.Windows.Forms.CheckBox>コントロール (`CredentialCheck`) と<xref:System.Windows.Forms.TabControl>3 つのタブ ページを持つコントロール。</span><span class="sxs-lookup"><span data-stu-id="71b56-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="71b56-120">(Visual C#、Visual C)イベント ハンドラーを登録するフォームのコンス トラクターでは、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="71b56-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="71b56-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="71b56-121">See also</span></span>

- [<span data-ttu-id="71b56-122">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="71b56-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="71b56-123">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="71b56-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="71b56-124">方法: Windows フォーム tabcontrol のタブ追加および削除</span><span class="sxs-lookup"><span data-stu-id="71b56-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="71b56-125">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="71b56-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
