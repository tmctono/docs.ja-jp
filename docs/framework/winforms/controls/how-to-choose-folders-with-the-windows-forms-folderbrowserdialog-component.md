---
title: FolderBrowserDialog コンポーネントを使用したフォルダーの選択
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
ms.openlocfilehash: 313388442101f341cfed366143f3c9669fb45cbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742230"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="7d4f0-102">方法: Windows フォーム FolderBrowserDialog コンポーネントを使用してフォルダーを選択する</span><span class="sxs-lookup"><span data-stu-id="7d4f0-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="7d4f0-103">多くの場合、作成した Windows アプリケーション内で、フォルダーを選択するようにユーザーに促す必要があります。とりわけ、一連のファイルを保存するように求める場合が多いです。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="7d4f0-104">Windows フォーム <xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントを使用すると、このタスクを簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="7d4f0-105">FolderBrowserDialog コンポーネントを使用してフォルダーを選択するには</span><span class="sxs-lookup"><span data-stu-id="7d4f0-105">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="7d4f0-106">プロシージャで、<xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントの <xref:System.Windows.Forms.Form.DialogResult%2A> プロパティをチェックして、ダイアログボックスがどのように閉じられたかを確認し、<xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントの <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="7d4f0-107">ダイアログボックスのツリービュー内に表示される最上位のフォルダーを設定する必要がある場合は、<xref:System.Environment.SpecialFolder> 列挙体のメンバーを取得する <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="7d4f0-108">また、[<xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>] プロパティを設定することもできます。このプロパティは、フォルダーブラウザーのツリービューの上部に表示されるテキスト文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="7d4f0-109">次の例では、Visual Studio でプロジェクトを作成する場合と同様に、<xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントを使用してフォルダーを選択し、保存先のフォルダーを選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="7d4f0-110">この例では、フォルダー名がフォームの <xref:System.Windows.Forms.TextBox> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="7d4f0-111">エラーやその他の問題が発生した場合にユーザーが選択内容を編集できるように、<xref:System.Windows.Forms.TextBox> コントロールなどの編集可能な領域に場所を配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="7d4f0-112">この例では、フォームに <xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントと <xref:System.Windows.Forms.TextBox> コントロールがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

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
    > <span data-ttu-id="7d4f0-113">このクラスを使用するには、アセンブリに、<xref:System.Security.Permissions.FileIOPermissionAccess> 列挙体の一部である <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> プロパティによって付与される特権レベルが必要です。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="7d4f0-114">部分的に信頼されたコンテキストで実行している場合、プロセスは、特権がないため例外をスローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="7d4f0-115">詳しくは、「[コード アクセス セキュリティの基礎](../../misc/code-access-security-basics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="7d4f0-116">ファイルの保存方法については、「[方法: SaveFileDialog コンポーネントを使用してファイルを保存する](how-to-save-files-using-the-savefiledialog-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d4f0-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d4f0-117">参照</span><span class="sxs-lookup"><span data-stu-id="7d4f0-117">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="7d4f0-118">FolderBrowserDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="7d4f0-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="7d4f0-119">FolderBrowserDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7d4f0-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
