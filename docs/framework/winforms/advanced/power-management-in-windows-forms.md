---
title: Windows フォームでの電源管理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 36c152a9e388fe61b1c82a8783bf74bbe6c8f123
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592519"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="64688-102">Windows フォームでの電源管理</span><span class="sxs-lookup"><span data-stu-id="64688-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="64688-103">Windows フォーム アプリケーションによっては、Windows オペレーティング システムの電源管理機能を活用がかかります。</span><span class="sxs-lookup"><span data-stu-id="64688-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="64688-104">アプリケーションでは、コンピューターの電源の状態を監視でき、状態の変更が発生したときにアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="64688-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="64688-105">など、アプリケーションがポータブル コンピューターで実行している場合、コンピューターのバッテリ残量が一定のレベルを下回ったときに、アプリケーションで特定の機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="64688-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="64688-106">.NET Framework には、 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> AC 電源の状態またはバッテリの状態が変更されたときや、ユーザーが中断またはオペレーティング システムが再開されるなどの電源ステータスの変更があるたびに発生するイベントです。</span><span class="sxs-lookup"><span data-stu-id="64688-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="64688-107"><xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>のプロパティ、<xref:System.Windows.Forms.SystemInformation>クラスにすることが次のコード例に示すように現在の状態では、クエリに使用されます。</span><span class="sxs-lookup"><span data-stu-id="64688-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="64688-108">それに、<xref:System.Windows.Forms.BatteryChargeStatus>列挙型、<xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>プロパティには、バッテリ容量を決定するための列挙体も含まれています (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) とバッテリの充電の割合 (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>、 <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>)。</span><span class="sxs-lookup"><span data-stu-id="64688-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="64688-109">使用することができます、<xref:System.Windows.Forms.Application.SetSuspendState%2A>のメソッド、<xref:System.Windows.Forms.Application>コンピューターを休止状態または中断モードにします。</span><span class="sxs-lookup"><span data-stu-id="64688-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="64688-110">場合、`force`に設定されている引数`false`、オペレーティング システムが中断するためのアクセス許可を要求するすべてのアプリケーションにイベントをブロードキャストします。</span><span class="sxs-lookup"><span data-stu-id="64688-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="64688-111">場合、`disableWakeEvent`に設定されている引数`true`、オペレーティング システムがスリープ解除のすべてのイベントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="64688-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="64688-112">次のコード例では、コンピュータを休止状態にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="64688-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="64688-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="64688-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
