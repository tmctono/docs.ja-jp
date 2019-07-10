---
title: ICorDebugModule::EnableClassLoadCallbacks メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec9b4867ad19f25e35ca31c007c0d238b949abab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762224"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="cb2cf-102">ICorDebugModule::EnableClassLoadCallbacks メソッド</span><span class="sxs-lookup"><span data-stu-id="cb2cf-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="cb2cf-103">コントロールかどうか、 [icordebugmanagedcallback::loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)と[icordebugmanagedcallback::unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)このモジュールのコールバックが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cb2cf-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb2cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="cb2cf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb2cf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb2cf-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="cb2cf-106">[in]この値に設定`true`共通言語ランタイム (CLR) に呼び出しを有効にする、`ICorDebugManagedCallback::LoadClass`と`ICorDebugManagedCallback::UnloadClass`メソッド、関連するイベントが発生するとします。</span><span class="sxs-lookup"><span data-stu-id="cb2cf-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="cb2cf-107">既定値は`false`非動的モジュール。</span><span class="sxs-lookup"><span data-stu-id="cb2cf-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="cb2cf-108">値は常に`true`動的モジュールを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cb2cf-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb2cf-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb2cf-109">Remarks</span></span>  
 <span data-ttu-id="cb2cf-110">`ICorDebugManagedCallback::LoadClass`と`ICorDebugManagedCallback::UnloadClass`コールバックは、動的モジュールが常に有効し、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb2cf-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb2cf-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb2cf-111">Requirements</span></span>  
 <span data-ttu-id="cb2cf-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb2cf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb2cf-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb2cf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb2cf-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb2cf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb2cf-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb2cf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2cf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb2cf-116">See also</span></span>
