---
title: イメージ、ビットマップ、およびメタファイル
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
ms.openlocfilehash: 2ce19642b37946db7a172e61004688059dba61db
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717428"
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="5f521-102">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="5f521-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="5f521-103">
  `Image\` クラスはラスター イメージ (ビットマップ) およびベクター イメージ (メタファイル) を操作するためのメソッドを提供する抽象基本クラスです。</span><span class="sxs-lookup"><span data-stu-id="5f521-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="5f521-104">`Bitmap` クラスおよび <xref:System.Drawing.Imaging.Metafile> クラスは、どちらも `Image` クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="5f521-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="5f521-105">`Bitmap` クラスは、ラスター イメージの読み込み、保存、および操作のための追加のメソッドを提供することで、`Image` クラスの機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="5f521-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="5f521-106">
  <xref:System.Drawing.Imaging.Metafile> クラスは、ベクター イメージの記録および検証のための追加のメソッドを提供することで、`Image\` クラスの機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="5f521-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f521-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5f521-107">In This Section</span></span>  
 [<span data-ttu-id="5f521-108">ビットマップの種類</span><span class="sxs-lookup"><span data-stu-id="5f521-108">Types of Bitmaps</span></span>](types-of-bitmaps.md)  
 <span data-ttu-id="5f521-109">さまざまなイメージ形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f521-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="5f521-110">GDI+ でのメタファイル</span><span class="sxs-lookup"><span data-stu-id="5f521-110">Metafiles in GDI+</span></span>](metafiles-in-gdi.md)  
 <span data-ttu-id="5f521-111">メタファイルの [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5f521-111">Discusses [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] support for metafiles.</span></span>  
  
 [<span data-ttu-id="5f521-112">GDI+ でのイメージの描画、配置、およびクローン作成</span><span class="sxs-lookup"><span data-stu-id="5f521-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="5f521-113">マネージド コードを使用して、ベクター イメージとラスター イメージを描画するためのメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5f521-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="5f521-114">GDI+ でのイメージのトリミングおよびスケーリング</span><span class="sxs-lookup"><span data-stu-id="5f521-114">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="5f521-115">マネージド コードを使用して、ベクター イメージとラスター イメージのトリミングとスケーリングのためのメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5f521-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5f521-116">参照</span><span class="sxs-lookup"><span data-stu-id="5f521-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="5f521-117">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5f521-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="5f521-118">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5f521-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5f521-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f521-119">Related Sections</span></span>  
 [<span data-ttu-id="5f521-120">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="5f521-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="5f521-121">アプリケーションでイメージを使用する方法を説明するトピックへのリンクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f521-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
