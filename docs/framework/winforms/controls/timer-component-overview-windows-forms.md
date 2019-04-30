---
title: Timer コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 5bef0ba87d6a496acf7575965128be2b20b437ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962618"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="8770c-102">Timer コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="8770c-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="8770c-103">Windows フォーム <xref:System.Windows.Forms.Timer> は、一定の間隔でイベントを発生させるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="8770c-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="8770c-104">このコンポーネントは、Windows フォームの環境用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="8770c-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="8770c-105">サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8770c-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="8770c-106">キー プロパティ、メソッド、およびイベント</span><span class="sxs-lookup"><span data-stu-id="8770c-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="8770c-107">間隔の長さが定義されている、<xref:System.Windows.Forms.Timer.Interval%2A>プロパティ、値はミリ秒単位で。</span><span class="sxs-lookup"><span data-stu-id="8770c-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="8770c-108">コンポーネントが有効にすると、<xref:System.Windows.Forms.Timer.Tick>イベントの発生間隔。</span><span class="sxs-lookup"><span data-stu-id="8770c-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="8770c-109">これは、実行するコードを追加することです。</span><span class="sxs-lookup"><span data-stu-id="8770c-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="8770c-110">詳細については、「[方法 :Windows フォームの Timer コンポーネントを使用して一定間隔でプロシージャを実行](run-procedures-at-set-intervals-with-wf-timer-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="8770c-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="8770c-111">主要なメソッド、<xref:System.Windows.Forms.Timer>コンポーネントは<xref:System.Windows.Forms.Timer.Start%2A>と<xref:System.Windows.Forms.Timer.Stop%2A>タイマーをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="8770c-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="8770c-112">タイマーをオフにすると、ときにリセットされます。一時停止する方法はありません、<xref:System.Windows.Forms.Timer>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="8770c-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8770c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8770c-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="8770c-114">Timer コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8770c-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="8770c-115">Windows フォームの Timer コンポーネントの Interval プロパティの制限</span><span class="sxs-lookup"><span data-stu-id="8770c-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
