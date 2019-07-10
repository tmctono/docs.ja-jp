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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1e045c475b57f863071eb81194868b7db3c5a3c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755799"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="dbc23-102">ICorDebugManagedCallback::ExitAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="dbc23-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="dbc23-103">アプリケーション ドメインが終了していることをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="dbc23-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc23-104">構文</span><span class="sxs-lookup"><span data-stu-id="dbc23-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbc23-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dbc23-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="dbc23-106">[in]特定のアプリケーション ドメインが含まれるプロセスを表す ICorDebugProcess オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dbc23-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="dbc23-107">[in]終了するアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dbc23-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbc23-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="dbc23-108">Requirements</span></span>  
 <span data-ttu-id="dbc23-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbc23-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbc23-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbc23-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbc23-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbc23-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbc23-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbc23-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc23-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbc23-113">See also</span></span>

- [<span data-ttu-id="dbc23-114">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dbc23-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
