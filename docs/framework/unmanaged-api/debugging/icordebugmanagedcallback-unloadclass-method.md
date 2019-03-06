---
title: ICorDebugManagedCallback::UnloadClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 020774778b21cf0f6029a666e0022fe83845c4ed
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472448"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="311f8-102">ICorDebugManagedCallback::UnloadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="311f8-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="311f8-103">クラスがアンロードされることをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="311f8-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="311f8-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="311f8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="311f8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="311f8-106">[in]クラスを含むアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="311f8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="311f8-107">[in]クラスを表す ICorDebugClass オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="311f8-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="311f8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="311f8-108">Remarks</span></span>  
 <span data-ttu-id="311f8-109">クラスは、この呼び出しの後は参照できません。</span><span class="sxs-lookup"><span data-stu-id="311f8-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="311f8-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="311f8-110">Requirements</span></span>  
 <span data-ttu-id="311f8-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="311f8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="311f8-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="311f8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="311f8-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="311f8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="311f8-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="311f8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311f8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="311f8-115">See also</span></span>
- [<span data-ttu-id="311f8-116">LoadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="311f8-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="311f8-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="311f8-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
