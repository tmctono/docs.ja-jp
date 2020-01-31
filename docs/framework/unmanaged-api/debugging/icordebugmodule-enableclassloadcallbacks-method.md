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
ms.openlocfilehash: d552b694787b5d9f0d5adc399eda6f75df93c385
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793021"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="c48b2-102">ICorDebugModule::EnableClassLoadCallbacks メソッド</span><span class="sxs-lookup"><span data-stu-id="c48b2-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="c48b2-103">このモジュールに対して、" [UnloadClass](icordebugmanagedcallback-unloadclass-method.md) " コール[バック:: loadclass](icordebugmanagedcallback-loadclass-method.md)との各コールバックを呼び出すかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c48b2-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c48b2-104">構文</span><span class="sxs-lookup"><span data-stu-id="c48b2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c48b2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c48b2-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="c48b2-106">からこの値を `true` に設定すると、共通言語ランタイム (CLR) が、関連付けられたイベントが発生したときに `ICorDebugManagedCallback::LoadClass` および `ICorDebugManagedCallback::UnloadClass` メソッドを呼び出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="c48b2-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="c48b2-107">既定値は、非動的モジュールの場合は `false` です。</span><span class="sxs-lookup"><span data-stu-id="c48b2-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="c48b2-108">動的モジュールの値は常に `true`、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c48b2-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c48b2-109">コメント</span><span class="sxs-lookup"><span data-stu-id="c48b2-109">Remarks</span></span>  
 <span data-ttu-id="c48b2-110">`ICorDebugManagedCallback::LoadClass` と `ICorDebugManagedCallback::UnloadClass` のコールバックは動的モジュールに対して常に有効であり、無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c48b2-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c48b2-111">要件</span><span class="sxs-lookup"><span data-stu-id="c48b2-111">Requirements</span></span>  
 <span data-ttu-id="c48b2-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c48b2-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c48b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c48b2-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c48b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c48b2-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c48b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c48b2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c48b2-116">See also</span></span>
