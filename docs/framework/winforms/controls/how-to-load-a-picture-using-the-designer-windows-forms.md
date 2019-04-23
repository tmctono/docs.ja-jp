---
title: '方法: デザイナー (Windows フォーム) を使用してピクチャを読み込む.'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 6bdf7c3df0ffd97dd88a4c442a8a73593a0447ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336383"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="db1fb-102">方法: デザイナー (Windows フォーム) を使用してピクチャを読み込む.</span><span class="sxs-lookup"><span data-stu-id="db1fb-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="db1fb-103">Windows フォームで<xref:System.Windows.Forms.PictureBox>コントロール、読み込みし、設定して、デザイン時にフォームに画像を表示できます、<xref:System.Windows.Forms.PictureBox.Image%2A>に有効な画像のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="db1fb-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="db1fb-104">次の表では、許容されるファイルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="db1fb-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="db1fb-105">型</span><span class="sxs-lookup"><span data-stu-id="db1fb-105">Type</span></span>|<span data-ttu-id="db1fb-106">ファイル名の拡張子</span><span class="sxs-lookup"><span data-stu-id="db1fb-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="db1fb-107">ビットマップ</span><span class="sxs-lookup"><span data-stu-id="db1fb-107">Bitmap</span></span>|<span data-ttu-id="db1fb-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="db1fb-108">.bmp</span></span>|  
|<span data-ttu-id="db1fb-109">アイコン</span><span class="sxs-lookup"><span data-stu-id="db1fb-109">Icon</span></span>|<span data-ttu-id="db1fb-110">.ico</span><span class="sxs-lookup"><span data-stu-id="db1fb-110">.ico</span></span>|  
|<span data-ttu-id="db1fb-111">GIF</span><span class="sxs-lookup"><span data-stu-id="db1fb-111">GIF</span></span>|<span data-ttu-id="db1fb-112">.gif</span><span class="sxs-lookup"><span data-stu-id="db1fb-112">.gif</span></span>|  
|<span data-ttu-id="db1fb-113">メタファイル</span><span class="sxs-lookup"><span data-stu-id="db1fb-113">Metafile</span></span>|<span data-ttu-id="db1fb-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="db1fb-114">.wmf</span></span>|  
|<span data-ttu-id="db1fb-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="db1fb-115">JPEG</span></span>|<span data-ttu-id="db1fb-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="db1fb-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="db1fb-117">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="db1fb-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="db1fb-118">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db1fb-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="db1fb-119">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db1fb-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="db1fb-120">デザイン時に画像を表示するには</span><span class="sxs-lookup"><span data-stu-id="db1fb-120">To display a picture at design time</span></span>  
  
1. <span data-ttu-id="db1fb-121">描画を<xref:System.Windows.Forms.PictureBox>フォーム上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="db1fb-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2. <span data-ttu-id="db1fb-122">プロパティ ウィンドウで、選択、<xref:System.Windows.Forms.PictureBox.Image%2A>プロパティ、省略記号を表示するボタンをクリックし、**オープン** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="db1fb-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3. <span data-ttu-id="db1fb-123">特定のファイルの種類 (たとえば、.gif ファイル) を探している場合にそれを選択します。、**ファイルの種類**ボックス。</span><span class="sxs-lookup"><span data-stu-id="db1fb-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4. <span data-ttu-id="db1fb-124">表示するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="db1fb-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="db1fb-125">デザイン時に、画像を消去するには</span><span class="sxs-lookup"><span data-stu-id="db1fb-125">To clear the picture at design time</span></span>  
  
1. <span data-ttu-id="db1fb-126">**プロパティ**ウィンドウで、<xref:System.Windows.Forms.PictureBox.Image%2A>プロパティと、イメージ オブジェクトの名前の左側に表示される小さなのサムネイル画像を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="db1fb-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="db1fb-127">選択**リセット**します。</span><span class="sxs-lookup"><span data-stu-id="db1fb-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1fb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="db1fb-128">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="db1fb-129">PictureBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="db1fb-129">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="db1fb-130">方法: 実行時にサイズまたは画像の配置を変更します。</span><span class="sxs-lookup"><span data-stu-id="db1fb-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="db1fb-131">方法: 実行時にピクチャを設定します。</span><span class="sxs-lookup"><span data-stu-id="db1fb-131">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="db1fb-132">PictureBox コントロール</span><span class="sxs-lookup"><span data-stu-id="db1fb-132">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
