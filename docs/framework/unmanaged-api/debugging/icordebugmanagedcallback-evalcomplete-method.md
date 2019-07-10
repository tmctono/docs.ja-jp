---
title: ICorDebugManagedCallback::EvalComplete メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a874646a6746a9b2fc8ce597e6c1ca47340c199a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759648"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="0d7f9-102">ICorDebugManagedCallback::EvalComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="0d7f9-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="0d7f9-103">評価が完了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0d7f9-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d7f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d7f9-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d7f9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d7f9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0d7f9-106">[in]評価が実行されたアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d7f9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0d7f9-107">[in]評価が実行されたスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d7f9-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="0d7f9-108">[in]評価を実行するコードを表す ICorDebugEval オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d7f9-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d7f9-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d7f9-109">Requirements</span></span>  
 <span data-ttu-id="0d7f9-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d7f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d7f9-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d7f9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d7f9-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d7f9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d7f9-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d7f9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7f9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d7f9-114">See also</span></span>

- [<span data-ttu-id="0d7f9-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d7f9-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
