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
ms.openlocfilehash: 51d34e68851bc6a60d25f643f63d112396abdc4e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209072"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="84308-102">ICorDebugManagedCallback2::CreateConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="84308-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="84308-103">新しい接続が作成されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="84308-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84308-104">構文</span><span class="sxs-lookup"><span data-stu-id="84308-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84308-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84308-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="84308-106">から接続が作成されたプロセスを表す "いいプロセス" オブジェクトへのポインター</span><span class="sxs-lookup"><span data-stu-id="84308-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="84308-107">から新しい接続の ID。</span><span class="sxs-lookup"><span data-stu-id="84308-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="84308-108">から新しい接続の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="84308-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84308-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="84308-109">Remarks</span></span>  
 <span data-ttu-id="84308-110">`CreateConnection`コールバックは、次のいずれかの場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="84308-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="84308-111">デバッガーが接続を含むプロセスにアタッチする場合。</span><span class="sxs-lookup"><span data-stu-id="84308-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="84308-112">この場合、ランタイムは、 `CreateConnection` プロセス内の各接続に対して、イベントと、 [ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md)イベントを生成してディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="84308-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="84308-113">ホストが[ホスティング API](../hosting/index.md)で[ICLRDebugManager:: beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)を呼び出すとき。</span><span class="sxs-lookup"><span data-stu-id="84308-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84308-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="84308-114">Requirements</span></span>  
 <span data-ttu-id="84308-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84308-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84308-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84308-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84308-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84308-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84308-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84308-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84308-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="84308-119">See also</span></span>

- [<span data-ttu-id="84308-120">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84308-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="84308-121">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84308-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
