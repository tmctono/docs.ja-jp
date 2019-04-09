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
ms.openlocfilehash: 82648714c375998e9daa1bb59cd9ebd9802b5794
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153934"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="be91b-102">ICorDebugThread2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="be91b-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="be91b-103">ICorDebugThread インターフェイスを論理的に拡張として機能します。</span><span class="sxs-lookup"><span data-stu-id="be91b-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be91b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="be91b-104">Methods</span></span>  
  
|<span data-ttu-id="be91b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="be91b-105">Method</span></span>|<span data-ttu-id="be91b-106">説明</span><span class="sxs-lookup"><span data-stu-id="be91b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be91b-107">GetActiveFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="be91b-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="be91b-108">スレッドのフレーム内のアクティブな関数についてのデータを含む COR_ACTIVE_FUNCTION インスタンスの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="be91b-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="be91b-109">GetConnectionID メソッド</span><span class="sxs-lookup"><span data-stu-id="be91b-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="be91b-110">この接続識別子を取得します。`ICorDebugThread2`します。</span><span class="sxs-lookup"><span data-stu-id="be91b-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="be91b-111">GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="be91b-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="be91b-112">このタスクの識別子を取得`ICorDebugThread2`します。</span><span class="sxs-lookup"><span data-stu-id="be91b-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="be91b-113">GetVolatileOSThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="be91b-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="be91b-114">このオペレーティング システムのスレッド識別子を取得します。`ICorDebugThread2`します。</span><span class="sxs-lookup"><span data-stu-id="be91b-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="be91b-115">InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="be91b-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="be91b-116">スレッドで現在の例外をインターセプトするデバッガーを使用します。</span><span class="sxs-lookup"><span data-stu-id="be91b-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be91b-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="be91b-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be91b-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="be91b-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be91b-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="be91b-119">Requirements</span></span>  
 <span data-ttu-id="be91b-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be91b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be91b-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be91b-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be91b-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be91b-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="be91b-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="be91b-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be91b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="be91b-124">See also</span></span>

- [<span data-ttu-id="be91b-125">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="be91b-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
