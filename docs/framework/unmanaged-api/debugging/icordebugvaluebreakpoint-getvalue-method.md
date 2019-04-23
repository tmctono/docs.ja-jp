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
ms.openlocfilehash: acdfddd015013215bba9039d871837a60ead1405
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175093"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="fcb69-102">ICorDebugValueBreakpoint::GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="fcb69-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="fcb69-103">ブレークポイントが設定されているオブジェクトの値を表す"ICorDebugValue"オブジェクトへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="fcb69-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb69-104">構文</span><span class="sxs-lookup"><span data-stu-id="fcb69-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcb69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcb69-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="fcb69-106">[out]アドレスへのポインター、`ICorDebugValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fcb69-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcb69-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="fcb69-107">Requirements</span></span>  
 <span data-ttu-id="fcb69-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcb69-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcb69-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcb69-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcb69-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcb69-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcb69-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcb69-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb69-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcb69-112">See also</span></span>
