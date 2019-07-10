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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639b34093e79933b4daaa0e3ae5223f1a1a51bf6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773784"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="9adeb-102">ICorDebugValueBreakpoint::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="9adeb-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="9adeb-103">ブレークポイントが設定されているオブジェクトの値を表す"ICorDebugValue"オブジェクトへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9adeb-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9adeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="9adeb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9adeb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9adeb-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="9adeb-106">[out]アドレスへのポインター、`ICorDebugValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9adeb-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9adeb-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="9adeb-107">Requirements</span></span>  
 <span data-ttu-id="9adeb-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9adeb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9adeb-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9adeb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9adeb-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9adeb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9adeb-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9adeb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9adeb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9adeb-112">See also</span></span>
