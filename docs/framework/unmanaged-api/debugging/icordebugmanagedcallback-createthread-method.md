---
title: ICorDebugManagedCallback::CreateThread メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48e92c73347957d8acc5c209f6f5473e9e18524
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223252"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="748f9-102">ICorDebugManagedCallback::CreateThread メソッド</span><span class="sxs-lookup"><span data-stu-id="748f9-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="748f9-103">スレッドのマネージ コードの実行が開始されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="748f9-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="748f9-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="748f9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="748f9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="748f9-106">[in]スレッドがあるアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="748f9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="748f9-107">[in]スレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="748f9-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="748f9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="748f9-108">Remarks</span></span>  
 <span data-ttu-id="748f9-109">スレッドは、実行されるマネージ コードの最初の命令に配置されます。</span><span class="sxs-lookup"><span data-stu-id="748f9-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="748f9-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="748f9-110">Requirements</span></span>  
 <span data-ttu-id="748f9-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="748f9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="748f9-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="748f9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="748f9-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="748f9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="748f9-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="748f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="748f9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="748f9-115">See also</span></span>

- [<span data-ttu-id="748f9-116">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="748f9-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
