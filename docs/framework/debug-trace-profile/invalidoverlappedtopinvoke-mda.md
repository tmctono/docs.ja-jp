---
title: invalidOverlappedToPinvoke MDA
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
ms.openlocfilehash: 1f557cc370d5c6121b0ad9a4528bd75dcb70a93c
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216287"
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="5047f-102">invalidOverlappedToPinvoke MDA</span><span class="sxs-lookup"><span data-stu-id="5047f-102">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="5047f-103">`invalidOverlappedToPinvoke` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) は、ガベージ コレクション ヒープで作成されていないオーバーラップ ポインターが特定の Win32 関数に渡されるとアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="5047f-103">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5047f-104">既定では、この MDA は、プラットフォームの起動の呼び出しがコードで定義され、デバッガーが各メソッドの JustMyCode 状態をレポートする場合にのみアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="5047f-104">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="5047f-105">JustMyCode を理解しないデバッガー (拡張機能なしの MDbg.exe など) は、この MDA をアクティブにしません。</span><span class="sxs-lookup"><span data-stu-id="5047f-105">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="5047f-106">このようなデバッガーに対してこの MDA を有効にするには、構成ファイルを使用し、.mda.config ファイルで `justMyCode="false"` を明示的に設定します`(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`)。</span><span class="sxs-lookup"><span data-stu-id="5047f-106">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5047f-107">現象</span><span class="sxs-lookup"><span data-stu-id="5047f-107">Symptoms</span></span>  
 <span data-ttu-id="5047f-108">クラッシュまたは説明のつかないヒープ破損。</span><span class="sxs-lookup"><span data-stu-id="5047f-108">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5047f-109">原因</span><span class="sxs-lookup"><span data-stu-id="5047f-109">Cause</span></span>  
 <span data-ttu-id="5047f-110">ガベージ コレクション ヒープで作成されていないオーバーラップ ポインターが特定のオペレーティング システム関数に渡されています。</span><span class="sxs-lookup"><span data-stu-id="5047f-110">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="5047f-111">この MDA が追跡する関数を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="5047f-111">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="5047f-112">モジュール</span><span class="sxs-lookup"><span data-stu-id="5047f-112">Module</span></span>|<span data-ttu-id="5047f-113">関数</span><span class="sxs-lookup"><span data-stu-id="5047f-113">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="5047f-114">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-114">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="5047f-115">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-115">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="5047f-116">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-116">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="5047f-117">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-117">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="5047f-118">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-118">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="5047f-119">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-119">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="5047f-120">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-120">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="5047f-121">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-121">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="5047f-122">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-122">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="5047f-123">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-123">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="5047f-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-124">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="5047f-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-125">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="5047f-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-126">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="5047f-127">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="5047f-127">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="5047f-128">呼び出しを行う <xref:System.AppDomain> がアンロードされる可能性があるため、この条件ではヒープが破損する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="5047f-128">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="5047f-129"><xref:System.AppDomain> がアンロードされると、アプリケーション コードがオーバーラップ ポインター用メモリを解放するため、操作終了時に破損が発生します。または、コードによってメモリ リークが発生し、後で問題となります。</span><span class="sxs-lookup"><span data-stu-id="5047f-129">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5047f-130">解決策</span><span class="sxs-lookup"><span data-stu-id="5047f-130">Resolution</span></span>  
 <span data-ttu-id="5047f-131"><xref:System.Threading.Overlapped> オブジェクトを使用して <xref:System.Threading.Overlapped.Pack%2A> メソッドを呼び出し、関数に渡すことができる <xref:System.Threading.NativeOverlapped> 構造体を取得します。</span><span class="sxs-lookup"><span data-stu-id="5047f-131">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="5047f-132"><xref:System.AppDomain> がアンロードされると、CLR は非同期操作が完了するのを待ってからポインターを解放します。</span><span class="sxs-lookup"><span data-stu-id="5047f-132">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5047f-133">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="5047f-133">Effect on the Runtime</span></span>  
 <span data-ttu-id="5047f-134">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="5047f-134">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5047f-135">出力</span><span class="sxs-lookup"><span data-stu-id="5047f-135">Output</span></span>  
 <span data-ttu-id="5047f-136">この MDA からの出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5047f-136">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="5047f-137">構成</span><span class="sxs-lookup"><span data-stu-id="5047f-137">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5047f-138">参照</span><span class="sxs-lookup"><span data-stu-id="5047f-138">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="5047f-139">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="5047f-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5047f-140">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="5047f-140">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
