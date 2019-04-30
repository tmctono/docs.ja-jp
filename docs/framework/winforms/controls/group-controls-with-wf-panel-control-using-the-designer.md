---
title: '方法: デザイナーを使用して Windows フォーム Panel コントロールでコントロールをグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 662343af42f72816a5a673d2cd6d839a5dca9190
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971302"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="0772a-102">方法: デザイナーを使用して Windows フォーム Panel コントロールでコントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="0772a-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="0772a-103">Windows フォーム<xref:System.Windows.Forms.Panel>コントロールを使用すると、その他のコントロールをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="0772a-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="0772a-104">コントロールをグループ化の 3 つの理由があります。</span><span class="sxs-lookup"><span data-stu-id="0772a-104">There are three reasons to group controls.</span></span> <span data-ttu-id="0772a-105">視覚的にわかりやすいユーザー インターフェイスです。 関連するフォーム要素のグループ化もう 1 つは、プログラムによるグループ化、ラジオ ボタンの例です。最後には、単位としてデザイン時にコントロールを移動するためです。</span><span class="sxs-lookup"><span data-stu-id="0772a-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0772a-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0772a-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0772a-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0772a-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0772a-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0772a-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="0772a-109">コントロールのグループを作成するには</span><span class="sxs-lookup"><span data-stu-id="0772a-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="0772a-110">ドラッグ、<xref:System.Windows.Forms.Panel>コントロールから、 **Windows フォーム**フォームには、ツールボックスのタブ。</span><span class="sxs-lookup"><span data-stu-id="0772a-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2. <span data-ttu-id="0772a-111">その他のコントロール、パネル、パネル内の各描画を追加します。</span><span class="sxs-lookup"><span data-stu-id="0772a-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="0772a-112">既存のコントロール パネルにする場合は、すべてのコントロールを選択する、選択、クリップボードに切り取ります、<xref:System.Windows.Forms.Panel>を制御して、パネルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0772a-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="0772a-113">パネルにもドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="0772a-113">You can also drag them into the panel.</span></span>  
  
3. <span data-ttu-id="0772a-114">(省略可能)パネルに罫線を追加する場合は、設定、<xref:System.Windows.Forms.BorderStyle>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0772a-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="0772a-115">次の 3 つの選択肢があります: <xref:System.Windows.Forms.BorderStyle.Fixed3D>、 <xref:System.Windows.Forms.BorderStyle.FixedSingle>、および<xref:System.Windows.Forms.BorderStyle.None>します。</span><span class="sxs-lookup"><span data-stu-id="0772a-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0772a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0772a-116">See also</span></span>

- [<span data-ttu-id="0772a-117">Panel コントロール</span><span class="sxs-lookup"><span data-stu-id="0772a-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="0772a-118">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="0772a-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="0772a-119">方法: パネルの背景を設定します。</span><span class="sxs-lookup"><span data-stu-id="0772a-119">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
