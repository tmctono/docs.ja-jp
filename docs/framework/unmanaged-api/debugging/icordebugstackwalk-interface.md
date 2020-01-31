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
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791876"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="7ae1b-102">ICorDebugStackWalk インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ae1b-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="7ae1b-103">スレッドのスタック上のマネージド メソッド (フレーム) を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ae1b-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ae1b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7ae1b-104">Methods</span></span>  
  
|<span data-ttu-id="7ae1b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7ae1b-105">Method</span></span>|<span data-ttu-id="7ae1b-106">説明</span><span class="sxs-lookup"><span data-stu-id="7ae1b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ae1b-107">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="7ae1b-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="7ae1b-108">`ICorDebugStackWalk` オブジェクト内の現在のフレームのコンテキストを返します。</span><span class="sxs-lookup"><span data-stu-id="7ae1b-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="7ae1b-109">SetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="7ae1b-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="7ae1b-110">`ICorDebugStackWalk` オブジェクトの現在のコンテキストをスレッドの有効なコンテキストに設定します。</span><span class="sxs-lookup"><span data-stu-id="7ae1b-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="7ae1b-111">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="7ae1b-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="7ae1b-112">`ICorDebugStackWalk` オブジェクトを次のフレームに移動します。</span><span class="sxs-lookup"><span data-stu-id="7ae1b-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="7ae1b-113">GetFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="7ae1b-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="7ae1b-114">`ICorDebugStackWalk` オブジェクト内の現在のフレームを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ae1b-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ae1b-115">コメント</span><span class="sxs-lookup"><span data-stu-id="7ae1b-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ae1b-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7ae1b-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae1b-117">要件</span><span class="sxs-lookup"><span data-stu-id="7ae1b-117">Requirements</span></span>  
 <span data-ttu-id="7ae1b-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ae1b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae1b-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ae1b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ae1b-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ae1b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ae1b-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae1b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae1b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ae1b-122">See also</span></span>

- [<span data-ttu-id="7ae1b-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ae1b-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7ae1b-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7ae1b-124">Debugging</span></span>](index.md)
