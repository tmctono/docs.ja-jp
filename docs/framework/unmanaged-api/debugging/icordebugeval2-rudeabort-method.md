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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1adb79e5081fc909d0cd180d8161eccea7e58e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754354"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="372d0-102">ICorDebugEval2::RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="372d0-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="372d0-103">計算の中止この`ICorDebugEval2`は現在実行中です。</span><span class="sxs-lookup"><span data-stu-id="372d0-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="372d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="372d0-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="372d0-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="372d0-105">Remarks</span></span>  
 <span data-ttu-id="372d0-106">`RudeAbort` 安全でない状態で、デバッグ セッションの外に出ているため、エバリュエーターを保持しているすべてのロックを解放しません。</span><span class="sxs-lookup"><span data-stu-id="372d0-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="372d0-107">十分注意してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="372d0-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="372d0-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="372d0-108">Requirements</span></span>  
 <span data-ttu-id="372d0-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="372d0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="372d0-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="372d0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="372d0-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="372d0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="372d0-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="372d0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
