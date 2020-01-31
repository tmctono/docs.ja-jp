---
title: ICorDebugManagedCallback::ExitAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
ms.openlocfilehash: 7bfa71ccff4a65e72a6b548a09d27648b67c0ae5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781853"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="84a71-102">ICorDebugManagedCallback::ExitAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="84a71-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="84a71-103">アプリケーションドメインが終了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="84a71-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a71-104">構文</span><span class="sxs-lookup"><span data-stu-id="84a71-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84a71-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84a71-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="84a71-106">から指定されたアプリケーションドメインを含むプロセスを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="84a71-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="84a71-107">から終了したアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="84a71-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a71-108">要件</span><span class="sxs-lookup"><span data-stu-id="84a71-108">Requirements</span></span>  
 <span data-ttu-id="84a71-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a71-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a71-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84a71-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84a71-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84a71-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84a71-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a71-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a71-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="84a71-113">See also</span></span>

- [<span data-ttu-id="84a71-114">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84a71-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
