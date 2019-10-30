---
title: ICorDebugModuleBreakpoint::GetModule メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: 6f9d8cd79ac4107817d19fc0632aeaee287d253a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097014"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="b3df7-102">ICorDebugModuleBreakpoint::GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="b3df7-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="b3df7-103">このブレークポイントが設定されているモジュールを参照する "ツールモジュール" へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3df7-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3df7-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3df7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3df7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3df7-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="b3df7-106">入出力ブレークポイントが設定されているモジュールを参照する `ICorDebugModule` インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b3df7-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3df7-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="b3df7-107">Requirements</span></span>  
 <span data-ttu-id="b3df7-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3df7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3df7-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3df7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3df7-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3df7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3df7-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3df7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3df7-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3df7-112">See also</span></span>
