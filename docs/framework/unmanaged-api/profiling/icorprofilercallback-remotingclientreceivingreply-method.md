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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2134a7f12ac482b3fe79ac722684ac8601a7280b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662917"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="33797-102">ICorProfilerCallback::RemotingClientReceivingReply メソッド</span><span class="sxs-lookup"><span data-stu-id="33797-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="33797-103">リモート処理呼び出しのサーバー側の部分が完了し、クライアントが受け取るようになりましたことをプロファイラーに通知し、応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="33797-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33797-104">構文</span><span class="sxs-lookup"><span data-stu-id="33797-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="33797-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="33797-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="33797-106">[in]指定された値に対応する値[icorprofilercallback::remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)これらの条件下で。</span><span class="sxs-lookup"><span data-stu-id="33797-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="33797-107">リモート処理の GUID の cookie はアクティブです。</span><span class="sxs-lookup"><span data-stu-id="33797-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="33797-108">チャネルは、メッセージの送信に成功します。</span><span class="sxs-lookup"><span data-stu-id="33797-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="33797-109">GUID の cookie は、サーバー側のプロセスでアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="33797-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="33797-110">これにより、リモート処理呼び出しのペアを容易にします。</span><span class="sxs-lookup"><span data-stu-id="33797-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="33797-111">[in]値が`true`呼び出しが非同期。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="33797-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33797-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="33797-112">Requirements</span></span>  
 <span data-ttu-id="33797-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33797-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33797-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33797-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33797-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33797-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33797-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33797-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33797-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="33797-117">See also</span></span>

- [<span data-ttu-id="33797-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33797-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
