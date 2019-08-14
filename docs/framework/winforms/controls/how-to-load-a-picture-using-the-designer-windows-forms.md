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
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972372"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="043ca-102">方法: デザイナーを使用して画像を読み込む (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="043ca-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="043ca-103">Windows フォーム<xref:System.Windows.Forms.PictureBox>コントロールを使用すると、プロパティを<xref:System.Windows.Forms.PictureBox.Image%2A>有効な画像に設定することによって、デザイン時にフォームの画像を読み込んで表示することができます。</span><span class="sxs-lookup"><span data-stu-id="043ca-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="043ca-104">次の表に、許容されるファイルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="043ca-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="043ca-105">種類</span><span class="sxs-lookup"><span data-stu-id="043ca-105">Type</span></span>|<span data-ttu-id="043ca-106">ファイル名の拡張子</span><span class="sxs-lookup"><span data-stu-id="043ca-106">File name extension</span></span>|
|----------|-------------------------|
|<span data-ttu-id="043ca-107">ビットマップ</span><span class="sxs-lookup"><span data-stu-id="043ca-107">Bitmap</span></span>|<span data-ttu-id="043ca-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="043ca-108">.bmp</span></span>|
|<span data-ttu-id="043ca-109">アイコン</span><span class="sxs-lookup"><span data-stu-id="043ca-109">Icon</span></span>|<span data-ttu-id="043ca-110">.ico</span><span class="sxs-lookup"><span data-stu-id="043ca-110">.ico</span></span>|
|<span data-ttu-id="043ca-111">GIF</span><span class="sxs-lookup"><span data-stu-id="043ca-111">GIF</span></span>|<span data-ttu-id="043ca-112">.gif</span><span class="sxs-lookup"><span data-stu-id="043ca-112">.gif</span></span>|
|<span data-ttu-id="043ca-113">ピクチャ</span><span class="sxs-lookup"><span data-stu-id="043ca-113">Metafile</span></span>|<span data-ttu-id="043ca-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="043ca-114">.wmf</span></span>|
|<span data-ttu-id="043ca-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="043ca-115">JPEG</span></span>|<span data-ttu-id="043ca-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="043ca-116">.jpg</span></span>|

> [!NOTE]
>  <span data-ttu-id="043ca-117">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="043ca-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="043ca-118">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="043ca-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="043ca-119">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="043ca-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="043ca-120">デザイン時に画像を表示するには</span><span class="sxs-lookup"><span data-stu-id="043ca-120">To display a picture at design time</span></span>

1. <span data-ttu-id="043ca-121">フォーム上<xref:System.Windows.Forms.PictureBox>にコントロールを描画します。</span><span class="sxs-lookup"><span data-stu-id="043ca-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="043ca-122">プロパティウィンドウで、 <xref:System.Windows.Forms.PictureBox.Image%2A>プロパティを選択し、省略記号ボタンをクリックして **開く** ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="043ca-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="043ca-123">特定のファイルの種類 (.gif ファイルなど) を探している場合は、 **[ファイルの種類]** ボックスでそれを選択します。</span><span class="sxs-lookup"><span data-stu-id="043ca-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="043ca-124">表示するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="043ca-124">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="043ca-125">デザイン時に画像をクリアするには</span><span class="sxs-lookup"><span data-stu-id="043ca-125">To clear the picture at design time</span></span>

1. <span data-ttu-id="043ca-126">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.PictureBox.Image%2A>プロパティを選択し、イメージオブジェクトの名前の左側に表示される小さいサムネイル画像を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="043ca-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="043ca-127">**[リセット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="043ca-127">Choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="043ca-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="043ca-128">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="043ca-129">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="043ca-129">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="043ca-130">方法: 実行時に画像のサイズまたは配置を変更する</span><span class="sxs-lookup"><span data-stu-id="043ca-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="043ca-131">方法: 実行時に画像を設定する</span><span class="sxs-lookup"><span data-stu-id="043ca-131">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="043ca-132">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="043ca-132">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
