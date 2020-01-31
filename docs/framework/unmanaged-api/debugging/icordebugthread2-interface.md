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
ms.openlocfilehash: fdaad46b739721ff95b712d4b6461a793ae0a480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791430"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="13992-102">ICorDebugThread2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13992-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="13992-103">は、"、" スレッドインターフェイスの論理的な拡張として機能します。</span><span class="sxs-lookup"><span data-stu-id="13992-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13992-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="13992-104">Methods</span></span>  
  
|<span data-ttu-id="13992-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="13992-105">Method</span></span>|<span data-ttu-id="13992-106">説明</span><span class="sxs-lookup"><span data-stu-id="13992-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13992-107">GetActiveFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="13992-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="13992-108">スレッドのフレーム内のアクティブな関数に関するデータを格納している COR_ACTIVE_FUNCTION インスタンスの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="13992-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="13992-109">GetConnectionID メソッド</span><span class="sxs-lookup"><span data-stu-id="13992-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="13992-110">この `ICorDebugThread2`の接続識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="13992-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="13992-111">GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="13992-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="13992-112">この `ICorDebugThread2`のタスク識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="13992-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="13992-113">GetVolatileOSThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="13992-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="13992-114">この `ICorDebugThread2`のオペレーティングシステムスレッド識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="13992-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="13992-115">InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="13992-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="13992-116">デバッガーがスレッドの現在の例外をインターセプトできるようにします。</span><span class="sxs-lookup"><span data-stu-id="13992-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13992-117">コメント</span><span class="sxs-lookup"><span data-stu-id="13992-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13992-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="13992-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13992-119">要件</span><span class="sxs-lookup"><span data-stu-id="13992-119">Requirements</span></span>  
 <span data-ttu-id="13992-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13992-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13992-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13992-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13992-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13992-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13992-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13992-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13992-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="13992-124">See also</span></span>

- [<span data-ttu-id="13992-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13992-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
