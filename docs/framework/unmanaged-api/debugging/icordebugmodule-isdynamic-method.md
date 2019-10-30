---
title: ICorDebugModule::IsDynamic メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 5774b40178ce0d7c2ef5d063a37b9011fc2630df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127943"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="0f7fd-102">ICorDebugModule::IsDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="0f7fd-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="0f7fd-103">このモジュールが動的かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f7fd-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f7fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f7fd-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f7fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f7fd-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="0f7fd-106">[out] このモジュールが動的である場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="0f7fd-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f7fd-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f7fd-107">Remarks</span></span>  
 <span data-ttu-id="0f7fd-108">動的モジュールは、モジュールが読み込まれた後でも、新しいクラスを追加したり、既存のクラスを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="0f7fd-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="0f7fd-109">は、クラスが追加または削除されたときに、 [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) [Callback:: loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)コールバックとによって、デバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0f7fd-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f7fd-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="0f7fd-110">Requirements</span></span>  
 <span data-ttu-id="0f7fd-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f7fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f7fd-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f7fd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f7fd-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f7fd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f7fd-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f7fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
