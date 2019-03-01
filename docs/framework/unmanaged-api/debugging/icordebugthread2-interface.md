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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e162c114de013eed160a515dbc92fef47ea3327
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980504"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="14055-102">ICorDebugThread2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14055-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="14055-103">ICorDebugThread インターフェイスを論理的に拡張として機能します。</span><span class="sxs-lookup"><span data-stu-id="14055-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14055-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="14055-104">Methods</span></span>  
  
|<span data-ttu-id="14055-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="14055-105">Method</span></span>|<span data-ttu-id="14055-106">説明</span><span class="sxs-lookup"><span data-stu-id="14055-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14055-107">GetActiveFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="14055-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="14055-108">スレッドのフレーム内のアクティブな関数についてのデータを含む COR_ACTIVE_FUNCTION インスタンスの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="14055-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="14055-109">GetConnectionID メソッド</span><span class="sxs-lookup"><span data-stu-id="14055-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="14055-110">この接続識別子を取得します。`ICorDebugThread2`します。</span><span class="sxs-lookup"><span data-stu-id="14055-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="14055-111">GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="14055-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="14055-112">このタスクの識別子を取得`ICorDebugThread2`します。</span><span class="sxs-lookup"><span data-stu-id="14055-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="14055-113">GetVolatileOSThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="14055-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="14055-114">このオペレーティング システムのスレッド識別子を取得します。`ICorDebugThread2`します。</span><span class="sxs-lookup"><span data-stu-id="14055-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="14055-115">InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="14055-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="14055-116">スレッドで現在の例外をインターセプトするデバッガーを使用します。</span><span class="sxs-lookup"><span data-stu-id="14055-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14055-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="14055-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14055-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="14055-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14055-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="14055-119">Requirements</span></span>  
 <span data-ttu-id="14055-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14055-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14055-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14055-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14055-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14055-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14055-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14055-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14055-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="14055-124">See also</span></span>
- [<span data-ttu-id="14055-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14055-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
