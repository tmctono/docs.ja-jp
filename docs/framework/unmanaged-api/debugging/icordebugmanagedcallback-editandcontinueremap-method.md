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
ms.openlocfilehash: 78b87b5c566b0d760a205757430123665fb2fcd3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213713"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="8d4d4-102">ICorDebugManagedCallback::EditAndContinueRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="8d4d4-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="8d4d4-103">このメソッドの使用は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="8d4d4-103">This method has been deprecated.</span></span> <span data-ttu-id="8d4d4-104">これは、マップイベントが統合開発環境 (IDE) に送信されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8d4d4-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d4d4-105">構文</span><span class="sxs-lookup"><span data-stu-id="8d4d4-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8d4d4-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d4d4-106">Remarks</span></span>  
 <span data-ttu-id="8d4d4-107">更新された `EditAndContinueRemap` 関数の古いバージョンでコードを実行しようとすると、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8d4d4-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="8d4d4-108">共通言語ランタイムは、メソッドを呼び出して、 `EditAndContinueRemap` リマップイベントを IDE に送信します。</span><span class="sxs-lookup"><span data-stu-id="8d4d4-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d4d4-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8d4d4-109">Requirements</span></span>  
 <span data-ttu-id="8d4d4-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d4d4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d4d4-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d4d4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d4d4-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d4d4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d4d4-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d4d4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d4d4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d4d4-114">See also</span></span>

- [<span data-ttu-id="8d4d4-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d4d4-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
