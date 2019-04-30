---
title: ToolTip コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 3fbe883501d1ce36ca25ea07631f98042f451e07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009328"
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="bb5b1-102">ToolTip コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="bb5b1-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="bb5b1-103">Windows フォーム <xref:System.Windows.Forms.ToolTip> コンポーネントは、ユーザーがコントロールをポイントしたときにテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="bb5b1-104">ツールヒントは任意のコントロールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="bb5b1-105">このコンポーネントの使用例: フォーム領域を保存するボタンに小さなアイコンを表示およびボタンの機能を説明するツールヒントを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="bb5b1-106">ToolTip コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="bb5b1-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="bb5b1-107">A<xref:System.Windows.Forms.ToolTip>コンポーネントは、提供、`ToolTip`を Windows フォームやその他のコンテナーに複数のコントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="bb5b1-108">たとえば、1 つを配置する場合<xref:System.Windows.Forms.ToolTip>フォーム上のコンポーネントの「名前を入力する」表示できます、<xref:System.Windows.Forms.TextBox>を制御し、「ここをクリックして変更を保存する」、<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="bb5b1-109">主要なメソッド、<xref:System.Windows.Forms.ToolTip>コンポーネントは<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>と<xref:System.Windows.Forms.ToolTip.GetToolTip%2A>します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="bb5b1-110">使用することができます、<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>コントロールに表示されるツールヒントを設定します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="bb5b1-111">詳細については、「[方法 :デザイン時に Windows フォーム上のコントロールのツールヒントを設定](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="bb5b1-112">プロパティは<xref:System.Windows.Forms.ToolTip.Active%2A>設定する必要がある必要があります`true`のツールヒントを表示すると<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>、ツール ヒントの文字列が示されている時間の長さを設定するのツールヒントを表示するには、コントロールでユーザーがどのくらいの期間ポイントする必要がありますと時間方法ツールヒント ウィンドウが表示されるがされます。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="bb5b1-113">詳細については、「[方法 :Windows フォームの ToolTip コンポーネントの遅延時間を変更](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5b1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb5b1-114">See also</span></span>

- <xref:System.Windows.Forms.ToolTip>
- [<span data-ttu-id="bb5b1-115">方法: デザイン時に Windows フォーム上のコントロールのツールヒントを設定します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="bb5b1-116">方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更します。</span><span class="sxs-lookup"><span data-stu-id="bb5b1-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
