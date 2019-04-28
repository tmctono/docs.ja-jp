---
title: '方法: Windows フォーム FolderBrowserDialog コンポーネントを使用してフォルダーを選択する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 050af6d10faec3dd09998349dcf96e96ea0f9201
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746926"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="ced57-102">方法: Windows フォーム FolderBrowserDialog コンポーネントを使用してフォルダーを選択する</span><span class="sxs-lookup"><span data-stu-id="ced57-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>
<span data-ttu-id="ced57-103">多くの場合、作成した Windows アプリケーション内で、フォルダーを選択するようにユーザーに促す必要があります。とりわけ、一連のファイルを保存するように求める場合が多いです。</span><span class="sxs-lookup"><span data-stu-id="ced57-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="ced57-104">Windows フォーム<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネントでは、このタスクを簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="ced57-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="ced57-105">FolderBrowserDialog コンポーネントを使用してフォルダーを選択するには</span><span class="sxs-lookup"><span data-stu-id="ced57-105">To choose folders with the FolderBrowserDialog component</span></span>  
  
1. <span data-ttu-id="ced57-106">プロシージャでは、確認、<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネントの<xref:System.Windows.Forms.Form.DialogResult%2A> ダイアログ ボックスが閉じられた方法を表示しの値を取得するプロパティ、<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネントの<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ced57-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>  
  
2. <span data-ttu-id="ced57-107">ダイアログ ボックスのツリー ビュー内に表示されるフォルダーを最上位を設定する必要がある場合は、設定、<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>のメンバーを受け取りますプロパティ、<xref:System.Environment.SpecialFolder>列挙体。</span><span class="sxs-lookup"><span data-stu-id="ced57-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>  
  
3. <span data-ttu-id="ced57-108">さらに、設定、<xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>フォルダー ブラウザーのツリー ビューの上部にある文字列をテキストを指定するには、プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ced57-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>  
  
     <span data-ttu-id="ced57-109">次の例で、<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネントを使用して Visual Studio でプロジェクトを作成し、保存するフォルダーを選択するように求められますのようなフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ced57-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="ced57-110">この例で、フォルダー名に表示されますが、<xref:System.Windows.Forms.TextBox>フォーム上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="ced57-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="ced57-111">編集可能な領域になど場所を配置することをお勧め、<xref:System.Windows.Forms.TextBox>制御、ユーザーがエラーまたはその他の問題が発生した場合、選択項目を編集可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ced57-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="ced57-112">この例では使用して、フォーム、<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネントと<xref:System.Windows.Forms.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="ced57-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ced57-113">このクラスを使用するアセンブリに必要です特権レベルを付与して、<xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>一部であるプロパティの<xref:System.Security.Permissions.FileIOPermissionAccess>列挙体。</span><span class="sxs-lookup"><span data-stu-id="ced57-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="ced57-114">部分的に信頼されたコンテキストで実行している場合、プロセスは、特権がないため例外をスローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ced57-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="ced57-115">詳しくは、「[コード アクセス セキュリティの基礎](../../misc/code-access-security-basics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ced57-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="ced57-116">ファイルを保存する方法については、次を参照してください。[方法。SaveFileDialog コンポーネントを使用してファイルを保存](how-to-save-files-using-the-savefiledialog-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="ced57-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced57-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ced57-117">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="ced57-118">FolderBrowserDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ced57-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="ced57-119">FolderBrowserDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ced57-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
