---
title: ICorDebugArrayValue::GetElementAtPosition メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
ms.openlocfilehash: 10584442d7e0bd61e6decaf2b494dfe39f339d6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088413"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="d0862-102">ICorDebugArrayValue::GetElementAtPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="d0862-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="d0862-103">配列を0から始まる1次元配列として扱い、指定された位置にある要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="d0862-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0862-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0862-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0862-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0862-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="d0862-106">から取得する要素の位置。</span><span class="sxs-lookup"><span data-stu-id="d0862-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d0862-107">入出力要素の値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d0862-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0862-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0862-108">Remarks</span></span>  
 <span data-ttu-id="d0862-109">多次元配列のレイアウトは、配列レイアウトのスタイルC++に従います。</span><span class="sxs-lookup"><span data-stu-id="d0862-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0862-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="d0862-110">Requirements</span></span>  
 <span data-ttu-id="d0862-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0862-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0862-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0862-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0862-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0862-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0862-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0862-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
