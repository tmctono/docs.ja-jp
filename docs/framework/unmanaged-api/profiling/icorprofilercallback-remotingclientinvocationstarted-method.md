---
title: ICorProfilerCallback::RemotingClientInvocationStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1f73b36fc1e3a464155f390c25e956f9d706a73
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782937"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="37360-102">ICorProfilerCallback::RemotingClientInvocationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="37360-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="37360-103">リモート処理呼び出しが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="37360-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37360-104">構文</span><span class="sxs-lookup"><span data-stu-id="37360-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="37360-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="37360-105">Remarks</span></span>  
 <span data-ttu-id="37360-106">このイベントは、同期および非同期の呼び出しに同じです。</span><span class="sxs-lookup"><span data-stu-id="37360-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="37360-107">次のコールバックのペアのそれぞれについては、同じスレッドで発生します。</span><span class="sxs-lookup"><span data-stu-id="37360-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="37360-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="37360-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="37360-109">[Icorprofilercallback::remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)と[icorprofilercallback::remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="37360-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="37360-110">[Icorprofilercallback::remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)と[icorprofilercallback::remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="37360-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="37360-111">リモート処理のコールバックの次の問題を認識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37360-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="37360-112">クライアントから呼び出され、サーバー上で実行される関数の通知が正しく受信されていないために、リモート処理関数の実行は、プロファイラー API によって反映されません。</span><span class="sxs-lookup"><span data-stu-id="37360-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="37360-113">プロキシ オブジェクトによって行われ、実際の呼び出しプロファイラーを特定の関数でが JIT コンパイルしますが、使用されていないと表示されます。</span><span class="sxs-lookup"><span data-stu-id="37360-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="37360-114">プロファイラーは、非同期リモート処理イベントの正確な通知を受信しません。</span><span class="sxs-lookup"><span data-stu-id="37360-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37360-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="37360-115">Requirements</span></span>  
 <span data-ttu-id="37360-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37360-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37360-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37360-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37360-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37360-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37360-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37360-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37360-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="37360-120">See also</span></span>

- [<span data-ttu-id="37360-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37360-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
