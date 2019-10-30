---
title: ICorDebugThread::CreateEval メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: 0c622e0eba27f501446d2b7d9d264ee0834e869c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133613"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="1b17d-102">ICorDebugThread::CreateEval メソッド</span><span class="sxs-lookup"><span data-stu-id="1b17d-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="1b17d-103">このスレッドの機能を収集して公開する、表示されるオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b17d-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b17d-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b17d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b17d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b17d-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="1b17d-106">入出力このスレッドの機能を収集して公開する `ICorDebugEval` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1b17d-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b17d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b17d-107">Remarks</span></span>  
 <span data-ttu-id="1b17d-108">評価オブジェクトは、計算を実行する前に、スレッドに新しいチェーンをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="1b17d-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="1b17d-109">これにより、評価が完了するまで、スレッドで現在実行されている計算が中断されます。</span><span class="sxs-lookup"><span data-stu-id="1b17d-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b17d-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="1b17d-110">Requirements</span></span>  
 <span data-ttu-id="1b17d-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b17d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b17d-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b17d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b17d-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b17d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b17d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b17d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
