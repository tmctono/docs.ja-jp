---
title: '方法: ToolStrip を ToolStripContainer からフォームに移動する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 9106a69ea9f28442da6e3270f7cf5abb9374b62d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335265"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="2342a-102">方法: ToolStrip を ToolStripContainer からフォームに移動する</span><span class="sxs-lookup"><span data-stu-id="2342a-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="2342a-103">移動する、次の手順を使用して、<xref:System.Windows.Forms.ToolStrip>のうち、<xref:System.Windows.Forms.ToolStripContainer>からフォームにします。</span><span class="sxs-lookup"><span data-stu-id="2342a-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2342a-104">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2342a-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2342a-105">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2342a-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2342a-106">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2342a-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="2342a-107">ToolStrip を ToolStripContainer からフォームに外に移動するには</span><span class="sxs-lookup"><span data-stu-id="2342a-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1. <span data-ttu-id="2342a-108"><xref:System.Windows.Forms.ToolStrip>を選択します。</span><span class="sxs-lookup"><span data-stu-id="2342a-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2. <span data-ttu-id="2342a-109">切り取り、<xref:System.Windows.Forms.ToolStrip>で ctrl キーを押しながら X キーを押すか右クリック、<xref:System.Windows.Forms.ToolStrip>選択**切り取り**コンテキスト メニュー。</span><span class="sxs-lookup"><span data-stu-id="2342a-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3. <span data-ttu-id="2342a-110">フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="2342a-110">Select the form.</span></span>  
  
4. <span data-ttu-id="2342a-111">貼り付け、<xref:System.Windows.Forms.ToolStrip>で ctrl キーを押しながら V キーを押すか、選択**貼り付け**から、**編集**メニュー。</span><span class="sxs-lookup"><span data-stu-id="2342a-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5. <span data-ttu-id="2342a-112">設定、<xref:System.Windows.Forms.ToolStrip.Dock%2A>のプロパティ、<xref:System.Windows.Forms.ToolStrip>に**上部**します。</span><span class="sxs-lookup"><span data-stu-id="2342a-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2342a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2342a-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="2342a-114">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2342a-114">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
