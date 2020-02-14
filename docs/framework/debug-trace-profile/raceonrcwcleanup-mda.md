---
title: raceOnRCWCleanup MDA
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: edf1fe3ee5be631f7f3c42f4a6cdb17f1be722cf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216197"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="76433-102">raceOnRCWCleanup MDA</span><span class="sxs-lookup"><span data-stu-id="76433-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="76433-103">`raceOnRCWCleanup` メソッドなどのコマンドを使用して [ランタイム呼び出し可能ラッパー](../../standard/native-interop/runtime-callable-wrapper.md) (RCW: Runtime Callable Wrapper) を解放する呼び出しがなされた時点でその RCW が使用中であることを共通言語ランタイム (CLR: Common Language Runtime) が検出すると、<xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="76433-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="76433-104">現象</span><span class="sxs-lookup"><span data-stu-id="76433-104">Symptoms</span></span>  
 <span data-ttu-id="76433-105"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> メソッド、または類似メソッドを使用して RCW が解放中または解放後に、アクセス違反またはメモリ破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="76433-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="76433-106">原因</span><span class="sxs-lookup"><span data-stu-id="76433-106">Cause</span></span>  
 <span data-ttu-id="76433-107">別のスレッドまたは解放中のスレッド スタックで、RCW が使用中です。</span><span class="sxs-lookup"><span data-stu-id="76433-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="76433-108">使用中の RCW は解放できません。</span><span class="sxs-lookup"><span data-stu-id="76433-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="76433-109">解決策</span><span class="sxs-lookup"><span data-stu-id="76433-109">Resolution</span></span>  
 <span data-ttu-id="76433-110">現在のスレッドまたは他のスレッドで使用中の可能性がある RCW は、解放しないでください。</span><span class="sxs-lookup"><span data-stu-id="76433-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="76433-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="76433-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="76433-112">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="76433-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="76433-113">出力</span><span class="sxs-lookup"><span data-stu-id="76433-113">Output</span></span>  
 <span data-ttu-id="76433-114">エラーを説明するメッセージです。</span><span class="sxs-lookup"><span data-stu-id="76433-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="76433-115">構成</span><span class="sxs-lookup"><span data-stu-id="76433-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76433-116">参照</span><span class="sxs-lookup"><span data-stu-id="76433-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="76433-117">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="76433-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="76433-118">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="76433-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
