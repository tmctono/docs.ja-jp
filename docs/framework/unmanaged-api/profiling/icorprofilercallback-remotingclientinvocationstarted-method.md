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
ms.openlocfilehash: 5de291774f1e20b4c399c416f9f52657fa8a9a84
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445828"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="ad333-102">ICorProfilerCallback::RemotingClientInvocationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="ad333-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="ad333-103">リモート処理呼び出しが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ad333-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad333-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad333-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ad333-105">コメント</span><span class="sxs-lookup"><span data-stu-id="ad333-105">Remarks</span></span>  
 <span data-ttu-id="ad333-106">このイベントは、同期呼び出しと非同期呼び出しで同じです。</span><span class="sxs-lookup"><span data-stu-id="ad333-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="ad333-107">次のコールバックの各ペアは、同じスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ad333-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="ad333-108">`RemotingClientInvocationStarted` と[ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="ad333-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="ad333-109">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)と[ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="ad333-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="ad333-110">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)と[ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="ad333-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="ad333-111">リモート処理のコールバックでは、次の問題に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad333-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="ad333-112">リモート処理関数の実行はプロファイラー API によっては反映されないため、クライアントから呼び出され、サーバーで実行される関数の通知は正しく受信されません。</span><span class="sxs-lookup"><span data-stu-id="ad333-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="ad333-113">実際の呼び出しは、プロキシオブジェクトを介して行われます。プロファイラーには、特定の関数が JIT コンパイルされていても使用されていないように見えます。</span><span class="sxs-lookup"><span data-stu-id="ad333-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="ad333-114">プロファイラーは、非同期のリモート処理イベントに対して正確な通知を受信しません。</span><span class="sxs-lookup"><span data-stu-id="ad333-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad333-115">要件</span><span class="sxs-lookup"><span data-stu-id="ad333-115">Requirements</span></span>  
 <span data-ttu-id="ad333-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad333-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad333-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad333-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad333-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad333-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad333-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad333-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad333-120">参照</span><span class="sxs-lookup"><span data-stu-id="ad333-120">See also</span></span>

- [<span data-ttu-id="ad333-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad333-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
