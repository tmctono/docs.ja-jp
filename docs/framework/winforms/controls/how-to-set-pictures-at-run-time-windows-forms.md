---
title: '方法 : 実行時にピクチャを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: cd599ac7e07b5210f8bcff1ffbc76b3d9ee563d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182115"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="bf6e5-102">方法 : 実行時にピクチャを設定する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="bf6e5-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="bf6e5-103">Windows フォーム<xref:System.Windows.Forms.PictureBox>コントロールによって表示されるイメージをプログラムで設定できます。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="bf6e5-104">プログラムで画像を設定するには</span><span class="sxs-lookup"><span data-stu-id="bf6e5-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="bf6e5-105">クラスの<xref:System.Windows.Forms.PictureBox.Image%2A>メソッドを<xref:System.Drawing.Image.FromFile%2A>使用してプロパティを<xref:System.Drawing.Image>設定します。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="bf6e5-106">次の例では、イメージの場所に設定されているパスは[マイ ドキュメント]フォルダです。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="bf6e5-107">これは、Windows オペレーティング システムを実行しているほとんどのコンピュータにこのディレクトリが含まれると仮定できるためです。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="bf6e5-108">また、このようにすることで、最小限のシステム アクセス レベルしか持たないユーザーもアプリケーションを安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="bf6e5-109">次の例では、コントロールが既<xref:System.Windows.Forms.PictureBox>に追加されているフォームを想定しています。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="bf6e5-110">グラフィックをクリアするには</span><span class="sxs-lookup"><span data-stu-id="bf6e5-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="bf6e5-111">まず、イメージで使用されているメモリを解放し、次にグラフィックをクリアします。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="bf6e5-112">メモリ管理が問題になると、ガベージ コレクションによってメモリが解放されます。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="bf6e5-113">この方法でメソッドを使用する理由の<xref:System.Drawing.Image.Dispose%2A>詳細については、「[アンマネージ リソースのクリーンアップ](../../../standard/garbage-collection/unmanaged.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="bf6e5-114">このコードは、デザイン時にグラフィックがコントロールに読み込まれても、イメージをクリアします。</span><span class="sxs-lookup"><span data-stu-id="bf6e5-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6e5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf6e5-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bf6e5-116">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="bf6e5-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="bf6e5-117">方法 : デザイナーを使用してピクチャを読み込む</span><span class="sxs-lookup"><span data-stu-id="bf6e5-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="bf6e5-118">方法 : 実行時にピクチャのサイズまたは配置を変更する</span><span class="sxs-lookup"><span data-stu-id="bf6e5-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="bf6e5-119">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="bf6e5-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
