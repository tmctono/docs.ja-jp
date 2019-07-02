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
ms.openlocfilehash: 8c778018a2d78fbec67a3bf41b5cbaa8e4bfb606
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504860"
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="43ed0-102">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="43ed0-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
<span data-ttu-id="43ed0-103">GDI + は、提供、`Bitmap`ラスター イメージを操作するためのクラスと`Metafile`ベクター イメージを操作するためのクラス。</span><span class="sxs-lookup"><span data-stu-id="43ed0-103">GDI+ provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="43ed0-104">`Bitmap` クラスおよび `Metafile` クラスは、どちらも `Image` クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="43ed0-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43ed0-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="43ed0-105">In This Section</span></span>  
 [<span data-ttu-id="43ed0-106">方法: 既存のビットマップを画面に描画します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-106">How to: Draw an Existing Bitmap to the Screen</span></span>](how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="43ed0-107">ビットマップを読み込んで描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="43ed0-108">方法: ロード テストと表示のメタファイル</span><span class="sxs-lookup"><span data-stu-id="43ed0-108">How to: Load and Display Metafiles</span></span>](how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="43ed0-109">メタファイルを読み込んで描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="43ed0-110">GDI+ でのイメージのトリミングおよびスケーリング</span><span class="sxs-lookup"><span data-stu-id="43ed0-110">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="43ed0-111">ベクター イメージおよびラスター イメージをトリミングしてスケールを調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="43ed0-112">方法: 回転、反転、およびイメージの傾斜</span><span class="sxs-lookup"><span data-stu-id="43ed0-112">How to: Rotate, Reflect, and Skew Images</span></span>](how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="43ed0-113">回転、反転、および傾斜したイメージを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="43ed0-114">方法: 画質を制御する補間モードを使用してスケーリング時</span><span class="sxs-lookup"><span data-stu-id="43ed0-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="43ed0-115"><xref:System.Drawing.Drawing2D.InterpolationMode> 列挙体を使用してイメージ品質を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="43ed0-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="43ed0-116">方法: サムネイル イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-116">How to: Create Thumbnail Images</span></span>](how-to-create-thumbnail-images.md)  
 <span data-ttu-id="43ed0-117">サムネイル イメージを作成する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="43ed0-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="43ed0-118">方法: 自動スケーリングを解除してパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="43ed0-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="43ed0-119">自動スケーリングなしでイメージを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="43ed0-120">方法: イメージのメタデータの読み取り</span><span class="sxs-lookup"><span data-stu-id="43ed0-120">How to: Read Image Metadata</span></span>](how-to-read-image-metadata.md)  
 <span data-ttu-id="43ed0-121">イメージからメタデータを読み取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="43ed0-122">方法: 実行時にビットマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-122">How to: Create a Bitmap at Run Time</span></span>](how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="43ed0-123">実行時にビットマップを描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="43ed0-124">方法: Windows フォームでファイルに関連付けられているアイコンを抽出します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="43ed0-125">ファイルの埋め込みリソースであるアイコンを抽出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="43ed0-126">参照</span><span class="sxs-lookup"><span data-stu-id="43ed0-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="43ed0-127">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="43ed0-128">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="43ed0-129">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="43ed0-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43ed0-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="43ed0-130">Related Sections</span></span>  
 [<span data-ttu-id="43ed0-131">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="43ed0-131">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="43ed0-132">さまざまな種類のビットマップと、アプリケーションでこれらを操作する方法について説明するトピックへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="43ed0-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
