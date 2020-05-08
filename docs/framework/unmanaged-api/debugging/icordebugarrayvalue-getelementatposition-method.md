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
ms.openlocfilehash: 5644c20ec5df2606c7258131573691997f424e50
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895020"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="c6285-102">ICorDebugArrayValue::GetElementAtPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="c6285-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="c6285-103">配列を0から始まる1次元配列として扱い、指定された位置にある要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="c6285-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6285-104">構文</span><span class="sxs-lookup"><span data-stu-id="c6285-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6285-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6285-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="c6285-106">から取得する要素の位置。</span><span class="sxs-lookup"><span data-stu-id="c6285-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c6285-107">入出力要素の値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c6285-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6285-108">解説</span><span class="sxs-lookup"><span data-stu-id="c6285-108">Remarks</span></span>  
 <span data-ttu-id="c6285-109">多次元配列のレイアウトは、C++ スタイルの配列レイアウトに従います。</span><span class="sxs-lookup"><span data-stu-id="c6285-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6285-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6285-110">Requirements</span></span>  
 <span data-ttu-id="c6285-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6285-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6285-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6285-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6285-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6285-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6285-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6285-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
