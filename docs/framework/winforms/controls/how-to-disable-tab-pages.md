---
title: '方法 : タブ ページを無効化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182174"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="16a61-102">方法 : タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="16a61-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="16a61-103">Windows フォーム アプリケーション内で使用できるデータへのアクセスを制限する場合があります。</span><span class="sxs-lookup"><span data-stu-id="16a61-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="16a61-104">この例の 1 つとして、タブ コントロールのタブ ページにデータが表示されている場合があります。管理者は、ゲストレベルまたは下位レベルのユーザーから制限する必要がある情報をタブ ページに含める場合があります。</span><span class="sxs-lookup"><span data-stu-id="16a61-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="16a61-105">プログラムでタブ ページを無効にするには</span><span class="sxs-lookup"><span data-stu-id="16a61-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="16a61-106">タブ コントロールのイベントを処理するコード<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>を記述します。</span><span class="sxs-lookup"><span data-stu-id="16a61-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="16a61-107">これは、ユーザーがタブを切り替えたときに発生するイベントです。</span><span class="sxs-lookup"><span data-stu-id="16a61-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="16a61-108">資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="16a61-108">Check credentials.</span></span> <span data-ttu-id="16a61-109">表示される情報によっては、ユーザーがログインしたユーザー名や、ユーザーがタブを表示できるようにする前に、その他の形式の資格情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16a61-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="16a61-110">ユーザーが適切な資格情報を持っている場合は、クリックされたタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="16a61-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="16a61-111">ユーザーが適切な資格情報を持っていない場合は、アクセス権を持っていないというメッセージ ボックスまたはその他のユーザー インターフェイスを表示し、最初のタブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="16a61-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="16a61-112">この機能を実稼働アプリケーションに実装する場合、フォームの<xref:System.Windows.Forms.Form.Load>イベント中にこの資格情報チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="16a61-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="16a61-113">これにより、ユーザーインターフェイスが表示される前にタブを非表示にすることが可能になり、プログラミングに対するはるかにクリーンなアプローチです。</span><span class="sxs-lookup"><span data-stu-id="16a61-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="16a61-114">以下で使用する方法 (資格情報の確認、イベント中のタブの<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>無効化) は、説明の目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="16a61-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="16a61-115">必要に応じて、3 つ以上のタブ ページがある場合は、元のタブ ページとは異なるタブ ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="16a61-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="16a61-116">次の例では、タブ<xref:System.Windows.Forms.CheckBox>へのアクセス基準はアプリケーションによって異なるため、資格情報をチェックする代わりにコントロールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="16a61-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="16a61-117"><xref:System.Windows.Forms.TabControl.SelectedIndexChanged>イベントが発生した場合、資格情報チェックが true (つまり、チェック ボックスがチェックされている) で、選択された`TabPage2`タブ (この例では機密情報が含まれているタブ)`TabPage2`が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16a61-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="16a61-118">それ以外`TabPage3`の場合は、適切なアクセス権を持っていなかったことを示すメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16a61-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="16a61-119">次のコードでは、<xref:System.Windows.Forms.CheckBox>コントロール ( )`CredentialCheck`と<xref:System.Windows.Forms.TabControl>3 つのタブ ページを持つコントロールを持つフォームを想定しています。</span><span class="sxs-lookup"><span data-stu-id="16a61-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
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
  
     <span data-ttu-id="16a61-120">(ビジュアル C#、ビジュアル C++)フォームのコンストラクターに次のコードを配置して、イベント ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="16a61-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="16a61-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="16a61-121">See also</span></span>

- [<span data-ttu-id="16a61-122">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="16a61-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="16a61-123">方法 : タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="16a61-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="16a61-124">方法 : Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="16a61-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="16a61-125">方法 : Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="16a61-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
