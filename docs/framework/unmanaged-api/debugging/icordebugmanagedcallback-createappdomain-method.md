---
title: ICorDebugManagedCallback::CreateAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3958e62f23615d4c9038713bb973a6d16424f348
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759728"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="06376-102">ICorDebugManagedCallback::CreateAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="06376-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="06376-103">アプリケーション ドメインが作成されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="06376-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06376-104">構文</span><span class="sxs-lookup"><span data-stu-id="06376-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06376-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06376-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="06376-106">[in]アプリケーション ドメインが作成されたプロセスを表す ICorDebugProcess オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="06376-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="06376-107">[in]作成されたアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="06376-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06376-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="06376-108">Requirements</span></span>  
 <span data-ttu-id="06376-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06376-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06376-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06376-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06376-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06376-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06376-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06376-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06376-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="06376-113">See also</span></span>

- [<span data-ttu-id="06376-114">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06376-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
