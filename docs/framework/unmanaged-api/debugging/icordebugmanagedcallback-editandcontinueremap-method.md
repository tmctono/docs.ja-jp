---
title: ICorDebugManagedCallback::EditAndContinueRemap メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 100688ece4ebb984d3d03823ab01bbaae7d395db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760274"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="8d872-102">ICorDebugManagedCallback::EditAndContinueRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="8d872-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="8d872-103">このメソッドの使用は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="8d872-103">This method has been deprecated.</span></span> <span data-ttu-id="8d872-104">統合開発環境 (IDE) に再割り当てイベントが送信されたことに、デバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8d872-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d872-105">構文</span><span class="sxs-lookup"><span data-stu-id="8d872-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8d872-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d872-106">Remarks</span></span>  
 <span data-ttu-id="8d872-107">`EditAndContinueRemap`更新済みの関数の古いバージョンのコードの実行が試行されたときに、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8d872-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="8d872-108">共通言語ランタイムの呼び出し、 `EditAndContinueRemap` IDE に再割り当てイベントを送信する方法。</span><span class="sxs-lookup"><span data-stu-id="8d872-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d872-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8d872-109">Requirements</span></span>  
 <span data-ttu-id="8d872-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d872-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d872-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d872-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d872-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d872-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d872-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d872-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d872-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d872-114">See also</span></span>

- [<span data-ttu-id="8d872-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d872-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
