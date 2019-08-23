---
title: '方法: Windows フォームの ImageList コンポーネントにイメージを追加または削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: 430b7f573b115c21b9e2fa87f0ace74205717285
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925118"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="d4f40-102">方法: Windows フォームの ImageList コンポーネントにイメージを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="d4f40-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="d4f40-103">Windows フォーム<xref:System.Windows.Forms.ImageList>コンポーネントには、通常、コントロールに関連付けられる前にイメージが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d4f40-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="d4f40-104">ただし、イメージリストをコントロールに関連付けた後に、イメージの追加や削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d4f40-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4f40-105">イメージを削除する場合は、関連<xref:System.Windows.Forms.ButtonBase.ImageIndex%2A>付けられているコントロールのプロパティが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4f40-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="d4f40-106">プログラムによってイメージを追加するには</span><span class="sxs-lookup"><span data-stu-id="d4f40-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="d4f40-107">イメージリストの<xref:System.Windows.Forms.ImageList.Images%2A>プロパティのメソッドを使用します。<xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A></span><span class="sxs-lookup"><span data-stu-id="d4f40-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="d4f40-108">次のコード例では、イメージの場所に設定されたパスが **[マイドキュメント**] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d4f40-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="d4f40-109">この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f40-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="d4f40-110">また、この場所を選択すると、システムアクセスレベルを最小限にしたユーザーがアプリケーションをより安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d4f40-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="d4f40-111">次のコード例では、 <xref:System.Windows.Forms.ImageList>コントロールが既に追加されているフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="d4f40-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the   
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =   
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample   
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as   
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =   
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="d4f40-112">キー値を使用してイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4f40-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="d4f40-113">キー値を受け取る<xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>イメージリストの<xref:System.Windows.Forms.ImageList.Images%2A>プロパティのメソッドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f40-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="d4f40-114">次のコード例では、イメージの場所に設定されたパスが **[マイドキュメント**] フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d4f40-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="d4f40-115">この場所は、Windows オペレーティングシステムを実行しているほとんどのコンピューターにこのフォルダーを含めることを前提としているために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4f40-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="d4f40-116">また、この場所を選択すると、システムアクセスレベルを最小限にしたユーザーがアプリケーションをより安全に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d4f40-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="d4f40-117">次のコード例では、 <xref:System.Windows.Forms.ImageList>コントロールが既に追加されているフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="d4f40-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the   
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =   
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="d4f40-118">プログラムによってすべてのイメージを削除するには</span><span class="sxs-lookup"><span data-stu-id="d4f40-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="d4f40-119">1つ<xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A>のイメージを削除するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f40-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="d4f40-120">、-または-</span><span class="sxs-lookup"><span data-stu-id="d4f40-120">,-or-</span></span>  
  
     <span data-ttu-id="d4f40-121">イメージリスト<xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>内のすべてのイメージをクリアするには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f40-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="d4f40-122">キーによってイメージを削除するには</span><span class="sxs-lookup"><span data-stu-id="d4f40-122">To remove images by key</span></span>  
  
- <span data-ttu-id="d4f40-123">キーに<xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A>よって1つのイメージを削除するには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4f40-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4f40-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4f40-124">See also</span></span>

- [<span data-ttu-id="d4f40-125">ImageList コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4f40-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="d4f40-126">ImageList コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="d4f40-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="d4f40-127">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="d4f40-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
