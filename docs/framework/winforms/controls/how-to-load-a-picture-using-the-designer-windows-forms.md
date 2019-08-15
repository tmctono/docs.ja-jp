---
title: '方法: デザイナーを使用して画像を読み込む (Windows フォーム)'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 818bc63b5b3bea6c73804f716a72ba3cd1a62b4c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039681"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="16405-102">方法: デザイナーを使用して画像を読み込む (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="16405-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="16405-103">Windows フォーム<xref:System.Windows.Forms.PictureBox>コントロールを使用すると、プロパティを<xref:System.Windows.Forms.PictureBox.Image%2A>有効な画像に設定することによって、デザイン時にフォームの画像を読み込んで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="16405-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="16405-104">次の表に、許容されるファイルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="16405-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="16405-105">種類</span><span class="sxs-lookup"><span data-stu-id="16405-105">Type</span></span>|<span data-ttu-id="16405-106">ファイル名の拡張子</span><span class="sxs-lookup"><span data-stu-id="16405-106">File name extension</span></span>|
|---|---|
|<span data-ttu-id="16405-107">ビットマップ</span><span class="sxs-lookup"><span data-stu-id="16405-107">Bitmap</span></span>|<span data-ttu-id="16405-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="16405-108">.bmp</span></span>|
|<span data-ttu-id="16405-109">アイコン</span><span class="sxs-lookup"><span data-stu-id="16405-109">Icon</span></span>|<span data-ttu-id="16405-110">.ico</span><span class="sxs-lookup"><span data-stu-id="16405-110">.ico</span></span>|
|<span data-ttu-id="16405-111">GIF</span><span class="sxs-lookup"><span data-stu-id="16405-111">GIF</span></span>|<span data-ttu-id="16405-112">.gif</span><span class="sxs-lookup"><span data-stu-id="16405-112">.gif</span></span>|
|<span data-ttu-id="16405-113">ピクチャ</span><span class="sxs-lookup"><span data-stu-id="16405-113">Metafile</span></span>|<span data-ttu-id="16405-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="16405-114">.wmf</span></span>|
|<span data-ttu-id="16405-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="16405-115">JPEG</span></span>|<span data-ttu-id="16405-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="16405-116">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="16405-117">デザイン時に画像を表示するには</span><span class="sxs-lookup"><span data-stu-id="16405-117">To display a picture at design time</span></span>

1. <span data-ttu-id="16405-118">フォーム上<xref:System.Windows.Forms.PictureBox>にコントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="16405-118">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="16405-119">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.PictureBox.Image%2A>プロパティを選択し、省略記号ボタンを選択して **[開く]** ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="16405-119">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="16405-120">特定のファイルの種類 (.gif ファイルなど) を探している場合は、 **[ファイルの種類]** ボックスでそれを選択します。</span><span class="sxs-lookup"><span data-stu-id="16405-120">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="16405-121">表示するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="16405-121">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="16405-122">デザイン時に画像をクリアするには</span><span class="sxs-lookup"><span data-stu-id="16405-122">To clear the picture at design time</span></span>

1. <span data-ttu-id="16405-123">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.PictureBox.Image%2A>プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="16405-123">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="16405-124">イメージオブジェクトの名前の左側に表示される小さいサムネイル画像を右クリックし、 **[リセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="16405-124">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="16405-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="16405-125">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="16405-126">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="16405-126">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="16405-127">方法: 実行時に画像のサイズまたは配置を変更する</span><span class="sxs-lookup"><span data-stu-id="16405-127">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="16405-128">方法: 実行時に画像を設定する</span><span class="sxs-lookup"><span data-stu-id="16405-128">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="16405-129">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="16405-129">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
