---
title: '方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: cf257cccd272c16c3d7c3d403456265444fc8ac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781239"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="eca24-102">方法: Windows フォームの ToolTip コンポーネントの遅延時間を変更する</span><span class="sxs-lookup"><span data-stu-id="eca24-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="eca24-103">Windows フォームに設定できる複数の遅延時間の値がある<xref:System.Windows.Forms.ToolTip>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="eca24-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="eca24-104">これらすべてのプロパティの測定単位は、(ミリ秒) です。</span><span class="sxs-lookup"><span data-stu-id="eca24-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="eca24-105"><xref:System.Windows.Forms.ToolTip.InitialDelay%2A>プロパティは、ユーザーが、関連付けられたコントロールに表示されるツールヒントの文字列でポイントする必要があります期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="eca24-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="eca24-106"><xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>プロパティ後続のヒント文字列が表示されるツールヒントに関連付けられている 1 つのコントロール間マウスを移動するためにかかる時間をミリ秒単位の数を設定します。</span><span class="sxs-lookup"><span data-stu-id="eca24-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="eca24-107"><xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>プロパティがツール ヒントの文字列が表示される時間の長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="eca24-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="eca24-108">これらの値を設定するには、個別またはの値を設定して、<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>プロパティです。 その他の遅延に割り当てられている値に基づいてプロパティが設定、<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="eca24-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="eca24-109">たとえば、 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> N の値に設定されている<xref:System.Windows.Forms.ToolTip.InitialDelay%2A>N に設定されている<xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>の値に設定されている<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>5 で割った値 (または N/5) と<xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>5 倍の値を示す値に設定されている、<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>プロパティ (または 5 個以上)。</span><span class="sxs-lookup"><span data-stu-id="eca24-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="eca24-110">遅延を設定するには</span><span class="sxs-lookup"><span data-stu-id="eca24-110">To set the delay</span></span>  
  
1. <span data-ttu-id="eca24-111">この例で示すように、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="eca24-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eca24-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="eca24-112">See also</span></span>

- [<span data-ttu-id="eca24-113">ToolTip コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="eca24-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="eca24-114">方法: デザイン時に Windows フォーム上のコントロールのツールヒントを設定します。</span><span class="sxs-lookup"><span data-stu-id="eca24-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="eca24-115">ToolTip コンポーネント</span><span class="sxs-lookup"><span data-stu-id="eca24-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
