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
ms.openlocfilehash: 0aabff090634f1ecdeec5636336ad1fb77b8b81c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988924"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="1678a-102">ICorDebugEval2::RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="1678a-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="1678a-103">計算の中止この`ICorDebugEval2`は現在実行中です。</span><span class="sxs-lookup"><span data-stu-id="1678a-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1678a-104">構文</span><span class="sxs-lookup"><span data-stu-id="1678a-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1678a-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="1678a-105">Remarks</span></span>  
 <span data-ttu-id="1678a-106">`RudeAbort` 安全でない状態で、デバッグ セッションの外に出ているため、エバリュエーターを保持しているすべてのロックを解放しません。</span><span class="sxs-lookup"><span data-stu-id="1678a-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="1678a-107">十分注意してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1678a-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1678a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="1678a-108">Requirements</span></span>  
 <span data-ttu-id="1678a-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1678a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1678a-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1678a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1678a-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1678a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1678a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1678a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
