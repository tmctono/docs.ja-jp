---
title: ICorDebugHeapValue3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: b062faffc22e444bd4d3b4a0c67f2a08d7af3560
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131108"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="40edb-102">ICorDebugHeapValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40edb-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="40edb-103">オブジェクトのモニター ロック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="40edb-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="40edb-104">このインターフェイスは、ICorDebugHeapValue2 の値とインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="40edb-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40edb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="40edb-105">Methods</span></span>  
  
|<span data-ttu-id="40edb-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="40edb-106">Method</span></span>|<span data-ttu-id="40edb-107">説明</span><span class="sxs-lookup"><span data-stu-id="40edb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40edb-108">GetThreadOwningMonitorLock メソッド</span><span class="sxs-lookup"><span data-stu-id="40edb-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="40edb-109">このオブジェクトのモニターロックを所有するマネージスレッドを返します。</span><span class="sxs-lookup"><span data-stu-id="40edb-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="40edb-110">GetMonitorEventWaitList メソッド</span><span class="sxs-lookup"><span data-stu-id="40edb-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="40edb-111">モニターロックに関連付けられているイベントでキューに登録されているスレッドの順序付きリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="40edb-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40edb-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="40edb-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40edb-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="40edb-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40edb-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="40edb-114">Requirements</span></span>  
 <span data-ttu-id="40edb-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40edb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40edb-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40edb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40edb-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40edb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40edb-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40edb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40edb-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="40edb-119">See also</span></span>

- [<span data-ttu-id="40edb-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40edb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="40edb-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="40edb-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
