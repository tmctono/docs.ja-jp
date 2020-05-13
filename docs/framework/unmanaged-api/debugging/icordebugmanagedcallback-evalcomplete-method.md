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
ms.openlocfilehash: 0431b54997c9889e2b3206392e86e4dcde45ffb3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212452"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="2e998-102">ICorDebugManagedCallback::EvalComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="2e998-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="2e998-103">評価が完了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2e998-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e998-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e998-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e998-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e998-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2e998-106">から評価が実行されたアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2e998-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2e998-107">から評価が実行されたスレッドを表す、スレッドオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2e998-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="2e998-108">から評価を実行したコードを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2e998-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e998-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2e998-109">Requirements</span></span>  
 <span data-ttu-id="2e998-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e998-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e998-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e998-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e998-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e998-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e998-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e998-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e998-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e998-114">See also</span></span>

- [<span data-ttu-id="2e998-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e998-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
