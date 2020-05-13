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
ms.openlocfilehash: 714819504099ea978ed31d471b4ceb9fc17a6552
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212296"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="701d2-102">ICorDebugModuleBreakpoint::GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="701d2-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="701d2-103">このブレークポイントが設定されているモジュールを参照する "ツールモジュール" へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="701d2-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="701d2-104">構文</span><span class="sxs-lookup"><span data-stu-id="701d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="701d2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="701d2-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="701d2-106">入出力`ICorDebugModule`ブレークポイントが設定されているモジュールを参照するインターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="701d2-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="701d2-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="701d2-107">Requirements</span></span>  
 <span data-ttu-id="701d2-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="701d2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="701d2-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="701d2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="701d2-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="701d2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="701d2-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="701d2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701d2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="701d2-112">See also</span></span>
