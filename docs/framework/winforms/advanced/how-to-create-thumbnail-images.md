---
title: '方法: サムネイル イメージを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: b9afbac85dee90938e2bd55ebe19d3b02c0d66d5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341492"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="10e70-102">方法: サムネイル イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="10e70-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="10e70-103">サムネイル イメージは、小さいイメージのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="10e70-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="10e70-104">サムネイル イメージを作成するには呼び出すことによって、<xref:System.Drawing.Image.GetThumbnailImage%2A>のメソッド、<xref:System.Drawing.Image>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="10e70-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10e70-105">例</span><span class="sxs-lookup"><span data-stu-id="10e70-105">Example</span></span>  
 <span data-ttu-id="10e70-106">次の例では、構築、 <xref:System.Drawing.Image> JPG ファイルからのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="10e70-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="10e70-107">元のイメージは、640 ピクセルの幅および 479 ピクセルの高さを持ちます。</span><span class="sxs-lookup"><span data-stu-id="10e70-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="10e70-108">コードでは、100 ピクセルの幅と高さ 100 ピクセルの持つサムネイル イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="10e70-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="10e70-109">次の図は、サムネイル画像を示します。</span><span class="sxs-lookup"><span data-stu-id="10e70-109">The following illustration shows the thumbnail image.</span></span>  
  
 <span data-ttu-id="10e70-110">![サムネイル画像](./media/thumbnail1.png "Thumbnail1")</span><span class="sxs-lookup"><span data-stu-id="10e70-110">![Thumbnail Image](./media/thumbnail1.png "Thumbnail1")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10e70-111">この例では、コールバック メソッドが宣言されるが、使用されていません。</span><span class="sxs-lookup"><span data-stu-id="10e70-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="10e70-112">これには、GDI + のすべてのバージョンがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="10e70-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10e70-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="10e70-113">Compiling the Code</span></span>  
 <span data-ttu-id="10e70-114">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="10e70-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="10e70-115">例を実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="10e70-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="10e70-116">新しい Windows フォーム アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="10e70-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="10e70-117">コード例をフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="10e70-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="10e70-118">フォームのハンドラーを作成<xref:System.Windows.Forms.Control.Paint>イベント</span><span class="sxs-lookup"><span data-stu-id="10e70-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="10e70-119"><xref:System.Windows.Forms.Control.Paint>ハンドラーを呼び出し、`GetThumbnail`メソッドを渡します`e`の<xref:System.Windows.Forms.PaintEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="10e70-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="10e70-120">サムネイルを作成したいイメージ ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="10e70-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="10e70-121">`GetThumbnail`メソッドは、パスを指定し、ファイル名をイメージにします。</span><span class="sxs-lookup"><span data-stu-id="10e70-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="10e70-122">F5 キーを押して、例を実行します。</span><span class="sxs-lookup"><span data-stu-id="10e70-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="10e70-123">フォームに 100 × 100 のサムネイル画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10e70-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e70-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="10e70-124">See also</span></span>

- [<span data-ttu-id="10e70-125">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="10e70-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="10e70-126">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="10e70-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
