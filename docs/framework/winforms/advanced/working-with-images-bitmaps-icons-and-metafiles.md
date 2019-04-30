---
title: イメージ、ビットマップ、アイコン、およびメタファイルの操作
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
ms.openlocfilehash: 61d534f8299c920f656abe4280cc3ea5e609c0b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011919"
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="f7e12-102">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="f7e12-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="f7e12-103">は、ラスター イメージを操作するための `Bitmap` クラスと、ベクター イメージを操作するための `Metafile` クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-103">provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="f7e12-104">`Bitmap` クラスおよび `Metafile` クラスは、どちらも `Image` クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="f7e12-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7e12-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f7e12-105">In This Section</span></span>  
 [<span data-ttu-id="f7e12-106">方法: 既存のビットマップを画面に描画します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-106">How to: Draw an Existing Bitmap to the Screen</span></span>](how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="f7e12-107">ビットマップを読み込んで描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="f7e12-108">方法: ロード テストと表示のメタファイル</span><span class="sxs-lookup"><span data-stu-id="f7e12-108">How to: Load and Display Metafiles</span></span>](how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="f7e12-109">メタファイルを読み込んで描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="f7e12-110">GDI+ でのイメージのトリミングおよびスケーリング</span><span class="sxs-lookup"><span data-stu-id="f7e12-110">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="f7e12-111">ベクター イメージおよびラスター イメージをトリミングしてスケールを調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="f7e12-112">方法: 回転、反転、およびイメージの傾斜</span><span class="sxs-lookup"><span data-stu-id="f7e12-112">How to: Rotate, Reflect, and Skew Images</span></span>](how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="f7e12-113">回転、反転、および傾斜したイメージを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="f7e12-114">方法: 画質を制御する補間モードを使用してスケーリング時</span><span class="sxs-lookup"><span data-stu-id="f7e12-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="f7e12-115"><xref:System.Drawing.Drawing2D.InterpolationMode> 列挙体を使用してイメージ品質を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f7e12-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="f7e12-116">方法: サムネイル イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-116">How to: Create Thumbnail Images</span></span>](how-to-create-thumbnail-images.md)  
 <span data-ttu-id="f7e12-117">サムネイル イメージを作成する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="f7e12-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="f7e12-118">方法: 自動スケーリングを解除してパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="f7e12-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="f7e12-119">自動スケーリングなしでイメージを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="f7e12-120">方法: イメージのメタデータの読み取り</span><span class="sxs-lookup"><span data-stu-id="f7e12-120">How to: Read Image Metadata</span></span>](how-to-read-image-metadata.md)  
 <span data-ttu-id="f7e12-121">イメージからメタデータを読み取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="f7e12-122">方法: 実行時にビットマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-122">How to: Create a Bitmap at Run Time</span></span>](how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="f7e12-123">実行時にビットマップを描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="f7e12-124">方法: Windows フォームでファイルに関連付けられているアイコンを抽出します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="f7e12-125">ファイルの埋め込みリソースであるアイコンを抽出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f7e12-126">参照</span><span class="sxs-lookup"><span data-stu-id="f7e12-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="f7e12-127">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="f7e12-128">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="f7e12-129">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f7e12-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f7e12-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7e12-130">Related Sections</span></span>  
 [<span data-ttu-id="f7e12-131">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="f7e12-131">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="f7e12-132">さまざまな種類のビットマップと、アプリケーションでこれらを操作する方法について説明するトピックへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7e12-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
