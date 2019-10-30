---
title: ICorDebugValueBreakpoint::GetValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
ms.openlocfilehash: 5924a3914c7fe04413b4a6744bce263b56165d78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140224"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="18c90-102">ICorDebugValueBreakpoint::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="18c90-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="18c90-103">ブレークポイントが設定されているオブジェクトの値を表す "ICorDebugValue" オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="18c90-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c90-104">構文</span><span class="sxs-lookup"><span data-stu-id="18c90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18c90-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18c90-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="18c90-106">入出力`ICorDebugValue` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="18c90-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18c90-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="18c90-107">Requirements</span></span>  
 <span data-ttu-id="18c90-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18c90-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18c90-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18c90-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18c90-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18c90-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18c90-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18c90-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c90-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="18c90-112">See also</span></span>
