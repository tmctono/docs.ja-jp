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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76100116f2ca3a9b9a99477ca2352d5fa1335ab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645683"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="b040a-102">ICorDebugArrayValue::GetElementAtPosition メソッド</span><span class="sxs-lookup"><span data-stu-id="b040a-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="b040a-103">0 から始まる 1 次元の配列として、配列を扱う方法の指定された位置に要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="b040a-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b040a-104">構文</span><span class="sxs-lookup"><span data-stu-id="b040a-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b040a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b040a-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="b040a-106">[in]取得する要素の位置。</span><span class="sxs-lookup"><span data-stu-id="b040a-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b040a-107">[out]要素の値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b040a-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b040a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b040a-108">Remarks</span></span>  
 <span data-ttu-id="b040a-109">多次元配列のレイアウトでは、C++ スタイルの配列のレイアウトに従います。</span><span class="sxs-lookup"><span data-stu-id="b040a-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b040a-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b040a-110">Requirements</span></span>  
 <span data-ttu-id="b040a-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b040a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b040a-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b040a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b040a-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b040a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b040a-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b040a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
