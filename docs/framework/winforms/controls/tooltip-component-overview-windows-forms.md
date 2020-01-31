---
title: ToolTip コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741907"
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="68a38-102">ToolTip コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="68a38-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="68a38-103">Windows フォーム <xref:System.Windows.Forms.ToolTip> コンポーネントは、ユーザーがコントロールをポイントしたときにテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="68a38-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="68a38-104">ツールヒントは任意のコントロールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="68a38-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="68a38-105">このコンポーネントの使用例: フォーム上の領域を節約するには、ボタンに小さいアイコンを表示し、ツールヒントを使用してボタンの機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="68a38-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="68a38-106">ツールヒントコンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="68a38-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="68a38-107"><xref:System.Windows.Forms.ToolTip> コンポーネントは、Windows フォームまたは他のコンテナーの複数のコントロールに `ToolTip` プロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="68a38-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="68a38-108">たとえば、フォームに1つの <xref:System.Windows.Forms.ToolTip> コンポーネントを配置した場合、<xref:System.Windows.Forms.TextBox> コントロールの "ここに名前を入力してください" と <xref:System.Windows.Forms.Button> コントロールの [ここをクリックして変更を保存します] を表示できます。</span><span class="sxs-lookup"><span data-stu-id="68a38-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="68a38-109"><xref:System.Windows.Forms.ToolTip> コンポーネントの主要なメソッドは <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> と <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>です。</span><span class="sxs-lookup"><span data-stu-id="68a38-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="68a38-110"><xref:System.Windows.Forms.ToolTip.SetToolTip%2A> メソッドを使用して、コントロールに表示されるツールヒントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="68a38-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="68a38-111">詳細については、「[方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68a38-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="68a38-112">キーのプロパティは <xref:System.Windows.Forms.ToolTip.Active%2A>です。ツールヒントを表示するには、`true` に設定する必要があります。 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>また、ツールヒントの文字列を表示する時間の長さ、ツールヒントを表示するためにユーザーがコントロールをポイントする必要がある期間、およびその後のツールヒントウィンドウが表示されるまでの時間を設定します。</span><span class="sxs-lookup"><span data-stu-id="68a38-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="68a38-113">詳細については、「[方法: Windows フォーム ToolTip コンポーネントの遅延を変更する](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68a38-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a38-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a38-114">See also</span></span>

- <xref:System.Windows.Forms.ToolTip>
- [<span data-ttu-id="68a38-115">方法: デザイン時に Windows フォームのコントロールにツールヒントを設定する</span><span class="sxs-lookup"><span data-stu-id="68a38-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="68a38-116">方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更する</span><span class="sxs-lookup"><span data-stu-id="68a38-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
