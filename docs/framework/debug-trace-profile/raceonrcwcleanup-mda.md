---
title: raceOnRCWCleanup MDA
description: RaceOnRCWCleanup managed デバッグアシスタント (MDA) を確認します。これは、RCW が別のスレッドで使用されている場合、または .NET のスレッドスタックを解放している場合にアクティブ化されます。
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: e86ef96bebb648c7927ae5fec8b68fc4429b268b
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803652"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="ea01c-103">raceOnRCWCleanup MDA</span><span class="sxs-lookup"><span data-stu-id="ea01c-103">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="ea01c-104"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> メソッドなどのコマンドを使用して [ランタイム呼び出し可能ラッパー](../../standard/native-interop/runtime-callable-wrapper.md) (RCW: Runtime Callable Wrapper) を解放する呼び出しがなされた時点でその RCW が使用中であることを共通言語ランタイム (CLR: Common Language Runtime) が検出すると、`raceOnRCWCleanup` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="ea01c-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ea01c-105">現象</span><span class="sxs-lookup"><span data-stu-id="ea01c-105">Symptoms</span></span>  
 <span data-ttu-id="ea01c-106"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> メソッド、または類似メソッドを使用して RCW が解放中または解放後に、アクセス違反またはメモリ破損が発生します。</span><span class="sxs-lookup"><span data-stu-id="ea01c-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ea01c-107">原因</span><span class="sxs-lookup"><span data-stu-id="ea01c-107">Cause</span></span>  
 <span data-ttu-id="ea01c-108">別のスレッドまたは解放中のスレッド スタックで、RCW が使用中です。</span><span class="sxs-lookup"><span data-stu-id="ea01c-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="ea01c-109">使用中の RCW は解放できません。</span><span class="sxs-lookup"><span data-stu-id="ea01c-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ea01c-110">解決策</span><span class="sxs-lookup"><span data-stu-id="ea01c-110">Resolution</span></span>  
 <span data-ttu-id="ea01c-111">現在のスレッドまたは他のスレッドで使用中の可能性がある RCW は、解放しないでください。</span><span class="sxs-lookup"><span data-stu-id="ea01c-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ea01c-112">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="ea01c-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="ea01c-113">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="ea01c-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ea01c-114">出力</span><span class="sxs-lookup"><span data-stu-id="ea01c-114">Output</span></span>  
 <span data-ttu-id="ea01c-115">エラーを説明するメッセージです。</span><span class="sxs-lookup"><span data-stu-id="ea01c-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ea01c-116">構成</span><span class="sxs-lookup"><span data-stu-id="ea01c-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea01c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea01c-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ea01c-118">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="ea01c-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ea01c-119">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="ea01c-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
