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
ms.openlocfilehash: edcc0ebcadc1bd95574b0276bfd0e2d42e5474fd
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379819"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="a11c9-102">ICorDebugThread インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a11c9-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="a11c9-103">プロセス内のスレッドを表します。</span><span class="sxs-lookup"><span data-stu-id="a11c9-103">Represents a thread in a process.</span></span> <span data-ttu-id="a11c9-104">`ICorDebugThread` インスタンスの有効期間は、それが表しているスレッドの有効期間と同じです。</span><span class="sxs-lookup"><span data-stu-id="a11c9-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a11c9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-105">Methods</span></span>  
  
|<span data-ttu-id="a11c9-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-106">Method</span></span>|<span data-ttu-id="a11c9-107">説明</span><span class="sxs-lookup"><span data-stu-id="a11c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a11c9-108">ClearCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="a11c9-109">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="a11c9-109">This method is not implemented.</span></span> <span data-ttu-id="a11c9-110">使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a11c9-110">Do not use it.</span></span>|  
|[<span data-ttu-id="a11c9-111">CreateEval メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="a11c9-112">このを操作する、のオブジェクトを作成し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-113">CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="a11c9-114">こののアクティブなフレームをステップ実行できるようにする ICorDebugStepper オブジェクトを作成し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-115">EnumerateChains メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="a11c9-116">この内のすべてのスタックチェーンを格納している ICorDebugChainEnum 列挙子へのインターフェイスポインターを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-117">GetActiveChain メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="a11c9-118">こののアクティブなツールチェーンへのインターフェイスポインターを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-119">GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="a11c9-120">この上のアクティブなテキストフレームへのインターフェイスポインターを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-121">GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="a11c9-122">このが現在実行されているアプリケーションドメインへのインターフェイスポインターを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="a11c9-123">GetCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="a11c9-124">現在マネージコードによってスローされている例外を表す、ICorDebugValue オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a11c9-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="a11c9-125">GetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="a11c9-126">このの現在のデバッグ状態を示す CorDebugThreadState 値を取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-127">GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="a11c9-128">こののアクティブな部分の現在のハンドルを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-129">GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="a11c9-130">こののアクティブな部分の現在のオペレーティングシステム識別子を取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-131">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="a11c9-132">共通言語ランタイム (CLR) スレッドへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a11c9-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="a11c9-133">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="a11c9-134">このがパートを形成するプロセスへのインターフェイスポインターを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="a11c9-135">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="a11c9-136">このに関連付けられているレジスタセットへのインターフェイスポインターを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-137">GetUserState メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="a11c9-138">このの現在の状態を示す CorDebugUserState 値のビットごとの組み合わせを取得し `ICorDebugThread` ます。</span><span class="sxs-lookup"><span data-stu-id="a11c9-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="a11c9-139">SetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="a11c9-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="a11c9-140">こののデバッグ状態を記述する値のビットごとの組み合わせを設定 `CorDebugThreadState` `ICorDebugThread` します。</span><span class="sxs-lookup"><span data-stu-id="a11c9-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a11c9-141">Remarks</span><span class="sxs-lookup"><span data-stu-id="a11c9-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a11c9-142">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a11c9-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a11c9-143">必要条件</span><span class="sxs-lookup"><span data-stu-id="a11c9-143">Requirements</span></span>  
 <span data-ttu-id="a11c9-144">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a11c9-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a11c9-145">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a11c9-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a11c9-146">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a11c9-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a11c9-147">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a11c9-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11c9-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="a11c9-148">See also</span></span>

- [<span data-ttu-id="a11c9-149">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a11c9-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
