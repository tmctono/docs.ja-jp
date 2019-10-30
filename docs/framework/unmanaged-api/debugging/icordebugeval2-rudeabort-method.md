---
title: ICorDebugEval2::RudeAbort メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
ms.openlocfilehash: a486935d5d53a6fc7d862160ed1186c5774814c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084795"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="c2bb2-102">ICorDebugEval2::RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="c2bb2-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="c2bb2-103">この `ICorDebugEval2` が現在実行している計算を中止します。</span><span class="sxs-lookup"><span data-stu-id="c2bb2-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2bb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2bb2-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c2bb2-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2bb2-105">Remarks</span></span>  
 <span data-ttu-id="c2bb2-106">`RudeAbort` は、エバリュエーターに保持されているロックを解放しません。そのため、デバッグセッションは安全ではない状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="c2bb2-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="c2bb2-107">このメソッドは細心の注意を払って呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="c2bb2-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2bb2-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="c2bb2-108">Requirements</span></span>  
 <span data-ttu-id="c2bb2-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2bb2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2bb2-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2bb2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2bb2-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2bb2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2bb2-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2bb2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
