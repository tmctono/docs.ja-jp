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
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378907"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="2f6c5-102">ICorDebugStackWalk インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f6c5-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="2f6c5-103">スレッドのスタック上のマネージド メソッド (フレーム) を取得するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2f6c5-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f6c5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f6c5-104">Methods</span></span>  
  
|<span data-ttu-id="2f6c5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f6c5-105">Method</span></span>|<span data-ttu-id="2f6c5-106">説明</span><span class="sxs-lookup"><span data-stu-id="2f6c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f6c5-107">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="2f6c5-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="2f6c5-108">オブジェクト内の現在のフレームのコンテキストを返し `ICorDebugStackWalk` ます。</span><span class="sxs-lookup"><span data-stu-id="2f6c5-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="2f6c5-109">SetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="2f6c5-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="2f6c5-110">`ICorDebugStackWalk`オブジェクトの現在のコンテキストをスレッドの有効なコンテキストに設定します。</span><span class="sxs-lookup"><span data-stu-id="2f6c5-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="2f6c5-111">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="2f6c5-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="2f6c5-112">オブジェクトを `ICorDebugStackWalk` 次のフレームに移動します。</span><span class="sxs-lookup"><span data-stu-id="2f6c5-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="2f6c5-113">GetFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="2f6c5-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="2f6c5-114">オブジェクト内の現在のフレームを取得し `ICorDebugStackWalk` ます。</span><span class="sxs-lookup"><span data-stu-id="2f6c5-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f6c5-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f6c5-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f6c5-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2f6c5-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f6c5-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="2f6c5-117">Requirements</span></span>  
 <span data-ttu-id="2f6c5-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f6c5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f6c5-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f6c5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f6c5-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f6c5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f6c5-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f6c5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6c5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f6c5-122">See also</span></span>

- [<span data-ttu-id="2f6c5-123">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f6c5-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2f6c5-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2f6c5-124">Debugging</span></span>](index.md)
