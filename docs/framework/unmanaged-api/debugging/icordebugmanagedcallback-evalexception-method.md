---
title: ICorDebugManagedCallback::EvalException メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 602bcd12d1fd4c5806de6db81252731baa447b7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120017"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="3897e-102">ICorDebugManagedCallback::EvalException メソッド</span><span class="sxs-lookup"><span data-stu-id="3897e-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="3897e-103">ハンドルされない例外で、評価が終了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3897e-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3897e-104">構文</span><span class="sxs-lookup"><span data-stu-id="3897e-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3897e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3897e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3897e-106">[in]評価が終了したアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3897e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3897e-107">[in]評価が終了したスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3897e-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="3897e-108">[in]評価を実行するコードを表す ICorDebugEval オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3897e-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3897e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3897e-109">Requirements</span></span>  
 <span data-ttu-id="3897e-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3897e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3897e-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3897e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3897e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3897e-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3897e-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3897e-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3897e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3897e-114">See also</span></span>

- [<span data-ttu-id="3897e-115">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3897e-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
