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
ms.openlocfilehash: 6ae0fec0f8de2bbe3862f9f70ed9cf3d32af34c4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894210"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="d4cf1-102">ICorDebugChain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4cf1-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="d4cf1-103">物理呼び出し履歴または論理呼び出し履歴のセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4cf1-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-104">Methods</span></span>  
  
|<span data-ttu-id="d4cf1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-105">Method</span></span>|<span data-ttu-id="d4cf1-106">説明</span><span class="sxs-lookup"><span data-stu-id="d4cf1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4cf1-107">EnumerateFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-107">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="d4cf1-108">チェーン内のすべてのマネージスタックフレームが格納された列挙子を取得します。これは、最新のフレームから始まります。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="d4cf1-109">GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-109">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="d4cf1-110">チェーンのアクティブな (つまり、最新の) フレームを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="d4cf1-111">GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-111">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="d4cf1-112">このチェーンによって呼び出されたチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="d4cf1-113">GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-113">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="d4cf1-114">このチェーンを呼び出したチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="d4cf1-115">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-115">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="d4cf1-116">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-116">Not implemented.</span></span>|  
|[<span data-ttu-id="d4cf1-117">GetNext メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-117">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="d4cf1-118">スレッドの次のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="d4cf1-119">GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-119">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="d4cf1-120">スレッドの前のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="d4cf1-121">GetReason メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-121">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="d4cf1-122">この呼び出しチェーンの genesis の理由を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="d4cf1-123">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-123">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="d4cf1-124">このチェーンのアクティブな部分のレジスタセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="d4cf1-125">GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-125">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="d4cf1-126">このチェーンのスタックセグメントのアドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="d4cf1-127">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-127">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="d4cf1-128">この呼び出しチェーンが含まれている物理スレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="d4cf1-129">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="d4cf1-129">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="d4cf1-130">このチェーンでマネージコードが実行されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4cf1-131">解説</span><span class="sxs-lookup"><span data-stu-id="d4cf1-131">Remarks</span></span>  
 <span data-ttu-id="d4cf1-132">チェーン内のスタックフレームは、連続したスタック領域を占有し、同じスレッドとコンテキストを共有します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="d4cf1-133">チェーンは、マネージコードチェーンまたはアンマネージコードチェーンを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="d4cf1-134">空`ICorDebugChain`のインスタンスは、アンマネージコードチェーンを表します。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4cf1-135">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4cf1-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="d4cf1-136">Requirements</span></span>  
 <span data-ttu-id="d4cf1-137">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4cf1-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4cf1-138">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4cf1-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4cf1-139">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4cf1-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4cf1-140">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4cf1-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cf1-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4cf1-141">See also</span></span>

- [<span data-ttu-id="d4cf1-142">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4cf1-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
