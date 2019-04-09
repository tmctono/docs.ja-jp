---
title: '方法: デザイナーを使用して Windows フォーム コントロールによって表示されるイメージを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
- setting images [Windows Forms], Windows Forms controls
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
ms.openlocfilehash: 2e0837e4a3058db7f1086d6a8ed53136ec86c7ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153492"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="416be-102">方法: デザイナーを使用して Windows フォーム コントロールによって表示されるイメージを設定する</span><span class="sxs-lookup"><span data-stu-id="416be-102">How to: Set the Image Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="416be-103">いくつかの Windows フォーム コントロールは、イメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="416be-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="416be-104">イメージ、アイコンをボタン上のフロッピー ディスク アイコンなど、コントロールの目的を明確にする、**保存**コマンド。</span><span class="sxs-lookup"><span data-stu-id="416be-104">The image can be an icon that clarifies the purpose of the control, such as a disk icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="416be-105">コントロールの外観を与えるための背景画像の代わりに、アイコンもあります。</span><span class="sxs-lookup"><span data-stu-id="416be-105">Alternatively, the icon can be a background image to give the control the appearance you want.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="416be-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="416be-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="416be-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="416be-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="416be-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="416be-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="416be-109">コントロールによって表示されるイメージを設定するには</span><span class="sxs-lookup"><span data-stu-id="416be-109">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="416be-110">**プロパティ**ウィンドウで、**イメージ**または**BackgroundImage**コントロールのプロパティ をクリックし、省略記号ボタン (</span><span class="sxs-lookup"><span data-stu-id="416be-110">In the **Properties** window, select the **Image** or **BackgroundImage** property of the control, then click the ellipsis button (</span></span>  
  
     <span data-ttu-id="416be-111">![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")</span><span class="sxs-lookup"><span data-stu-id="416be-111">![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")</span></span>  
  
     <span data-ttu-id="416be-112">) を表示する、**リソースの選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="416be-112">) to display the **Select Resource** dialog box.</span></span>  
  
2.  <span data-ttu-id="416be-113">表示するイメージを選択します。</span><span class="sxs-lookup"><span data-stu-id="416be-113">Select the image you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="416be-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="416be-114">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="416be-115">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="416be-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
