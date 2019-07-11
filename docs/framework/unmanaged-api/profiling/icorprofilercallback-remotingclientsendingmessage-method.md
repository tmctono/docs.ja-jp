---
title: ICorProfilerCallback::RemotingClientSendingMessage メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4729a8d3ac2c6f7ec51a032a07ebfd1c2838cb9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782902"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="d7bde-102">ICorProfilerCallback::RemotingClientSendingMessage メソッド</span><span class="sxs-lookup"><span data-stu-id="d7bde-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="d7bde-103">クライアントがサーバーに要求を送信しているプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d7bde-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7bde-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7bde-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7bde-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7bde-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="d7bde-106">[in]指定された値に対応する値[icorprofilercallback::remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)これらの条件下で。</span><span class="sxs-lookup"><span data-stu-id="d7bde-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="d7bde-107">リモート処理の GUID の cookie はアクティブです。</span><span class="sxs-lookup"><span data-stu-id="d7bde-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="d7bde-108">チャネルは、メッセージの送信に成功します。</span><span class="sxs-lookup"><span data-stu-id="d7bde-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="d7bde-109">GUID の cookie は、サーバー側のプロセスでアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="d7bde-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="d7bde-110">これにより、リモート処理呼び出しと論理呼び出し履歴の作成のペアを容易にします。</span><span class="sxs-lookup"><span data-stu-id="d7bde-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="d7bde-111">[in]値が`true`呼び出しが非同期。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="d7bde-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7bde-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7bde-112">Requirements</span></span>  
 <span data-ttu-id="d7bde-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7bde-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7bde-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7bde-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7bde-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7bde-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7bde-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7bde-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7bde-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7bde-117">See also</span></span>

- [<span data-ttu-id="d7bde-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7bde-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
