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
ms.openlocfilehash: 61a36ff23bf9deac25983f06387b2bbbfd49546b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041900"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="25481-102">ICorProfilerCallback::RemotingClientSendingMessage メソッド</span><span class="sxs-lookup"><span data-stu-id="25481-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="25481-103">クライアントがサーバーに要求を送信しているプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="25481-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25481-104">構文</span><span class="sxs-lookup"><span data-stu-id="25481-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25481-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25481-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="25481-106">[in]指定された値に対応する値[icorprofilercallback::remotingserverreceivingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)これらの条件下で。</span><span class="sxs-lookup"><span data-stu-id="25481-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="25481-107">リモート処理の GUID の cookie はアクティブです。</span><span class="sxs-lookup"><span data-stu-id="25481-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="25481-108">チャネルは、メッセージの送信に成功します。</span><span class="sxs-lookup"><span data-stu-id="25481-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="25481-109">GUID の cookie は、サーバー側のプロセスでアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="25481-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="25481-110">これにより、リモート処理呼び出しと論理呼び出し履歴の作成のペアを容易にします。</span><span class="sxs-lookup"><span data-stu-id="25481-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="25481-111">[in]値が`true`呼び出しが非同期。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="25481-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25481-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="25481-112">Requirements</span></span>  
 <span data-ttu-id="25481-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25481-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25481-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25481-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25481-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25481-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25481-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25481-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25481-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="25481-117">See also</span></span>

- [<span data-ttu-id="25481-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="25481-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
