---
title: '方法: 実行時 (Windows フォーム) にサイズまたは画像の配置を変更します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: 695abf51870ef9164e4543a91b3183e801eee55f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649248"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="9a340-102">方法: 実行時 (Windows フォーム) にサイズまたは画像の配置を変更します。</span><span class="sxs-lookup"><span data-stu-id="9a340-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="9a340-103">Windows フォームを使用する場合<xref:System.Windows.Forms.PictureBox>コントロール、フォームで設定することができます、<xref:System.Windows.Forms.PictureBox.SizeMode%2A>をプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9a340-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="9a340-104">コントロールの左上隅で、画像の左上を揃え</span><span class="sxs-lookup"><span data-stu-id="9a340-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="9a340-105">コントロール内で画像を中央揃え</span><span class="sxs-lookup"><span data-stu-id="9a340-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="9a340-106">表示の画像に合わせてコントロールのサイズを調整します。</span><span class="sxs-lookup"><span data-stu-id="9a340-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="9a340-107">コントロールに合わせて、表示される任意の画像を拡大します。</span><span class="sxs-lookup"><span data-stu-id="9a340-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="9a340-108">(特にビットマップ形式の 1 つ) 画像を拡大すると、イメージの品質の損失を生成できます。</span><span class="sxs-lookup"><span data-stu-id="9a340-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="9a340-109">実行時にイメージを描画するためのグラフィックス命令リストのメタファイルはストレッチ ビットマップよりも適しています。</span><span class="sxs-lookup"><span data-stu-id="9a340-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="9a340-110">実行時に、SizeMode プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="9a340-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="9a340-111">設定<xref:System.Windows.Forms.PictureBox.SizeMode%2A>に<xref:System.Windows.Forms.PictureBoxSizeMode.Normal>(既定)、 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>、 <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>、または<xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>します。</span><span class="sxs-lookup"><span data-stu-id="9a340-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="9a340-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> コントロールの左上隅にある; で、イメージが格納されることを意味します。イメージがコントロールよりも大きい場合は、その右下隅、クリッピングされます。</span><span class="sxs-lookup"><span data-stu-id="9a340-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="9a340-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> イメージがコントロールの中央に配置する方法イメージがコントロールよりも大きい場合は、画像の外側の縁が切り取られます。</span><span class="sxs-lookup"><span data-stu-id="9a340-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="9a340-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> コントロールのサイズは、イメージのサイズに調整されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9a340-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="9a340-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> 逆の場合は、イメージのサイズは、コントロールのサイズに調整されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="9a340-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="9a340-116">次の例では、イメージの場所に設定されているパスは、My Documents フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9a340-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="9a340-117">これは、Windows オペレーティング システムを実行しているほとんどのコンピューターにはでこのディレクトリが含まれていると想定できます。</span><span class="sxs-lookup"><span data-stu-id="9a340-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="9a340-118">また、このようにすることで、最小限のシステム アクセス レベルしか持たないユーザーもアプリケーションを安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9a340-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="9a340-119">次の例でフォームを前提としています、<xref:System.Windows.Forms.PictureBox>コントロールが既に追加されています。</span><span class="sxs-lookup"><span data-stu-id="9a340-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9a340-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a340-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="9a340-121">方法: デザイナーを使用してピクチャを読み込む.</span><span class="sxs-lookup"><span data-stu-id="9a340-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="9a340-122">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9a340-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="9a340-123">方法: 実行時にピクチャを設定します。</span><span class="sxs-lookup"><span data-stu-id="9a340-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="9a340-124">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="9a340-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
