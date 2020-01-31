---
title: ICorProfilerCallback::RemotingServerReceivingMessage メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
ms.openlocfilehash: 6e045a99de9ad30516fd12a7b490e26c860bde7e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866014"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="eb5fd-102">ICorProfilerCallback::RemotingServerReceivingMessage メソッド</span><span class="sxs-lookup"><span data-stu-id="eb5fd-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="eb5fd-103">プロセスがリモートメソッド呼び出しまたはアクティベーション要求を受信したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb5fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb5fd-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb5fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb5fd-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="eb5fd-106">から次の条件下で[ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)で指定された値に対応する値。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="eb5fd-107">リモート処理 GUID クッキーはアクティブです。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="eb5fd-108">チャネルは、メッセージの送信に成功します。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="eb5fd-109">GUID cookie は、クライアント側のプロセスでアクティブです。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="eb5fd-110">これにより、リモート処理呼び出しと論理呼び出し履歴の作成を簡単に組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="eb5fd-111">から呼び出しが非同期の場合に `true` される値。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb5fd-112">コメント</span><span class="sxs-lookup"><span data-stu-id="eb5fd-112">Remarks</span></span>  
 <span data-ttu-id="eb5fd-113">メッセージ要求が非同期の場合は、任意のスレッドで要求を処理できます。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb5fd-114">要件</span><span class="sxs-lookup"><span data-stu-id="eb5fd-114">Requirements</span></span>  
 <span data-ttu-id="eb5fd-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb5fd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb5fd-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb5fd-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb5fd-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb5fd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb5fd-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb5fd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5fd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb5fd-119">See also</span></span>

- [<span data-ttu-id="eb5fd-120">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb5fd-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
