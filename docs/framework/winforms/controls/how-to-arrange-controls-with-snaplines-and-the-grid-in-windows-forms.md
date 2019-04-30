---
title: '方法: コントロールを Windows フォームのスナップ線とグリッドを使用して配置する'
ms.date: 03/30/2017
f1_keywords:
- GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
ms.openlocfilehash: 122c20e7c3e48eaa4b4986ce2cb45411dae00723
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011009"
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="bb6d0-102">方法: コントロールを Windows フォームのスナップ線とグリッドを使用して配置する</span><span class="sxs-lookup"><span data-stu-id="bb6d0-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="bb6d0-103">Visual Studio のレイアウト機能を使用すると、フォーム上のコントロールの配置場所を正確に指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-103">Using the layout features of Visual Studio, you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="bb6d0-104">コントロールをフォームに追加またはフォーム上の移動を行と、Windows フォーム デザイナーのグリッドの列に自動的に配置またはスナップ線の機能を使用してコントロールを配置することができます。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb6d0-105">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bb6d0-106">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bb6d0-107">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="bb6d0-108">すべてのコントロールをグリッドにスナップするには</span><span class="sxs-lookup"><span data-stu-id="bb6d0-108">To snap all controls to the grid</span></span>  
  
- <span data-ttu-id="bb6d0-109">選択、 **SnapToGrid** Windows フォーム デザイナーでレイアウト モード**オプション** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="bb6d0-110">詳細については、[全般、Windows フォーム デザイナー、オプション ダイアログ ボックス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span> <span data-ttu-id="bb6d0-111">すべてのコントロールでは、グリッド上の点に沿った自体今すぐ揃えます。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="bb6d0-112">グリッドの個々 のコントロールをスナップするには、それらの場所にロックできます。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="bb6d0-113">ただしがロックされているときに移動したりできないサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="bb6d0-114">コントロールのロックの詳細については、次を参照してください。[方法。Windows フォームにコントロールをロック](how-to-lock-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="bb6d0-115">スナップ線を使用してコントロールを配置するには</span><span class="sxs-lookup"><span data-stu-id="bb6d0-115">To align controls using snaplines</span></span>  
  
- <span data-ttu-id="bb6d0-116">選択、**スナップ**Windows フォーム デザイナーでレイアウト モード**オプション** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="bb6d0-117">詳細については、「[チュートリアル:フォームのスナップ線を使用して Windows 上のコントロール](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="bb6d0-118">スナップ線を使用して、フォーム上のコントロールを揃えたり整列したりすることができますようになりました。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6d0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb6d0-119">See also</span></span>

- <span data-ttu-id="bb6d0-120">[一般に、Windows フォーム デザイナー オプション ダイアログ ボックス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bb6d0-120">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- [<span data-ttu-id="bb6d0-121">チュートリアル: スナップ線を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="bb6d0-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="bb6d0-122">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="bb6d0-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="bb6d0-123">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="bb6d0-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="bb6d0-124">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="bb6d0-124">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="bb6d0-125">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="bb6d0-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="bb6d0-126">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="bb6d0-126">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="bb6d0-127">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="bb6d0-127">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
