---
title: Timer コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742775"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="7d47b-102">Timer コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="7d47b-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="7d47b-103">Windows フォーム <xref:System.Windows.Forms.Timer> は、一定の間隔でイベントを発生させるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="7d47b-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="7d47b-104">このコンポーネントは、Windows フォームの環境用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="7d47b-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="7d47b-105">サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d47b-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="7d47b-106">主要なプロパティ、メソッド、およびイベント</span><span class="sxs-lookup"><span data-stu-id="7d47b-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="7d47b-107">間隔の長さは、<xref:System.Windows.Forms.Timer.Interval%2A> プロパティによって定義され、その値はミリ秒単位です。</span><span class="sxs-lookup"><span data-stu-id="7d47b-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="7d47b-108">コンポーネントが有効になると、<xref:System.Windows.Forms.Timer.Tick> イベントがすべての間隔で発生します。</span><span class="sxs-lookup"><span data-stu-id="7d47b-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="7d47b-109">ここで、実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7d47b-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="7d47b-110">詳細については、「[方法: Windows フォーム Timer コンポーネントを使用して一定間隔でプロシージャを実行する](run-procedures-at-set-intervals-with-wf-timer-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d47b-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="7d47b-111"><xref:System.Windows.Forms.Timer> コンポーネントの主要なメソッドは <xref:System.Windows.Forms.Timer.Start%2A> と <xref:System.Windows.Forms.Timer.Stop%2A>であり、タイマーをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="7d47b-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="7d47b-112">タイマーがオフに切り替わると、リセットされます。<xref:System.Windows.Forms.Timer> コンポーネントを一時停止する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="7d47b-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d47b-113">参照</span><span class="sxs-lookup"><span data-stu-id="7d47b-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="7d47b-114">Timer コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7d47b-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="7d47b-115">Windows フォームの Timer コンポーネントの Interval プロパティの制限</span><span class="sxs-lookup"><span data-stu-id="7d47b-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
