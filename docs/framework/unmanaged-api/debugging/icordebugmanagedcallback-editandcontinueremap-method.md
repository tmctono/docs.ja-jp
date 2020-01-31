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
ms.openlocfilehash: 9cb956c0262fdcdb5971d049ea7b057aa4d952c0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781901"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="2984a-102">ICorDebugManagedCallback::EditAndContinueRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="2984a-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="2984a-103">このメソッドの使用は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="2984a-103">This method has been deprecated.</span></span> <span data-ttu-id="2984a-104">これは、マップイベントが統合開発環境 (IDE) に送信されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2984a-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2984a-105">構文</span><span class="sxs-lookup"><span data-stu-id="2984a-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="2984a-106">コメント</span><span class="sxs-lookup"><span data-stu-id="2984a-106">Remarks</span></span>  
 <span data-ttu-id="2984a-107">`EditAndContinueRemap` メソッドは、更新された関数の古いバージョンでコードを実行しようとしたときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2984a-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="2984a-108">共通言語ランタイムは、`EditAndContinueRemap` メソッドを呼び出して、リマップイベントを IDE に送信します。</span><span class="sxs-lookup"><span data-stu-id="2984a-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2984a-109">要件</span><span class="sxs-lookup"><span data-stu-id="2984a-109">Requirements</span></span>  
 <span data-ttu-id="2984a-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2984a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2984a-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2984a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2984a-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2984a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2984a-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2984a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2984a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2984a-114">See also</span></span>

- [<span data-ttu-id="2984a-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2984a-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
