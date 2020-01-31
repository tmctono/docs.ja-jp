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
ms.openlocfilehash: f4bacfe94178ea78b1c3afd15a2e100076c38a84
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777993"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="9538b-102">ICorDebugChain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9538b-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="9538b-103">物理呼び出し履歴または論理呼び出し履歴のセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="9538b-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9538b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-104">Methods</span></span>  
  
|<span data-ttu-id="9538b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-105">Method</span></span>|<span data-ttu-id="9538b-106">説明</span><span class="sxs-lookup"><span data-stu-id="9538b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9538b-107">EnumerateFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-107">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="9538b-108">チェーン内のすべてのマネージスタックフレームが格納された列挙子を取得します。これは、最新のフレームから始まります。</span><span class="sxs-lookup"><span data-stu-id="9538b-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="9538b-109">GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-109">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="9538b-110">チェーンのアクティブな (つまり、最新の) フレームを取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="9538b-111">GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-111">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="9538b-112">このチェーンによって呼び出されたチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="9538b-113">GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-113">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="9538b-114">このチェーンを呼び出したチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="9538b-115">GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-115">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="9538b-116">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="9538b-116">Not implemented.</span></span>|  
|[<span data-ttu-id="9538b-117">GetNext メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-117">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="9538b-118">スレッドの次のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="9538b-119">GetPrevious メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-119">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="9538b-120">スレッドの前のフレームのチェーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="9538b-121">GetReason メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-121">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="9538b-122">この呼び出しチェーンの genesis の理由を取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="9538b-123">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-123">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="9538b-124">このチェーンのアクティブな部分のレジスタセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="9538b-125">GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-125">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="9538b-126">このチェーンのスタックセグメントのアドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="9538b-127">GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-127">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="9538b-128">この呼び出しチェーンが含まれている物理スレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="9538b-129">IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="9538b-129">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="9538b-130">このチェーンでマネージコードが実行されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9538b-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9538b-131">コメント</span><span class="sxs-lookup"><span data-stu-id="9538b-131">Remarks</span></span>  
 <span data-ttu-id="9538b-132">チェーン内のスタックフレームは、連続したスタック領域を占有し、同じスレッドとコンテキストを共有します。</span><span class="sxs-lookup"><span data-stu-id="9538b-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="9538b-133">チェーンは、マネージコードチェーンまたはアンマネージコードチェーンを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="9538b-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="9538b-134">空の `ICorDebugChain` インスタンスは、アンマネージコードチェーンを表します。</span><span class="sxs-lookup"><span data-stu-id="9538b-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9538b-135">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9538b-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9538b-136">要件</span><span class="sxs-lookup"><span data-stu-id="9538b-136">Requirements</span></span>  
 <span data-ttu-id="9538b-137">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9538b-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9538b-138">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9538b-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9538b-139">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9538b-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9538b-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9538b-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9538b-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="9538b-141">See also</span></span>

- [<span data-ttu-id="9538b-142">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9538b-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
