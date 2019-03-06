---
title: ICorDebugThread::GetAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12a37ee8367006975b0f8ee4fa638ae3d72f9486
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487748"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="b915e-102">ICorDebugThread::GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="b915e-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="b915e-103">この ICorDebugThread を現在実行しているアプリケーション ドメインにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b915e-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b915e-104">構文</span><span class="sxs-lookup"><span data-stu-id="b915e-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b915e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b915e-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="b915e-106">[out]このスレッドを現在実行しているアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b915e-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b915e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b915e-107">Requirements</span></span>  
 <span data-ttu-id="b915e-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b915e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b915e-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b915e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b915e-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b915e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b915e-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b915e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
