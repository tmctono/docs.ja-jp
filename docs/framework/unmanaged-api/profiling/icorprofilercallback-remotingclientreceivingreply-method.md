---
title: ICorProfilerCallback::RemotingClientReceivingReply メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
ms.openlocfilehash: e25cbfabc10da0c7b1095a956583bb5c7450dba9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445811"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="ae15b-102">ICorProfilerCallback::RemotingClientReceivingReply メソッド</span><span class="sxs-lookup"><span data-stu-id="ae15b-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="ae15b-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span><span class="sxs-lookup"><span data-stu-id="ae15b-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae15b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae15b-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ae15b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae15b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="ae15b-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span><span class="sxs-lookup"><span data-stu-id="ae15b-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="ae15b-107">Remoting GUID cookies are active.</span><span class="sxs-lookup"><span data-stu-id="ae15b-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="ae15b-108">The channel succeeds in transmitting the message.</span><span class="sxs-lookup"><span data-stu-id="ae15b-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="ae15b-109">GUID cookies are active on the server-side process.</span><span class="sxs-lookup"><span data-stu-id="ae15b-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="ae15b-110">This allows easy pairing of remoting calls.</span><span class="sxs-lookup"><span data-stu-id="ae15b-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ae15b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span><span class="sxs-lookup"><span data-stu-id="ae15b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae15b-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="ae15b-112">Requirements</span></span>  
 <span data-ttu-id="ae15b-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae15b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae15b-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae15b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae15b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae15b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae15b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae15b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae15b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae15b-117">See also</span></span>

- [<span data-ttu-id="ae15b-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae15b-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
