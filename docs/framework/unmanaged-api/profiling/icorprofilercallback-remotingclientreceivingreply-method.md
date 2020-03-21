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
ms.openlocfilehash: f7a943627e2087e6b8c78ced9fc32824843d44fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175136"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="261ea-102">ICorProfilerCallback::RemotingClientReceivingReply メソッド</span><span class="sxs-lookup"><span data-stu-id="261ea-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="261ea-103">リモート処理呼び出しのサーバー側部分が完了し、クライアントが現在受信中であり、応答を処理しようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="261ea-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="261ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="261ea-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="261ea-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="261ea-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="261ea-106">[in]次の条件の下で提供される値に対応[する](icorprofilercallback-remotingserversendingreply-method.md)値:</span><span class="sxs-lookup"><span data-stu-id="261ea-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="261ea-107">リモート処理 GUID クッキーがアクティブです。</span><span class="sxs-lookup"><span data-stu-id="261ea-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="261ea-108">チャネルはメッセージの送信に成功します。</span><span class="sxs-lookup"><span data-stu-id="261ea-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="261ea-109">GUID クッキーはサーバー側のプロセスでアクティブです。</span><span class="sxs-lookup"><span data-stu-id="261ea-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="261ea-110">これにより、リモート処理呼び出しの組み合わせが簡単に行えます。</span><span class="sxs-lookup"><span data-stu-id="261ea-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="261ea-111">[in]呼び出し`true`が非同期である場合の値。それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="261ea-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="261ea-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="261ea-112">Requirements</span></span>  
 <span data-ttu-id="261ea-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="261ea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="261ea-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="261ea-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="261ea-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="261ea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="261ea-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="261ea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="261ea-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="261ea-117">See also</span></span>

- [<span data-ttu-id="261ea-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="261ea-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
