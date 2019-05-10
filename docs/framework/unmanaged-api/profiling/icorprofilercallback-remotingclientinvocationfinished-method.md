---
title: ICorProfilerCallback::RemotingClientInvocationFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c3f7c30518184be70c85ff096915738b1633a01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603222"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="5c6dc-102">ICorProfilerCallback::RemotingClientInvocationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="5c6dc-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="5c6dc-103">クライアントで、リモート処理呼び出しが完了するまで実行をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6dc-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c6dc-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5c6dc-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c6dc-105">Remarks</span></span>  
 <span data-ttu-id="5c6dc-106">リモート処理呼び出しが同期する場合、これも実行が完了、サーバー上。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="5c6dc-107">非同期リモート処理呼び出しの場合、呼び出しを処理するときの応答もことが予想されます。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="5c6dc-108">呼び出しとして発生するが、応答が予想される場合[icorprofilercallback::remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)への呼び出しを追加および`RemotingClientInvocationFinished`を非同期呼び出しの必要なセカンダリの処理を示します。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="5c6dc-109">次のコールバックのペアのそれぞれについては、同じスレッドで発生します。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="5c6dc-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="5c6dc-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="5c6dc-111">[Icorprofilercallback::remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)と[icorprofilercallback::remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="5c6dc-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="5c6dc-112">[Icorprofilercallback::remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)と[icorprofilercallback::remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="5c6dc-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="5c6dc-113">リモート処理のコールバックの次の問題を認識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="5c6dc-114">クライアントから呼び出され、サーバー上で実行される関数の通知が正しく受信されていないために、リモート処理関数の実行は、プロファイラー API によって反映されません。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="5c6dc-115">プロキシ オブジェクトによって行われ、実際の呼び出しプロファイラーを特定の関数でが JIT コンパイルしますが、使用されていないと表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="5c6dc-116">プロファイラーは、非同期リモート処理イベントの正確な通知を受信しません。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c6dc-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="5c6dc-117">Requirements</span></span>  
 <span data-ttu-id="5c6dc-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c6dc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6dc-119">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c6dc-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c6dc-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c6dc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c6dc-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6dc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6dc-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c6dc-122">See also</span></span>

- [<span data-ttu-id="5c6dc-123">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c6dc-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
