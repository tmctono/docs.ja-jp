---
title: '方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211683"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="7d2c2-102">方法: デザイン時に Windows フォーム上のコントロールのツールヒントを設定します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-102">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="7d2c2-103">設定することができます、<xref:System.Windows.Forms.ToolTip>コードまたは Visual Studio での Windows フォーム デザイナーでの文字列。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="7d2c2-104">詳細については、<xref:System.Windows.Forms.ToolTip>コンポーネントを参照してください[ToolTip コンポーネントの概要](tooltip-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="7d2c2-105">ツールヒントをプログラムで設定します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-105">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="7d2c2-106">ツールヒントを表示するコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-106">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="7d2c2-107">使用して、<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>のメソッド、<xref:System.Windows.Forms.ToolTip>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-107">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="7d2c2-108">デザイナーでツールヒントを設定します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-108">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="7d2c2-109">Visual Studio で、追加、<xref:System.Windows.Forms.ToolTip>コンポーネントをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-109">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="7d2c2-110">ツールヒントを表示または、フォームに追加されるコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-110">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="7d2c2-111">**プロパティ**ウィンドウで、設定、 **ToolTip1 のツールヒント**テキストの適切な文字列値。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-111">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="7d2c2-112">ツールヒントをプログラムで削除するには</span><span class="sxs-lookup"><span data-stu-id="7d2c2-112">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="7d2c2-113">使用して、<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>のメソッド、<xref:System.Windows.Forms.ToolTip>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-113">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="7d2c2-114">デザイナーでツールヒントを削除します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-114">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="7d2c2-115">Visual Studio で、ツールヒントを表示するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-115">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="7d2c2-116">**プロパティ**ウィンドウ内のテキストを削除、 **ToolTip1 のツールヒント**します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-116">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d2c2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d2c2-117">See also</span></span>

- [<span data-ttu-id="7d2c2-118">ToolTip コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="7d2c2-118">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="7d2c2-119">方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更します。</span><span class="sxs-lookup"><span data-stu-id="7d2c2-119">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="7d2c2-120">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7d2c2-120">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
