---
title: ICorDebugChain インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01dded47fca26df11781153eb45693057a25ad01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220709"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="aa640-102">ICorDebugChain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa640-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="aa640-103">物理呼び出し履歴または論理呼び出し履歴のセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="aa640-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa640-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-104">Methods</span></span>  
  
|<span data-ttu-id="aa640-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-105">Method</span></span>|<span data-ttu-id="aa640-106">説明</span><span class="sxs-lookup"><span data-stu-id="aa640-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa640-107">EnumerateFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="aa640-108">最新のフレームを開始する、チェーン内のすべてのマネージ スタック フレームを含む列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="aa640-109">GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="aa640-110">アクティブなを取得します (つまり、最新) チェーン上のフレーム。</span><span class="sxs-lookup"><span data-stu-id="aa640-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="aa640-111">GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="aa640-112">このチェーンによって呼び出されたチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="aa640-113">GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="aa640-114">このチェーンと呼ばれるチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="aa640-115">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="aa640-116">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="aa640-116">Not implemented.</span></span>|  
|[<span data-ttu-id="aa640-117">GetNext メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="aa640-118">スレッドの次のフレーム チェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="aa640-119">GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="aa640-120">スレッドの前のフレーム チェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="aa640-121">GetReason メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="aa640-122">この呼び出しチェーンの起源の理由を取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="aa640-123">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="aa640-124">このチェーンのアクティブな部分のレジスタ セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="aa640-125">GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="aa640-126">このチェーンの履歴のセグメントのアドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="aa640-127">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="aa640-128">この呼び出しチェーンが物理スレッドの一部を取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="aa640-129">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="aa640-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="aa640-130">このチェーンがマネージ コードを実行しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="aa640-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa640-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa640-131">Remarks</span></span>  
 <span data-ttu-id="aa640-132">チェーン内のスタック フレームはスタックの連続した領域を占有し、同じスレッドとコンテキストを共有します。</span><span class="sxs-lookup"><span data-stu-id="aa640-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="aa640-133">チェーンは、いずれかのマネージまたはアンマネージ コードのチェーンを表す場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa640-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="aa640-134">空`ICorDebugChain`インスタンスは、アンマネージ コードのチェーンを表します。</span><span class="sxs-lookup"><span data-stu-id="aa640-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa640-135">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="aa640-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa640-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="aa640-136">Requirements</span></span>  
 <span data-ttu-id="aa640-137">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa640-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa640-138">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa640-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa640-139">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa640-139">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="aa640-140">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="aa640-140">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa640-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa640-141">See also</span></span>

- [<span data-ttu-id="aa640-142">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa640-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
