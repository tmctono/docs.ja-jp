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
ms.openlocfilehash: 93ada40bd88e53cd06f5e8d8136b2d527d7741e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969307"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="6a31a-102">ICorDebugChain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a31a-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="6a31a-103">物理呼び出し履歴または論理呼び出し履歴のセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a31a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-104">Methods</span></span>  
  
|<span data-ttu-id="6a31a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-105">Method</span></span>|<span data-ttu-id="6a31a-106">説明</span><span class="sxs-lookup"><span data-stu-id="6a31a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a31a-107">EnumerateFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="6a31a-108">チェーン内のすべてのマネージスタックフレームが格納された列挙子を取得します。これは、最新のフレームから始まります。</span><span class="sxs-lookup"><span data-stu-id="6a31a-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="6a31a-109">GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="6a31a-110">チェーンのアクティブな (つまり、最新の) フレームを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="6a31a-111">GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="6a31a-112">このチェーンによって呼び出されたチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="6a31a-113">GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="6a31a-114">このチェーンを呼び出したチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="6a31a-115">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="6a31a-116">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="6a31a-116">Not implemented.</span></span>|  
|[<span data-ttu-id="6a31a-117">GetNext メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="6a31a-118">スレッドの次のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="6a31a-119">GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="6a31a-120">スレッドの前のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="6a31a-121">GetReason メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="6a31a-122">この呼び出しチェーンの genesis の理由を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="6a31a-123">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="6a31a-124">このチェーンのアクティブな部分のレジスタセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="6a31a-125">GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="6a31a-126">このチェーンのスタックセグメントのアドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="6a31a-127">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="6a31a-128">この呼び出しチェーンが含まれている物理スレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="6a31a-129">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="6a31a-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="6a31a-130">このチェーンでマネージコードが実行されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a31a-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a31a-131">Remarks</span></span>  
 <span data-ttu-id="6a31a-132">チェーン内のスタックフレームは、連続したスタック領域を占有し、同じスレッドとコンテキストを共有します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="6a31a-133">チェーンは、マネージコードチェーンまたはアンマネージコードチェーンを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a31a-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="6a31a-134">空`ICorDebugChain`のインスタンスは、アンマネージコードチェーンを表します。</span><span class="sxs-lookup"><span data-stu-id="6a31a-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a31a-135">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6a31a-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a31a-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a31a-136">Requirements</span></span>  
 <span data-ttu-id="6a31a-137">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a31a-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a31a-138">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6a31a-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a31a-139">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="6a31a-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a31a-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a31a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a31a-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a31a-141">See also</span></span>

- [<span data-ttu-id="6a31a-142">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6a31a-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
