---
title: Timer Component Interval プロパティの制限事項
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745233"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="b6b31-102">Windows フォームの Timer コンポーネントの Interval プロパティの制限</span><span class="sxs-lookup"><span data-stu-id="b6b31-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="b6b31-103">Windows フォーム <xref:System.Windows.Forms.Timer> コンポーネントには、1つのタイマーイベントから次のタイマーイベントまでの経過時間をミリ秒単位で指定する <xref:System.Windows.Forms.Timer.Interval%2A> プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b6b31-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="b6b31-104">コンポーネントが無効になっていない限り、タイマーはほぼ同じ間隔で <xref:System.Windows.Forms.Timer.Tick> イベントを受信し続けます。</span><span class="sxs-lookup"><span data-stu-id="b6b31-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="b6b31-105">このコンポーネントは、Windows フォームの環境用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="b6b31-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="b6b31-106">サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b31-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="b6b31-107">Interval プロパティ</span><span class="sxs-lookup"><span data-stu-id="b6b31-107">The Interval Property</span></span>  
 <span data-ttu-id="b6b31-108"><xref:System.Windows.Forms.Timer.Interval%2A> プロパティには、<xref:System.Windows.Forms.Timer> コンポーネントをプログラミングする際に考慮すべきいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="b6b31-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="b6b31-109">アプリケーションまたは他のアプリケーションがシステムに対して大量の要求 (長いループ、大量の計算、ドライブ、ネットワーク、ポートアクセスなど) を実行している場合、<xref:System.Windows.Forms.Timer.Interval%2A> プロパティで指定されているようにタイマーイベントを取得できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b6b31-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="b6b31-110">この間隔は、時間の経過と共に正確には保証されません。</span><span class="sxs-lookup"><span data-stu-id="b6b31-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="b6b31-111">正確さを確保するために、タイマーは、蓄積された時間を内部で追跡するのではなく、必要に応じてシステムクロックをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b31-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="b6b31-112"><xref:System.Windows.Forms.Timer.Interval%2A> プロパティの有効桁数はミリ秒単位です。</span><span class="sxs-lookup"><span data-stu-id="b6b31-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="b6b31-113">コンピューターによっては、ミリ秒よりも高い解像度の高解像度カウンターが提供される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6b31-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="b6b31-114">このようなカウンターの可用性は、コンピューターのプロセッサハードウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b6b31-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6b31-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6b31-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="b6b31-116">Timer コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b6b31-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="b6b31-117">Timer コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="b6b31-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
