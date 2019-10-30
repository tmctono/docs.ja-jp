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
ms.openlocfilehash: d623893bd77e46832b0bd823ed60c23e4eee29ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133540"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="06a8a-102">ICorDebugThread::GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="06a8a-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="06a8a-103">このテキストスレッドオブジェクトのアクティブな (最新の) フレームへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="06a8a-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a8a-104">構文</span><span class="sxs-lookup"><span data-stu-id="06a8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06a8a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06a8a-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="06a8a-106">入出力フレームを表す、テキストフレームインターフェイスオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="06a8a-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06a8a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="06a8a-107">Remarks</span></span>  
 <span data-ttu-id="06a8a-108">現在アクティブになっているフレームがない場合、`ppFrame` パラメーターは null になります。</span><span class="sxs-lookup"><span data-stu-id="06a8a-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06a8a-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="06a8a-109">Requirements</span></span>  
 <span data-ttu-id="06a8a-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06a8a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a8a-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06a8a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06a8a-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06a8a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06a8a-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a8a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
