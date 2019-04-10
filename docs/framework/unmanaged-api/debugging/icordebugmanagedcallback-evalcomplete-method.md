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
ms.openlocfilehash: c1261942865419762fa454eb8d4bc5e5d99e86d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193175"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="18e4c-102">ICorDebugManagedCallback::EvalComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="18e4c-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="18e4c-103">評価が完了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="18e4c-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e4c-104">構文</span><span class="sxs-lookup"><span data-stu-id="18e4c-104">Syntax</span></span>  
  
```  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18e4c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18e4c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="18e4c-106">[in]評価が実行されたアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="18e4c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="18e4c-107">[in]評価が実行されたスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="18e4c-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="18e4c-108">[in]評価を実行するコードを表す ICorDebugEval オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="18e4c-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18e4c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="18e4c-109">Requirements</span></span>  
 <span data-ttu-id="18e4c-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18e4c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18e4c-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18e4c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18e4c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18e4c-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="18e4c-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="18e4c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18e4c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="18e4c-114">See also</span></span>

- [<span data-ttu-id="18e4c-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18e4c-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
