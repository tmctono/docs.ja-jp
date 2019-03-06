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
ms.openlocfilehash: fff5b25706353d999ab6875092e31f554438f28c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469158"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="a6169-102">ICorProfilerCallback::RemotingClientReceivingReply メソッド</span><span class="sxs-lookup"><span data-stu-id="a6169-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="a6169-103">リモート処理呼び出しのサーバー側の部分が完了し、クライアントが受け取るようになりましたことをプロファイラーに通知し、応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="a6169-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6169-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6169-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a6169-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6169-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="a6169-106">[in]指定された値に対応する値[icorprofilercallback::remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)これらの条件下で。</span><span class="sxs-lookup"><span data-stu-id="a6169-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="a6169-107">リモート処理の GUID の cookie はアクティブです。</span><span class="sxs-lookup"><span data-stu-id="a6169-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="a6169-108">チャネルは、メッセージの送信に成功します。</span><span class="sxs-lookup"><span data-stu-id="a6169-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="a6169-109">GUID の cookie は、サーバー側のプロセスでアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="a6169-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="a6169-110">これにより、リモート処理呼び出しのペアを容易にします。</span><span class="sxs-lookup"><span data-stu-id="a6169-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="a6169-111">[in]値が`true`呼び出しが非同期。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="a6169-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6169-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a6169-112">Requirements</span></span>  
 <span data-ttu-id="a6169-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6169-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6169-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6169-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6169-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6169-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6169-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6169-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6169-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6169-117">See also</span></span>
- [<span data-ttu-id="a6169-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6169-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
