---
title: ICorDebugThread::GetActiveFrame メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 051491173bbcef3d87d9a3dbe854eece46c49e0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468781"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="e6dfc-102">ICorDebugThread::GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="e6dfc-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="e6dfc-103">ICorDebugThread オブジェクトでアクティブな (最新) フレームへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e6dfc-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6dfc-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6dfc-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6dfc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6dfc-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="e6dfc-106">[out]フレームを表す ICorDebugFrame インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6dfc-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6dfc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6dfc-107">Remarks</span></span>  
 <span data-ttu-id="e6dfc-108">`ppFrame`パラメーターが現在アクティブなフレームがない場合は null です。</span><span class="sxs-lookup"><span data-stu-id="e6dfc-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6dfc-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6dfc-109">Requirements</span></span>  
 <span data-ttu-id="e6dfc-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dfc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6dfc-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6dfc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6dfc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6dfc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6dfc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6dfc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
