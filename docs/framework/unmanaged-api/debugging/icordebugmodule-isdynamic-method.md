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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db5d07d2b9a295a5cd21b4d4af954503b8bd7a8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763661"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="3e056-102">ICorDebugModule::IsDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="3e056-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="3e056-103">このモジュールは動的であるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3e056-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e056-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e056-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e056-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e056-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="3e056-106">[out]`true`このモジュールは、動的。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="3e056-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e056-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e056-107">Remarks</span></span>  
 <span data-ttu-id="3e056-108">動的モジュールでは、新しいクラスを追加でき、モジュールが読み込まれた後も、既存のクラスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3e056-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="3e056-109">[Icordebugmanagedcallback::loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)と[icordebugmanagedcallback::unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)クラスが追加または削除されたときにコールバックをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3e056-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e056-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e056-110">Requirements</span></span>  
 <span data-ttu-id="3e056-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e056-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e056-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e056-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e056-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e056-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e056-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e056-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
