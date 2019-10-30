---
title: ICorDebug::SetUnmanagedHandler メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134045"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="4cfcb-102">ICorDebug::SetUnmanagedHandler メソッド</span><span class="sxs-lookup"><span data-stu-id="4cfcb-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="4cfcb-103">アンマネージイベントのイベントハンドラーオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cfcb-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cfcb-104">構文</span><span class="sxs-lookup"><span data-stu-id="4cfcb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cfcb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cfcb-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="4cfcb-106">からアンマネージイベントのイベントハンドラーを表す[ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4cfcb-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cfcb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4cfcb-107">Remarks</span></span>  
 <span data-ttu-id="4cfcb-108">アンマネージイベントのイベントハンドラーオブジェクトは、 [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)の呼び出しの後、 [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)または[ICorDebug::D e](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)の呼び出しの前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cfcb-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="4cfcb-109">ただし、従来の目的では、最初のネイティブデバッグイベントが発生するまで、アンマネージイベントのイベントハンドラーオブジェクトを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4cfcb-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="4cfcb-110">具体的には、`ICorDebug::CreateProcess` で CREATE_SUSPENDED フラグが設定されている場合、メインスレッドが再開されるまでネイティブデバッグイベントをディスパッチできません。</span><span class="sxs-lookup"><span data-stu-id="4cfcb-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cfcb-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="4cfcb-111">Requirements</span></span>  
 <span data-ttu-id="4cfcb-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cfcb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cfcb-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cfcb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cfcb-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cfcb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cfcb-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cfcb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfcb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4cfcb-116">See also</span></span>

- [<span data-ttu-id="4cfcb-117">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4cfcb-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
