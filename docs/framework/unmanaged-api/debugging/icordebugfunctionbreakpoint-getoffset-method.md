---
title: ICorDebugFunctionBreakpoint::GetOffset メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67e71002a78023ad6e8ef89c7a57d484a65aaeb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756385"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="d8d77-102">ICorDebugFunctionBreakpoint::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="d8d77-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="d8d77-103">関数内でのブレークポイントのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8d77-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d77-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8d77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8d77-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8d77-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="d8d77-106">[out]ブレークポイントのオフセットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d8d77-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d77-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="d8d77-107">Requirements</span></span>  
 <span data-ttu-id="d8d77-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8d77-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d77-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8d77-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8d77-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8d77-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8d77-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d77-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
