---
title: ICorDebugArrayValue::GetCount メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetCount
helpviewer_keywords:
- ICorDebugArrayValue::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 44cd98cf-2127-4d46-8c6a-da4e857bb6b0
topic_type:
- apiref
ms.openlocfilehash: f33225eae4b62f2d5f0793212ae7dcc70e97f508
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088529"
---
# <a name="icordebugarrayvaluegetcount-method"></a><span data-ttu-id="bc644-102">ICorDebugArrayValue::GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="bc644-102">ICorDebugArrayValue::GetCount Method</span></span>
<span data-ttu-id="bc644-103">配列内の要素の合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc644-103">Gets the total number of elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc644-104">構文</span><span class="sxs-lookup"><span data-stu-id="bc644-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG32 *pnCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc644-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc644-105">Parameters</span></span>  
 `pnCount`  
 <span data-ttu-id="bc644-106">入出力配列内の要素の合計数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bc644-106">[out] A pointer to the total number of elements in the array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc644-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="bc644-107">Requirements</span></span>  
 <span data-ttu-id="bc644-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc644-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc644-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc644-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc644-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc644-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc644-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc644-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
