---
title: ICorDebugThread2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: 49d0015e9d8390a47aae7ce497dd431dfe743c36
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138676"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="88a34-102">ICorDebugThread2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88a34-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="88a34-103">は、"、" スレッドインターフェイスの論理的な拡張として機能します。</span><span class="sxs-lookup"><span data-stu-id="88a34-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88a34-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="88a34-104">Methods</span></span>  
  
|<span data-ttu-id="88a34-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="88a34-105">Method</span></span>|<span data-ttu-id="88a34-106">説明</span><span class="sxs-lookup"><span data-stu-id="88a34-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88a34-107">GetActiveFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="88a34-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="88a34-108">スレッドのフレーム内のアクティブな関数に関するデータを格納する COR_ACTIVE_FUNCTION インスタンスの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="88a34-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="88a34-109">GetConnectionID メソッド</span><span class="sxs-lookup"><span data-stu-id="88a34-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="88a34-110">この `ICorDebugThread2`の接続識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="88a34-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="88a34-111">GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="88a34-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="88a34-112">この `ICorDebugThread2`のタスク識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="88a34-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="88a34-113">GetVolatileOSThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="88a34-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="88a34-114">この `ICorDebugThread2`のオペレーティングシステムスレッド識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="88a34-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="88a34-115">InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="88a34-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="88a34-116">デバッガーがスレッドの現在の例外をインターセプトできるようにします。</span><span class="sxs-lookup"><span data-stu-id="88a34-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88a34-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="88a34-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88a34-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="88a34-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88a34-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="88a34-119">Requirements</span></span>  
 <span data-ttu-id="88a34-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88a34-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88a34-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88a34-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88a34-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88a34-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88a34-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88a34-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88a34-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="88a34-124">See also</span></span>

- [<span data-ttu-id="88a34-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88a34-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
