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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994072"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="237c7-102">ICorDebugThread::CreateEval メソッド</span><span class="sxs-lookup"><span data-stu-id="237c7-102">ICorDebugThread::CreateEval Method</span></span>
<span data-ttu-id="237c7-103">ICorDebugEval を収集し、この ICorDebugThread の機能を公開するオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="237c7-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="237c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="237c7-104">Syntax</span></span>  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="237c7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="237c7-105">Parameters</span></span>  
 `ppEval`  
 <span data-ttu-id="237c7-106">[out]アドレスへのポインター、`ICorDebugEval`を収集し、このスレッドの機能を公開するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="237c7-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="237c7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="237c7-107">Remarks</span></span>  
 <span data-ttu-id="237c7-108">評価のオブジェクトは、計算を実行する前に、スレッドで新しいチェーンにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="237c7-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="237c7-109">これは、現在実行中のスレッドで評価が完了するまで計算を中断します。</span><span class="sxs-lookup"><span data-stu-id="237c7-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="237c7-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="237c7-110">Requirements</span></span>  
 <span data-ttu-id="237c7-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="237c7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="237c7-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="237c7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="237c7-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="237c7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="237c7-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="237c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
