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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8e7fcb4f44d6bdf6f18c93b1046b549331621a4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470797"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="f6e5b-102">ICorDebugEval::GetResult メソッド</span><span class="sxs-lookup"><span data-stu-id="f6e5b-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="f6e5b-103">この評価の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f6e5b-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6e5b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6e5b-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6e5b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6e5b-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="f6e5b-106">[out]評価が正常に完了した場合は、この評価の結果を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f6e5b-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6e5b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6e5b-107">Remarks</span></span>  
 <span data-ttu-id="f6e5b-108">`GetResult`メソッドは、評価の完了後にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="f6e5b-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="f6e5b-109">通常、評価が完了すると`ppResult`結果を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6e5b-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="f6e5b-110">例外で終了した場合にスローされる例外になります。</span><span class="sxs-lookup"><span data-stu-id="f6e5b-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="f6e5b-111">新しいオブジェクトの場合、評価は、新しいオブジェクトへの参照になります。</span><span class="sxs-lookup"><span data-stu-id="f6e5b-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6e5b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6e5b-112">Requirements</span></span>  
 <span data-ttu-id="f6e5b-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6e5b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6e5b-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6e5b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6e5b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6e5b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6e5b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6e5b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
