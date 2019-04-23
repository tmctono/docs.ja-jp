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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184705"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="53e2f-102">ICorDebugThread インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53e2f-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="53e2f-103">プロセス内のスレッドを表します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-103">Represents a thread in a process.</span></span> <span data-ttu-id="53e2f-104">`ICorDebugThread` インスタンスの有効期間は、それが表しているスレッドの有効期間と同じです。</span><span class="sxs-lookup"><span data-stu-id="53e2f-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53e2f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-105">Methods</span></span>  
  
|<span data-ttu-id="53e2f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-106">Method</span></span>|<span data-ttu-id="53e2f-107">説明</span><span class="sxs-lookup"><span data-stu-id="53e2f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53e2f-108">ClearCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="53e2f-109">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="53e2f-109">This method is not implemented.</span></span> <span data-ttu-id="53e2f-110">使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="53e2f-110">Do not use it.</span></span>|  
|[<span data-ttu-id="53e2f-111">CreateEval メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="53e2f-112">これで動作する ICorDebugEval オブジェクトを作成`ICorDebugThread`です。</span><span class="sxs-lookup"><span data-stu-id="53e2f-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-113">CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="53e2f-114">これで、アクティブなフレームをステップ実行できるようにする ICorDebugStepper オブジェクトを作成します。`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-115">EnumerateChains メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="53e2f-116">これですべてのスタック チェーンを含む ICorDebugChainEnum 列挙子へのインターフェイス ポインターを取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-117">GetActiveChain メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="53e2f-118">これで active ICorDebugChain へのインターフェイス ポインターを取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-119">GetActiveFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="53e2f-120">これで active ICorDebugFrame へのインターフェイス ポインターを取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-121">GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="53e2f-122">このアプリケーション ドメインへのインターフェイス ポインターを取得`ICorDebugThread`現在実行しています。</span><span class="sxs-lookup"><span data-stu-id="53e2f-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="53e2f-123">GetCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="53e2f-124">現在、マネージ コードによってスローされる例外を表す ICorDebugValue オブジェクトへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="53e2f-125">GetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="53e2f-126">この現在のデバッグ状態を説明する CorDebugThreadState 値を取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-127">GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="53e2f-128">このアクティブな部分の現在のハンドルを取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-129">GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="53e2f-130">このアクティブな部分の現在のオペレーティング システムの識別子を取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-131">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="53e2f-132">共通言語ランタイム (CLR) スレッドにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="53e2f-133">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="53e2f-134">このプロセスにインターフェイス ポインターを取得`ICorDebugThread`一部を形成します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="53e2f-135">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="53e2f-136">これに関連付けられている登録のセットにインターフェイス ポインターを取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-137">GetUserState メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="53e2f-138">この現在の状態を記述する CorDebugUserState 値のビットごとの組み合わせを取得`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="53e2f-139">SetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="53e2f-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="53e2f-140">ビットごとの組み合わせを設定`CorDebugThreadState`このデバッグ状態を記述する値`ICorDebugThread`します。</span><span class="sxs-lookup"><span data-stu-id="53e2f-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53e2f-141">Remarks</span><span class="sxs-lookup"><span data-stu-id="53e2f-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53e2f-142">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="53e2f-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53e2f-143">必要条件</span><span class="sxs-lookup"><span data-stu-id="53e2f-143">Requirements</span></span>  
 <span data-ttu-id="53e2f-144">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="53e2f-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53e2f-145">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53e2f-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53e2f-146">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53e2f-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53e2f-147">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53e2f-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e2f-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="53e2f-148">See also</span></span>

- [<span data-ttu-id="53e2f-149">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53e2f-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
