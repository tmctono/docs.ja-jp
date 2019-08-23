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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca3b28d0d27af0a752de894f5856b76939b01e09
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967241"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="a10a0-102">raceOnRCWCleanup MDA</span><span class="sxs-lookup"><span data-stu-id="a10a0-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="a10a0-103"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> メソッドなどのコマンドを使用して [ランタイム呼び出し可能ラッパー](../../standard/native-interop/runtime-callable-wrapper.md) (RCW: Runtime Callable Wrapper) を解放する呼び出しがなされた時点でその RCW が使用中であることを共通言語ランタイム (CLR: Common Language Runtime) が検出すると、`raceOnRCWCleanup` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="a10a0-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a10a0-104">症状</span><span class="sxs-lookup"><span data-stu-id="a10a0-104">Symptoms</span></span>  
 <span data-ttu-id="a10a0-105"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> メソッド、または類似メソッドを使用して RCW が解放中または解放後に、アクセス違反またはメモリ破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="a10a0-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a10a0-106">原因</span><span class="sxs-lookup"><span data-stu-id="a10a0-106">Cause</span></span>  
 <span data-ttu-id="a10a0-107">別のスレッドまたは解放中のスレッド スタックで、RCW が使用中です。</span><span class="sxs-lookup"><span data-stu-id="a10a0-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="a10a0-108">使用中の RCW は解放できません。</span><span class="sxs-lookup"><span data-stu-id="a10a0-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a10a0-109">解決策</span><span class="sxs-lookup"><span data-stu-id="a10a0-109">Resolution</span></span>  
 <span data-ttu-id="a10a0-110">現在のスレッドまたは他のスレッドで使用中の可能性がある RCW は、解放しないでください。</span><span class="sxs-lookup"><span data-stu-id="a10a0-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a10a0-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="a10a0-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="a10a0-112">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="a10a0-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a10a0-113">Output</span><span class="sxs-lookup"><span data-stu-id="a10a0-113">Output</span></span>  
 <span data-ttu-id="a10a0-114">エラーを説明するメッセージです。</span><span class="sxs-lookup"><span data-stu-id="a10a0-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a10a0-115">構成</span><span class="sxs-lookup"><span data-stu-id="a10a0-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a10a0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a10a0-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a10a0-117">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="a10a0-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a10a0-118">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="a10a0-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
