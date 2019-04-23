---
title: ICorDebugStepper インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212519"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="d6c7c-102">ICorDebugStepper インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6c7c-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="d6c7c-103">デバッガーが実行するコード実行内のステップを表します。コマンドの発行から完了までの間は識別子として機能します。これを使用するとステップをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6c7c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-104">Methods</span></span>  
  
|<span data-ttu-id="d6c7c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-105">Method</span></span>|<span data-ttu-id="d6c7c-106">説明</span><span class="sxs-lookup"><span data-stu-id="d6c7c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6c7c-107">Deactivate メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="d6c7c-108">この原因`ICorDebugStepper`を受信した最後の手順のコマンドをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="d6c7c-109">IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="d6c7c-110">示す値を取得するかどうかこの`ICorDebugStepper`ステップが現在実行します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="d6c7c-111">SetInterceptMask メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="d6c7c-112">ステップ インはコードの種類を示す CorDebugIntercept 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="d6c7c-113">SetRangeIL メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="d6c7c-114">示す値を設定するかどうかを呼び出す[icordebugstepper::steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)またはスルーされるメソッドの Microsoft intermediate language (MSIL) コードにネイティブ コードへの相対引数の値を渡します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="d6c7c-115">SetUnmappedStopMask メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="d6c7c-116">マップされていないコードが実行を中断の種類を示す CorDebugUnmappedStop 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="d6c7c-117">Step メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="d6c7c-118">この原因`ICorDebugStepper`その格納のスレッドと、必要に応じてをシングル ステップ実行するスレッド内で呼び出される関数をシングル ステップ実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="d6c7c-119">StepOut メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="d6c7c-120">この原因`ICorDebugStepper`その格納のスレッドをシングル ステップ実行して、完了時に、現在のフレームが呼び出し元のフレームにコントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="d6c7c-121">StepRange メソッド</span><span class="sxs-lookup"><span data-stu-id="d6c7c-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="d6c7c-122">この原因`ICorDebugStepper`シングル ステップの場合に返されるとその格納のスレッドを指定した範囲の最後のタスクを超えるコードに到達します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6c7c-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6c7c-123">Remarks</span></span>  
 <span data-ttu-id="d6c7c-124">`ICorDebugStepper`インターフェイスは、次の目的で機能します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="d6c7c-125">ステップ コマンドが発行されますが、そのコマンドの完了の間で識別子として機能します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="d6c7c-126">実行できるすべてのステップ実行をカプセル化する中央のインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="d6c7c-127">ステップ実行操作の途中でキャンセルする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="d6c7c-128">スレッドごとの 1 つ以上のステッパことができます。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="d6c7c-129">たとえば、ステップ オーバー関数の場合、中に、ブレークポイントにヒットする可能性があり、ユーザーが関数の内部での新しいステップ実行操作を開始することがあります。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="d6c7c-130">この状況に対処する方法については、デバッガーの責任です。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="d6c7c-131">デバッガーは元のステップ実行操作をキャンセルするか、2 つの操作を入れ子にします。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="d6c7c-132">`ICorDebugStepper`インターフェイスは、2 つの選択肢をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="d6c7c-133">共通言語ランタイム (CLR) が、マーシャ リングされたクロス シングル スレッドの呼び出しを行った場合、ステッパをスレッド間で移行可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6c7c-134">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6c7c-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6c7c-135">Requirements</span></span>  
 <span data-ttu-id="d6c7c-136">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6c7c-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6c7c-137">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6c7c-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6c7c-138">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6c7c-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6c7c-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6c7c-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c7c-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6c7c-140">See also</span></span>

- [<span data-ttu-id="d6c7c-141">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d6c7c-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
