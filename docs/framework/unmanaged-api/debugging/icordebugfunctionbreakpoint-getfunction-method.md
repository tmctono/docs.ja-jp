---
title: ICorDebugFunctionBreakpoint::GetFunction メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1da93ea073d6ae9f2e79f251014b2db5282a22c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496015"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="ad62b-102">ICorDebugFunctionBreakpoint::GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="ad62b-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="ad62b-103">ブレークポイントが設定されている関数を参照する、ICorDebugFunction にインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad62b-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad62b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad62b-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad62b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad62b-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="ad62b-106">[out]ブレークポイントが設定されている関数のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad62b-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad62b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad62b-107">Requirements</span></span>  
 <span data-ttu-id="ad62b-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad62b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad62b-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad62b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad62b-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad62b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad62b-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad62b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
