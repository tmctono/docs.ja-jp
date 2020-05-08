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
ms.openlocfilehash: e6401731844f2ce7a1d9fec1c94019f763870fe7
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894994"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="fdc95-102">ICorDebugArrayValue::GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="fdc95-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="fdc95-103">配列のディメンションの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="fdc95-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc95-104">構文</span><span class="sxs-lookup"><span data-stu-id="fdc95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdc95-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdc95-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="fdc95-106">入出力この`ICorDebugArrayValue`オブジェクトの次元数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fdc95-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc95-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="fdc95-107">Requirements</span></span>  
 <span data-ttu-id="fdc95-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdc95-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdc95-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdc95-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdc95-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdc95-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdc95-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc95-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
