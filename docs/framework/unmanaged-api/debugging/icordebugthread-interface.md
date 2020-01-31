---
title: ICorDebugThread インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
ms.openlocfilehash: b227b374021136e78f7f061d235eb18eca5b9515
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791478"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="6b5be-102">ICorDebugThread インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b5be-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="6b5be-103">プロセス内のスレッドを表します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-103">Represents a thread in a process.</span></span> <span data-ttu-id="6b5be-104">`ICorDebugThread` インスタンスの有効期間は、それが表しているスレッドの有効期間と同じです。</span><span class="sxs-lookup"><span data-stu-id="6b5be-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b5be-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-105">Methods</span></span>  
  
|<span data-ttu-id="6b5be-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-106">Method</span></span>|<span data-ttu-id="6b5be-107">説明</span><span class="sxs-lookup"><span data-stu-id="6b5be-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b5be-108">ClearCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="6b5be-109">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="6b5be-109">This method is not implemented.</span></span> <span data-ttu-id="6b5be-110">使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-110">Do not use it.</span></span>|  
|[<span data-ttu-id="6b5be-111">CreateEval メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="6b5be-112">この `ICorDebugThread`を操作する、のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-113">CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="6b5be-114">この `ICorDebugThread`内のアクティブなフレームをステップ実行できるようにする、ICorDebugStepper オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-115">EnumerateChains メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="6b5be-116">この `ICorDebugThread`内のすべてのスタックチェーンを格納している ICorDebugChainEnum 列挙子へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-117">GetActiveChain メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="6b5be-118">この `ICorDebugThread`上のアクティブなについてのオブジェクトチェーンへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-119">GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="6b5be-120">この `ICorDebugThread`のアクティブなテキストフレームへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-121">GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="6b5be-122">この `ICorDebugThread` が現在実行されているアプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="6b5be-123">GetCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="6b5be-124">現在マネージコードによってスローされている例外を表す、ICorDebugValue オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="6b5be-125">GetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="6b5be-126">この `ICorDebugThread`の現在のデバッグ状態を示す CorDebugThreadState 値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-127">GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="6b5be-128">この `ICorDebugThread`のアクティブな部分の現在のハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-129">GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="6b5be-130">この `ICorDebugThread`のアクティブな部分の現在のオペレーティングシステム識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-131">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="6b5be-132">共通言語ランタイム (CLR) スレッドへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="6b5be-133">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="6b5be-134">この `ICorDebugThread` がパートを形成するプロセスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="6b5be-135">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="6b5be-136">この `ICorDebugThread`に関連付けられているレジスタセットへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-137">GetUserState メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="6b5be-138">この `ICorDebugThread`の現在の状態を示す CorDebugUserState 値のビットごとの組み合わせを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="6b5be-139">SetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="6b5be-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="6b5be-140">この `ICorDebugThread`のデバッグ状態を記述する `CorDebugThreadState` 値のビットごとの組み合わせを設定します。</span><span class="sxs-lookup"><span data-stu-id="6b5be-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b5be-141">コメント</span><span class="sxs-lookup"><span data-stu-id="6b5be-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b5be-142">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6b5be-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b5be-143">要件</span><span class="sxs-lookup"><span data-stu-id="6b5be-143">Requirements</span></span>  
 <span data-ttu-id="6b5be-144">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b5be-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b5be-145">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b5be-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b5be-146">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b5be-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b5be-147">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b5be-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5be-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b5be-148">See also</span></span>

- [<span data-ttu-id="6b5be-149">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b5be-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
