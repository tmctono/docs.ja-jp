---
title: RichTextBox コントロールを使用してファイルを保存する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744822"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a7dd8-102">方法 : Windows フォームの RichTextBox コントロールを使用してファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="a7dd8-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="a7dd8-103">Windows フォーム <xref:System.Windows.Forms.RichTextBox> コントロールは、次のいずれかの形式で表示される情報を書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>

- <span data-ttu-id="a7dd8-104">プレーンテキスト</span><span class="sxs-lookup"><span data-stu-id="a7dd8-104">Plain text</span></span>

- <span data-ttu-id="a7dd8-105">Unicode プレーンテキスト</span><span class="sxs-lookup"><span data-stu-id="a7dd8-105">Unicode plain text</span></span>

- <span data-ttu-id="a7dd8-106">リッチテキスト形式 (RTF)</span><span class="sxs-lookup"><span data-stu-id="a7dd8-106">Rich-Text Format (RTF)</span></span>

- <span data-ttu-id="a7dd8-107">OLE オブジェクトの代わりにスペースを含む RTF</span><span class="sxs-lookup"><span data-stu-id="a7dd8-107">RTF with spaces in place of OLE objects</span></span>

- <span data-ttu-id="a7dd8-108">OLE オブジェクトのテキスト表現を含むプレーンテキスト</span><span class="sxs-lookup"><span data-stu-id="a7dd8-108">Plain text with a textual representation of OLE objects</span></span>

<span data-ttu-id="a7dd8-109">ファイルを保存するには、<xref:System.Windows.Forms.RichTextBox.SaveFile%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="a7dd8-110">**SaveFile**メソッドを使用して、データをストリームに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="a7dd8-111">詳細については、「 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="a7dd8-112">コントロールの内容をファイルに保存するには</span><span class="sxs-lookup"><span data-stu-id="a7dd8-112">To save the contents of the control to a file</span></span>

1. <span data-ttu-id="a7dd8-113">保存するファイルのパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-113">Determine the path of the file to be saved.</span></span>

    <span data-ttu-id="a7dd8-114">実際のアプリケーションでこれを行うには、通常、<xref:System.Windows.Forms.SaveFileDialog> コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="a7dd8-115">概要については、「 [Savefiledialog コンポーネントの概要](savefiledialog-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="a7dd8-116"><xref:System.Windows.Forms.RichTextBox> コントロールの <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> メソッドを呼び出して、保存するファイルと、必要に応じてファイルの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="a7dd8-117">ファイル名を唯一の引数としてメソッドを呼び出すと、ファイルは RTF として保存されます。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="a7dd8-118">別の種類のファイルを指定するには、2 番目の引数として <xref:System.Windows.Forms.RichTextBoxStreamType> 列挙型の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="a7dd8-119">次の例では、リッチテキストファイルの場所に設定されているパスが **[マイドキュメント**] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="a7dd8-120">この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a7dd8-121">また、この場所を選択すると、最小限のシステムアクセスレベルのユーザーがアプリケーションを安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a7dd8-122">次の例では、フォームに <xref:System.Windows.Forms.RichTextBox> コントロールが既に追加されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="a7dd8-123">次のコード例では、ファイルが存在しない場合は新規にファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="a7dd8-124">アプリケーションでファイルを作成する必要がある場合、そのアプリケーションにはフォルダーの作成アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="a7dd8-125">アクセス許可は、アクセス制御リストを使って設定します。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="a7dd8-126">ファイルが既に存在する場合、アプリケーションに必要なのは、より低い特権である書き込みアクセスだけです。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="a7dd8-127">可能な場合は、配置時にファイルを作成し、フォルダーのアクセスを作成するのではなく、1つのファイルに対する読み取りアクセスのみを許可する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="a7dd8-128">また、ルート フォルダーや Program Files フォルダーにデータを書き込むよりも、ユーザー フォルダーに書き込む方が安全です。</span><span class="sxs-lookup"><span data-stu-id="a7dd8-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7dd8-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7dd8-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="a7dd8-130">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="a7dd8-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="a7dd8-131">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="a7dd8-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
