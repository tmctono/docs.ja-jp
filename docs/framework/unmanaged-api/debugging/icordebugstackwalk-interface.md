---
title: ICorDebugStackWalk インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e33e9be112a6a10f89b88005496ce2e63dff2d54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782682"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="f3d58-102">ICorDebugStackWalk インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3d58-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="f3d58-103">スレッドのスタック上のマネージド メソッド (フレーム) を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3d58-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3d58-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f3d58-104">Methods</span></span>  
  
|<span data-ttu-id="f3d58-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f3d58-105">Method</span></span>|<span data-ttu-id="f3d58-106">説明</span><span class="sxs-lookup"><span data-stu-id="f3d58-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3d58-107">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="f3d58-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="f3d58-108">現在のフレームのコンテキストを返します、`ICorDebugStackWalk`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f3d58-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="f3d58-109">SetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="f3d58-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="f3d58-110">セット、`ICorDebugStackWalk`オブジェクトの現在のスレッドの有効なコンテキストのコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="f3d58-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="f3d58-111">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f3d58-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="f3d58-112">移動、`ICorDebugStackWalk`次のフレームにオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f3d58-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="f3d58-113">GetFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="f3d58-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="f3d58-114">内の現在のフレームを取得、`ICorDebugStackWalk`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f3d58-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3d58-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3d58-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3d58-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f3d58-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3d58-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="f3d58-117">Requirements</span></span>  
 <span data-ttu-id="f3d58-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3d58-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3d58-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3d58-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3d58-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3d58-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3d58-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3d58-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d58-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3d58-122">See also</span></span>

- [<span data-ttu-id="f3d58-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3d58-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f3d58-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f3d58-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
