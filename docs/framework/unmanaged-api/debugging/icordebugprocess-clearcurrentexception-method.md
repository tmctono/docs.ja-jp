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
ms.openlocfilehash: 37a7d8fa4439d52db3cddfff22ac6580b19af58a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128910"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="8e686-102">ICorDebugProcess::ClearCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="8e686-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="8e686-103">指定されたスレッドで現在のアンマネージ例外をクリアします。</span><span class="sxs-lookup"><span data-stu-id="8e686-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e686-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e686-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e686-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e686-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8e686-106">から現在のアンマネージ例外がクリアされるスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="8e686-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e686-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e686-107">Remarks</span></span>  
 <span data-ttu-id="8e686-108">スレッドがアンマネージ例外を報告し[たときに](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)、デバッグ対象では無視する必要がある場合は、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8e686-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="8e686-109">これにより、所定のスレッドで未処理の帯域内 (IB) イベントと帯域外 (OOB) イベントの両方がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="8e686-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="8e686-110">すべての OOB ブレークポイントと単一ステップの例外は、自動的にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="8e686-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="8e686-111">スレッドで現在のマネージ例外をインターセプトするには、 [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e686-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e686-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="8e686-112">Requirements</span></span>  
 <span data-ttu-id="8e686-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e686-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e686-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e686-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e686-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e686-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e686-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e686-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
