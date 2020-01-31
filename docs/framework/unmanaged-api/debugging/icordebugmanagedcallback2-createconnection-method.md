---
title: ICorDebugManagedCallback2::CreateConnection メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: e98748b523b948dc002f2ebc4e2e79fc7d659918
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781588"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="17504-102">ICorDebugManagedCallback2::CreateConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="17504-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="17504-103">新しい接続が作成されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="17504-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17504-104">構文</span><span class="sxs-lookup"><span data-stu-id="17504-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17504-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="17504-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="17504-106">から接続が作成されたプロセスを表す "いいプロセス" オブジェクトへのポインター</span><span class="sxs-lookup"><span data-stu-id="17504-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="17504-107">から新しい接続の ID。</span><span class="sxs-lookup"><span data-stu-id="17504-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="17504-108">から新しい接続の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="17504-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17504-109">コメント</span><span class="sxs-lookup"><span data-stu-id="17504-109">Remarks</span></span>  
 <span data-ttu-id="17504-110">`CreateConnection` コールバックは、次のいずれかの場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="17504-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="17504-111">デバッガーが接続を含むプロセスにアタッチする場合。</span><span class="sxs-lookup"><span data-stu-id="17504-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="17504-112">この場合、ランタイムは、プロセス内の各接続に対して、`CreateConnection` イベントと[ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md)イベントを生成してディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="17504-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="17504-113">ホストが[ホスティング API](../../../../docs/framework/unmanaged-api/hosting/index.md)で[ICLRDebugManager:: beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)を呼び出すとき。</span><span class="sxs-lookup"><span data-stu-id="17504-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17504-114">要件</span><span class="sxs-lookup"><span data-stu-id="17504-114">Requirements</span></span>  
 <span data-ttu-id="17504-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17504-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17504-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17504-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17504-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17504-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17504-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17504-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17504-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="17504-119">See also</span></span>

- [<span data-ttu-id="17504-120">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="17504-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="17504-121">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="17504-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
