---
title: '方法 : デザイナーを使用してピクチャを読み込む'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 12b90d561a18fcffaafb9c45b7fa6be6dd060215
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736330"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="ab5b3-102">方法 : デザイナーを使用してピクチャを読み込む (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ab5b3-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="ab5b3-103">Windows フォーム <xref:System.Windows.Forms.PictureBox> コントロールを使用すると、<xref:System.Windows.Forms.PictureBox.Image%2A> プロパティを有効な画像に設定することによって、デザイン時にフォームの画像を読み込んで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="ab5b3-104">次の表に、許容されるファイルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="ab5b3-105">種類</span><span class="sxs-lookup"><span data-stu-id="ab5b3-105">Type</span></span>|<span data-ttu-id="ab5b3-106">ファイル名拡張子</span><span class="sxs-lookup"><span data-stu-id="ab5b3-106">File name extension</span></span>|
|---|---|
|<span data-ttu-id="ab5b3-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="ab5b3-107">Bitmap</span></span>|<span data-ttu-id="ab5b3-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="ab5b3-108">.bmp</span></span>|
|<span data-ttu-id="ab5b3-109">アイコン</span><span class="sxs-lookup"><span data-stu-id="ab5b3-109">Icon</span></span>|<span data-ttu-id="ab5b3-110">.ico</span><span class="sxs-lookup"><span data-stu-id="ab5b3-110">.ico</span></span>|
|<span data-ttu-id="ab5b3-111">GIF</span><span class="sxs-lookup"><span data-stu-id="ab5b3-111">GIF</span></span>|<span data-ttu-id="ab5b3-112">.gif</span><span class="sxs-lookup"><span data-stu-id="ab5b3-112">.gif</span></span>|
|<span data-ttu-id="ab5b3-113">Metafile</span><span class="sxs-lookup"><span data-stu-id="ab5b3-113">Metafile</span></span>|<span data-ttu-id="ab5b3-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="ab5b3-114">.wmf</span></span>|
|<span data-ttu-id="ab5b3-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="ab5b3-115">JPEG</span></span>|<span data-ttu-id="ab5b3-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="ab5b3-116">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="ab5b3-117">デザイン時に画像を表示するには</span><span class="sxs-lookup"><span data-stu-id="ab5b3-117">To display a picture at design time</span></span>

1. <span data-ttu-id="ab5b3-118">フォームに <xref:System.Windows.Forms.PictureBox> コントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-118">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="ab5b3-119">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.PictureBox.Image%2A>] プロパティを選択し、省略記号ボタンを選択して **[開く]** ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-119">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="ab5b3-120">特定のファイルの種類 (.gif ファイルなど) を探している場合は、 **[ファイルの種類]** ボックスでそれを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-120">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="ab5b3-121">表示するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-121">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="ab5b3-122">デザイン時に画像をクリアするには</span><span class="sxs-lookup"><span data-stu-id="ab5b3-122">To clear the picture at design time</span></span>

1. <span data-ttu-id="ab5b3-123">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.PictureBox.Image%2A>] プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-123">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="ab5b3-124">イメージオブジェクトの名前の左側に表示される小さいサムネイル画像を右クリックし、 **[リセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab5b3-124">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab5b3-125">参照</span><span class="sxs-lookup"><span data-stu-id="ab5b3-125">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="ab5b3-126">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ab5b3-126">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="ab5b3-127">方法: 実行時にピクチャのサイズまたは配置を変更する</span><span class="sxs-lookup"><span data-stu-id="ab5b3-127">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="ab5b3-128">方法: 実行時にピクチャを設定する</span><span class="sxs-lookup"><span data-stu-id="ab5b3-128">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="ab5b3-129">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="ab5b3-129">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
