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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 300baeb4184bbb73704563671ab907fafbdb5284
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472630"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="67117-102">ICorDebugManagedCallback2::CreateConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="67117-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="67117-103">新しい接続が作成されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="67117-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67117-104">構文</span><span class="sxs-lookup"><span data-stu-id="67117-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67117-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67117-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="67117-106">[in]接続が作成されたプロセスを表す"ICorDebugProcess"オブジェクトへのポインター</span><span class="sxs-lookup"><span data-stu-id="67117-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="67117-107">[in]新しい接続の ID。</span><span class="sxs-lookup"><span data-stu-id="67117-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="67117-108">[in]新しい接続の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="67117-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67117-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="67117-109">Remarks</span></span>  
 <span data-ttu-id="67117-110">A`CreateConnection`コールバックは、次の場合のいずれかで発生します。</span><span class="sxs-lookup"><span data-stu-id="67117-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="67117-111">ときに、デバッガーは、接続を含むプロセスにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="67117-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="67117-112">ランタイムの生成し、ディスパッチここを`CreateConnection`イベントと[icordebugmanagedcallback 2::changeconnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)プロセス内の各接続のイベント。</span><span class="sxs-lookup"><span data-stu-id="67117-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="67117-113">ホストが呼び出したときに[iclrdebugmanager::beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)で、[ホスト API](../../../../docs/framework/unmanaged-api/hosting/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="67117-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67117-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="67117-114">Requirements</span></span>  
 <span data-ttu-id="67117-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67117-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67117-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67117-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67117-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67117-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67117-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67117-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67117-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="67117-119">See also</span></span>
- [<span data-ttu-id="67117-120">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67117-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="67117-121">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67117-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
