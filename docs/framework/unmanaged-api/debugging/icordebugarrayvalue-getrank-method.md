---
title: ICorDebugArrayValue::GetRank メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abf24b81bae4d16c3a03aa668d4e1f5e8117cc93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737449"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="469dd-102">ICorDebugArrayValue::GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="469dd-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="469dd-103">配列のディメンションの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="469dd-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="469dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="469dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="469dd-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="469dd-106">[out]このディメンションの数へのポインター`ICorDebugArrayValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="469dd-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="469dd-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="469dd-107">Requirements</span></span>  
 <span data-ttu-id="469dd-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="469dd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="469dd-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="469dd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="469dd-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="469dd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="469dd-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="469dd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
