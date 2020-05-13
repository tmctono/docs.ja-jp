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
ms.openlocfilehash: a7a8d96548704f223f05826af79a4e227bdfab06
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379832"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="25ecb-102">ICorDebugThread2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="25ecb-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="25ecb-103">は、"、" スレッドインターフェイスの論理的な拡張として機能します。</span><span class="sxs-lookup"><span data-stu-id="25ecb-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25ecb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="25ecb-104">Methods</span></span>  
  
|<span data-ttu-id="25ecb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="25ecb-105">Method</span></span>|<span data-ttu-id="25ecb-106">説明</span><span class="sxs-lookup"><span data-stu-id="25ecb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25ecb-107">GetActiveFunctions メソッド</span><span class="sxs-lookup"><span data-stu-id="25ecb-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="25ecb-108">スレッドのフレーム内のアクティブな関数に関するデータを格納している COR_ACTIVE_FUNCTION インスタンスの配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="25ecb-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="25ecb-109">GetConnectionID メソッド</span><span class="sxs-lookup"><span data-stu-id="25ecb-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="25ecb-110">このの接続識別子を取得し `ICorDebugThread2` ます。</span><span class="sxs-lookup"><span data-stu-id="25ecb-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="25ecb-111">GetTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="25ecb-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="25ecb-112">こののタスク識別子を取得し `ICorDebugThread2` ます。</span><span class="sxs-lookup"><span data-stu-id="25ecb-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="25ecb-113">GetVolatileOSThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="25ecb-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="25ecb-114">こののオペレーティングシステムスレッド識別子を取得し `ICorDebugThread2` ます。</span><span class="sxs-lookup"><span data-stu-id="25ecb-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="25ecb-115">InterceptCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="25ecb-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="25ecb-116">デバッガーがスレッドの現在の例外をインターセプトできるようにします。</span><span class="sxs-lookup"><span data-stu-id="25ecb-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25ecb-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="25ecb-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25ecb-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="25ecb-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25ecb-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="25ecb-119">Requirements</span></span>  
 <span data-ttu-id="25ecb-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25ecb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25ecb-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25ecb-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25ecb-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25ecb-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25ecb-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25ecb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ecb-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="25ecb-124">See also</span></span>

- [<span data-ttu-id="25ecb-125">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="25ecb-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
