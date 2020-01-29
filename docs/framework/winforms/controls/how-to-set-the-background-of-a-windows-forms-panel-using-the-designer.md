---
title: デザイナーを使用してパネルの背景を設定する
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731920"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="66d6b-102">方法: デザイナーを使用して Windows フォームパネルの背景を設定する</span><span class="sxs-lookup"><span data-stu-id="66d6b-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="66d6b-103">Windows フォーム <xref:System.Windows.Forms.Panel> コントロールには、背景色と背景画像の両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="66d6b-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="66d6b-104"><xref:System.Windows.Forms.Control.BackColor%2A> プロパティは、ラベルやラジオボタンなど、パネルに含まれるコントロールの背景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="66d6b-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="66d6b-105"><xref:System.Windows.Forms.Control.BackgroundImage%2A> プロパティが設定されていない場合、<xref:System.Windows.Forms.Control.BackColor%2A> 選択によってパネル全体が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66d6b-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="66d6b-106"><xref:System.Windows.Forms.Control.BackgroundImage%2A> プロパティが設定されている場合、パネルに含まれているコントロールの背後に画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="66d6b-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="66d6b-107">次の手順では、<xref:System.Windows.Forms.Panel> コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="66d6b-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="66d6b-108">Visual Studio でこのようなプロジェクトを設定する方法の詳細については、「[方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)する」および「[方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66d6b-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="66d6b-109">Windows フォームデザイナーの背景を設定する</span><span class="sxs-lookup"><span data-stu-id="66d6b-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="66d6b-110">Visual Studio でプロジェクトを開き、[<xref:System.Windows.Forms.Panel>] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="66d6b-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="66d6b-111">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.Control.BackColor%2A>] プロパティの横にある矢印ボタンをクリックして、3つのタブを含むウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="66d6b-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="66d6b-112">**[カスタム]** タブを選択して、色のパレットを表示します。</span><span class="sxs-lookup"><span data-stu-id="66d6b-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="66d6b-113">**[Web]** または **[システム]** タブを選択して、色の定義済みの名前の一覧を表示し、色を選択します。</span><span class="sxs-lookup"><span data-stu-id="66d6b-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="66d6b-114">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.Control.BackgroundImage%2A>] プロパティの横にある矢印ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66d6b-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="66d6b-115">**[開く]** ダイアログボックスで、表示するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="66d6b-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="66d6b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="66d6b-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="66d6b-117">Panel コントロール</span><span class="sxs-lookup"><span data-stu-id="66d6b-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="66d6b-118">Panel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="66d6b-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="66d6b-119">方法: デザイナーを使用して Windows フォーム Panel コントロールでコントロールをグループ化する</span><span class="sxs-lookup"><span data-stu-id="66d6b-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
