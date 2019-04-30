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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994059"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="99581-102">ICorDebugThread::GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="99581-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="99581-103">ICorDebugThread オブジェクトでアクティブな (最新) フレームへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="99581-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99581-104">構文</span><span class="sxs-lookup"><span data-stu-id="99581-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99581-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="99581-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="99581-106">[out]フレームを表す ICorDebugFrame インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="99581-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99581-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="99581-107">Remarks</span></span>  
 <span data-ttu-id="99581-108">`ppFrame`パラメーターが現在アクティブなフレームがない場合は null です。</span><span class="sxs-lookup"><span data-stu-id="99581-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99581-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="99581-109">Requirements</span></span>  
 <span data-ttu-id="99581-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99581-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99581-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99581-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99581-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99581-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99581-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99581-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
