---
title: '方法: Windows フォーム コントロールによって表示されるイメージを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 1de835bda5ac906837ac3fbd97b87f68f14d1953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771531"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="7ba91-102">方法: Windows フォーム コントロールによって表示されるイメージを設定する</span><span class="sxs-lookup"><span data-stu-id="7ba91-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="7ba91-103">いくつかの Windows フォーム コントロールは、イメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7ba91-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="7ba91-104">これらのイメージには、ボタン上のフロッピー ディスク アイコンなど、コントロールの目的を明確にするアイコンがあります、**保存**コマンド。</span><span class="sxs-lookup"><span data-stu-id="7ba91-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="7ba91-105">また、アイコンには、外観と動作を制御するための背景イメージもあります。</span><span class="sxs-lookup"><span data-stu-id="7ba91-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="7ba91-106">コントロールによって表示されるイメージを設定するには</span><span class="sxs-lookup"><span data-stu-id="7ba91-106">To set the image displayed by a control</span></span>  
  
1. <span data-ttu-id="7ba91-107">コントロールの設定`Image`または`BackgroundImage`プロパティ型のオブジェクトを<xref:System.Drawing.Image>します。</span><span class="sxs-lookup"><span data-stu-id="7ba91-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="7ba91-108">一般に、するはから読み込まれるイメージ ファイルを使用して、<xref:System.Drawing.Image.FromFile%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7ba91-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="7ba91-109">イメージの場所は次のコード例で、パスが設定、**マイ ピクチャ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7ba91-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="7ba91-110">Windows オペレーティング システムを実行しているほとんどのコンピューターでは、このディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ba91-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="7ba91-111">これにより、ユーザーは最小限のシステム アクセスのレベルでアプリケーションを安全に実行がもできます。</span><span class="sxs-lookup"><span data-stu-id="7ba91-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="7ba91-112">次のコード例では、既に使用して、フォームが必要です、<xref:System.Windows.Forms.PictureBox>コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="7ba91-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7ba91-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ba91-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
