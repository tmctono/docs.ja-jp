---
title: ICorDebugEval::GetResult メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 52bfe669d3b078657916554255a11cecfc07d484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085087"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="ddd43-102">ICorDebugEval::GetResult メソッド</span><span class="sxs-lookup"><span data-stu-id="ddd43-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="ddd43-103">この評価の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="ddd43-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd43-104">構文</span><span class="sxs-lookup"><span data-stu-id="ddd43-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddd43-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ddd43-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="ddd43-106">入出力評価が正常に完了した場合に、この評価の結果を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ddd43-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddd43-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ddd43-107">Remarks</span></span>  
 <span data-ttu-id="ddd43-108">`GetResult` メソッドは、評価が完了した後にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ddd43-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="ddd43-109">評価が正常に完了した場合、`ppResult` によって結果が指定されます。</span><span class="sxs-lookup"><span data-stu-id="ddd43-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="ddd43-110">例外が発生して終了した場合は、スローされた例外が結果になります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="ddd43-111">新しいオブジェクトの評価がの場合、結果は新しいオブジェクトへの参照になります。</span><span class="sxs-lookup"><span data-stu-id="ddd43-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd43-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="ddd43-112">Requirements</span></span>  
 <span data-ttu-id="ddd43-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddd43-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd43-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddd43-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddd43-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddd43-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddd43-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd43-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
