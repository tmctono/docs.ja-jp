---
title: '方法: SaveFileDialog コンポーネントを使用してファイルを保存する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: 7a3a7d0b12a83b756eb2790a94a95580576a2c32
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046275"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="19675-102">方法: SaveFileDialog コンポーネントを使用してファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="19675-102">How to: Save Files Using the SaveFileDialog Component</span></span>

<span data-ttu-id="19675-103">この<xref:System.Windows.Forms.SaveFileDialog>コンポーネントを使用すると、ユーザーはファイルシステムを参照して、保存するファイルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="19675-103">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="19675-104">このダイアログ ボックスは、ユーザーがダイアログ ボックス内で選択したファイルのパスと名前を返します。</span><span class="sxs-lookup"><span data-stu-id="19675-104">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="19675-105">ただし、ファイルを実際にディスクに書き込むためのコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19675-105">However, you must write the code to actually write the files to disk.</span></span>

### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="19675-106">SaveFileDialog コンポーネントを使用してファイルを保存するには</span><span class="sxs-lookup"><span data-stu-id="19675-106">To save a file using the SaveFileDialog component</span></span>

- <span data-ttu-id="19675-107">**[ファイルの保存]** ダイアログ ボックスを表示し、ユーザーによって選択されたファイルを保存するメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="19675-107">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>

  <span data-ttu-id="19675-108"><xref:System.Windows.Forms.SaveFileDialog>コンポーネントの<xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>メソッドを使用して、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="19675-108">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="19675-109">このメソッドは、書き込み<xref:System.IO.Stream>可能なオブジェクトを提供します。</span><span class="sxs-lookup"><span data-stu-id="19675-109">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>

  <span data-ttu-id="19675-110">次の例では<xref:System.Windows.Forms.DialogResult> 、プロパティを使用してファイルの名前を取得<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>し、メソッドを使用してファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="19675-110">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="19675-111">メソッド<xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>は、ファイルを書き込むストリームを提供します。</span><span class="sxs-lookup"><span data-stu-id="19675-111">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>

  <span data-ttu-id="19675-112">次の例では、イメージが<xref:System.Windows.Forms.Button>割り当てられたコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="19675-112">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="19675-113">このボタンをクリックすると、 <xref:System.Windows.Forms.SaveFileDialog>コンポーネントが、.gif、.jpeg、.bmp の種類のファイルを許可するフィルターでインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="19675-113">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="19675-114">[ファイルの保存] ダイアログ ボックスでこれらの種類のファイルが選択されると、ボタンのイメージが保存されます。</span><span class="sxs-lookup"><span data-stu-id="19675-114">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="19675-115"><xref:System.Windows.Forms.FileDialog.FileName%2A>プロパティを取得または設定するには、アセンブリに、 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>クラスによって付与された特権レベルが必要です。</span><span class="sxs-lookup"><span data-stu-id="19675-115">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="19675-116">部分的に信頼されたコンテキストで実行している場合、プロセスは、特権がないために例外をスローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19675-116">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="19675-117">詳しくは、「[コード アクセス セキュリティの基礎](../../misc/code-access-security-basics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19675-117">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

  <span data-ttu-id="19675-118">この例では、フォームに<xref:System.Windows.Forms.Button> 、 <xref:System.Windows.Forms.ButtonBase.Image%2A>プロパティが .gif、.jpeg、または .bmp のファイルに設定されたコントロールがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="19675-118">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>

  > [!NOTE]
  > <span data-ttu-id="19675-119">クラスのプロパティ (継承により、 <xref:System.Windows.Forms.SaveFileDialog>クラスに含まれる) は、1から始まるインデックスを使用します。 <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> <xref:System.Windows.Forms.FileDialog></span><span class="sxs-lookup"><span data-stu-id="19675-119">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="19675-120">これは、ファイルをバイナリ形式ではなくプレーン テキストで保存する場合など、データを特定の形式で保存するコードを記述する場合に重要です。</span><span class="sxs-lookup"><span data-stu-id="19675-120">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="19675-121">このプロパティは、次のコード例に示されています。</span><span class="sxs-lookup"><span data-stu-id="19675-121">This property is featured in the example below.</span></span>

  ```vb
  Private Sub Button2_Click(ByVal sender As System.Object, _
  ByVal e As System.EventArgs) Handles Button2.Click
      ' Displays a SaveFileDialog so the user can save the Image
      ' assigned to Button2.
      Dim saveFileDialog1 As New SaveFileDialog()
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"
      saveFileDialog1.Title = "Save an Image File"
      saveFileDialog1.ShowDialog()

      ' If the file name is not an empty string open it for saving.
      If saveFileDialog1.FileName <> "" Then
        ' Saves the Image via a FileStream created by the OpenFile method.
        Dim fs As System.IO.FileStream = Ctype _
            (saveFileDialog1.OpenFile(), System.IO.FileStream)
        ' Saves the Image in the appropriate ImageFormat based upon the
        ' file type selected in the dialog box.
        ' NOTE that the FilterIndex property is one-based.
        Select Case saveFileDialog1.FilterIndex
            Case 1
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Jpeg)

            Case 2
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Bmp)

            Case 3
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Gif)
          End Select

          fs.Close()
      End If
  End Sub
  ```

  ```csharp
  private void button2_Click(object sender, System.EventArgs e)
  {
      // Displays a SaveFileDialog so the user can save the Image
      // assigned to Button2.
      SaveFileDialog saveFileDialog1 = new SaveFileDialog();
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
      saveFileDialog1.Title = "Save an Image File";
      saveFileDialog1.ShowDialog();

      // If the file name is not an empty string open it for saving.
      if(saveFileDialog1.FileName != "")
      {
        // Saves the Image via a FileStream created by the OpenFile method.
        System.IO.FileStream fs =
            (System.IO.FileStream)saveFileDialog1.OpenFile();
        // Saves the Image in the appropriate ImageFormat based upon the
        // File type selected in the dialog box.
        // NOTE that the FilterIndex property is one-based.
        switch(saveFileDialog1.FilterIndex)
        {
            case 1 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Jpeg);
            break;

            case 2 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Bmp);
            break;

            case 3 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Gif);
            break;
        }

      fs.Close();
      }
  }
  ```

  ```cpp
  private:
      System::Void button2_Click(System::Object ^ sender,
        System::EventArgs ^ e)
      {
        // Displays a SaveFileDialog so the user can save the Image
        // assigned to Button2.
        SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();
        saveFileDialog1->Filter =
            "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
        saveFileDialog1->Title = "Save an Image File";
        saveFileDialog1->ShowDialog();
        // If the file name is not an empty string, open it for saving.
        if(saveFileDialog1->FileName != "")
        {
            // Saves the Image through a FileStream created by
            // the OpenFile method.
            System::IO::FileStream ^ fs =
              safe_cast\<System::IO::FileStream*>(
              saveFileDialog1->OpenFile());
            // Saves the Image in the appropriate ImageFormat based on
            // the file type selected in the dialog box.
            // Note that the FilterIndex property is one based.
            switch(saveFileDialog1->FilterIndex)
            {
              case 1 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Jpeg);
                  break;
              case 2 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Bmp);
                  break;
              case 3 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Gif);
                  break;
            }
        fs->Close();
        }
      }
  ```

  <span data-ttu-id="19675-122">(ビジュアルC#とビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="19675-122">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  <span data-ttu-id="19675-123">ファイルストリームの書き込みの詳細について<xref:System.IO.FileStream.BeginWrite%2A>は<xref:System.IO.FileStream.Write%2A>、「」および「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19675-123">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>

  > [!NOTE]
  > <span data-ttu-id="19675-124"><xref:System.Windows.Forms.RichTextBox>コントロールなどの特定のコントロールには、ファイルを保存する機能があります。</span><span class="sxs-lookup"><span data-stu-id="19675-124">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span> <span data-ttu-id="19675-125">詳細については、MSDN オンライン ライブラリの技術文書「[Windows フォーム ダイアログ ボックスの重要コード](https://go.microsoft.com/fwlink/?LinkID=102575)」の「SaveFileDialog コンポーネント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19675-125">For more information, see the "SaveFileDialog Component" section of the MSDN Online Library technical article, [Essential Code for Windows Forms Dialog Boxes](https://go.microsoft.com/fwlink/?LinkID=102575).</span></span>

## <a name="see-also"></a><span data-ttu-id="19675-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="19675-126">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="19675-127">SaveFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="19675-127">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
