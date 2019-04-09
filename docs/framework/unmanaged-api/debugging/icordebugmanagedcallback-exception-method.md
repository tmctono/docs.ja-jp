---
title: ICorDebugManagedCallback::Exception メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91318ea596cc7d6c8a747901fea2749a64aa2623
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168117"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="1c73c-102">ICorDebugManagedCallback::Exception メソッド</span><span class="sxs-lookup"><span data-stu-id="1c73c-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="1c73c-103">マネージ コードから例外がスローされたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1c73c-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c73c-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c73c-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c73c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1c73c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1c73c-106">[in]例外がスローされたアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1c73c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="1c73c-107">[in]例外がスローされたスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1c73c-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="1c73c-108">[in]この値が場合`false`例外が、まだそれ以外のアプリケーションによって処理されると、例外が処理されないとプロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="1c73c-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c73c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c73c-109">Remarks</span></span>  
 <span data-ttu-id="1c73c-110">特定の例外は、スレッド オブジェクトから取得できます。</span><span class="sxs-lookup"><span data-stu-id="1c73c-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c73c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="1c73c-111">Requirements</span></span>  
 <span data-ttu-id="1c73c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c73c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c73c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c73c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c73c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c73c-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1c73c-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1c73c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c73c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c73c-116">See also</span></span>

- [<span data-ttu-id="1c73c-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c73c-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
