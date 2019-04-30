---
title: ICorDebugManagedCallback::UnloadModule メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12e42da015864e83663d2f4d74bab2a34052d760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995086"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="b1052-102">ICorDebugManagedCallback::UnloadModule メソッド</span><span class="sxs-lookup"><span data-stu-id="b1052-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="b1052-103">共通言語ランタイム モジュール (DLL) がアンロードされたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b1052-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1052-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1052-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1052-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1052-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b1052-106">[in]モジュールに含まれるアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b1052-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="b1052-107">[in]モジュールを表す ICorDebugModule オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b1052-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1052-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1052-108">Remarks</span></span>  
 <span data-ttu-id="b1052-109">この呼び出しの後、モジュールを使用しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1052-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1052-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b1052-110">Requirements</span></span>  
 <span data-ttu-id="b1052-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1052-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1052-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1052-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1052-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1052-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1052-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1052-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1052-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1052-115">See also</span></span>

- [<span data-ttu-id="b1052-116">LoadModule メソッド</span><span class="sxs-lookup"><span data-stu-id="b1052-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="b1052-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1052-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
