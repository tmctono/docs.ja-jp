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
ms.openlocfilehash: 99bde4fac7b3057358c7e6a8550efdb4cc351eb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037883"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="87118-102">方法: Windows フォームコントロールによって表示されるイメージを設定する</span><span class="sxs-lookup"><span data-stu-id="87118-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="87118-103">いくつかの Windows フォームコントロールでイメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="87118-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="87118-104">これらのイメージは、 **[保存]** コマンドを示すボタン上のフロッピーディスクアイコンなど、コントロールの目的を明確にするアイコンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="87118-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="87118-105">または、アイコンに背景画像を使用して、コントロールの外観と動作を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="87118-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="87118-106">コントロールによって表示されるイメージを設定するには</span><span class="sxs-lookup"><span data-stu-id="87118-106">To set the image displayed by a control</span></span>

1. <span data-ttu-id="87118-107">コントロールの`Image`プロパティまたは`BackgroundImage`プロパティを、型<xref:System.Drawing.Image>のオブジェクトに設定します。</span><span class="sxs-lookup"><span data-stu-id="87118-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="87118-108">通常は、 <xref:System.Drawing.Image.FromFile%2A>メソッドを使用して、ファイルからイメージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="87118-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

     <span data-ttu-id="87118-109">次のコード例では、イメージの場所に設定されているパスが **[マイピクチャ**] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="87118-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="87118-110">Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="87118-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="87118-111">これにより、最小限のシステムアクセスレベルを持つユーザーも、アプリケーションを安全に実行できます。</span><span class="sxs-lookup"><span data-stu-id="87118-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="87118-112">次のコード例では、 <xref:System.Windows.Forms.PictureBox>コントロールが追加されたフォームが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="87118-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="87118-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="87118-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
