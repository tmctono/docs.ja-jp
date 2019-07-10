---
title: ICorDebugProcess::ClearCurrentException メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ad7dd3ae0e547933fdf7d579116dccc62ae579c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766151"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="1e24c-102">ICorDebugProcess::ClearCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="1e24c-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="1e24c-103">特定のスレッドで現在管理されていない例外をクリアします。</span><span class="sxs-lookup"><span data-stu-id="1e24c-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e24c-104">構文</span><span class="sxs-lookup"><span data-stu-id="1e24c-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e24c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e24c-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="1e24c-106">[in]現在管理されていない例外をクリアするスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="1e24c-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e24c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e24c-107">Remarks</span></span>  
 <span data-ttu-id="1e24c-108">このメソッドを呼び出す前に[icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)スレッドがデバッガーによって無視されるアンマネージ例外を報告する場合。</span><span class="sxs-lookup"><span data-stu-id="1e24c-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="1e24c-109">これは、未処理の帯域内 (IB) と特定のスレッドでの帯域外の (OOB) のイベントの両方にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="1e24c-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="1e24c-110">すべての OOB ブレークポイントとシングル ステップの例外は自動的にクリアします。</span><span class="sxs-lookup"><span data-stu-id="1e24c-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="1e24c-111">使用[icordebugthread 2::interceptcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)現在をインターセプトするスレッドの例外を管理します。</span><span class="sxs-lookup"><span data-stu-id="1e24c-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e24c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="1e24c-112">Requirements</span></span>  
 <span data-ttu-id="1e24c-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e24c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e24c-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e24c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e24c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e24c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e24c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e24c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
