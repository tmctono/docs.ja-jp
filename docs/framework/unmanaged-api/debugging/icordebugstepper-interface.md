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
ms.openlocfilehash: e9bb69567a247472af42efb08b609d3474c87ed2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791789"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="a2267-102">ICorDebugStepper インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2267-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="a2267-103">デバッガーが実行するコード実行内のステップを表します。コマンドの発行から完了までの間は識別子として機能します。これを使用するとステップをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="a2267-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2267-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-104">Methods</span></span>  
  
|<span data-ttu-id="a2267-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-105">Method</span></span>|<span data-ttu-id="a2267-106">説明</span><span class="sxs-lookup"><span data-stu-id="a2267-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2267-107">Deactivate メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-107">Deactivate Method</span></span>](icordebugstepper-deactivate-method.md)|<span data-ttu-id="a2267-108">この `ICorDebugStepper` によって、最後に受信したステップのコマンドがキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="a2267-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="a2267-109">IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-109">IsActive Method</span></span>](icordebugstepper-isactive-method.md)|<span data-ttu-id="a2267-110">この `ICorDebugStepper` が現在ステップを実行しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a2267-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="a2267-111">SetInterceptMask メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-111">SetInterceptMask Method</span></span>](icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="a2267-112">ステップインするコードの種類を指定する CorDebugIntercept 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a2267-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="a2267-113">SetRangeIL メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-113">SetRangeIL Method</span></span>](icordebugstepper-setrangeil-method.md)|<span data-ttu-id="a2267-114">[ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md)を呼び出すかどうかを示す値を設定します。これは、ネイティブコードまたはステップスルー中のメソッドの Microsoft 中間言語 (MSIL) コードを基準として、引数の値を渡します。</span><span class="sxs-lookup"><span data-stu-id="a2267-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="a2267-115">SetUnmappedStopMask メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-115">SetUnmappedStopMask Method</span></span>](icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="a2267-116">実行が停止するマップされていないコードの種類を指定する CorDebugUnmappedStop 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a2267-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="a2267-117">Step メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-117">Step Method</span></span>](icordebugstepper-step-method.md)|<span data-ttu-id="a2267-118">この `ICorDebugStepper` は、そのスレッドを含むスレッドを1ステップずつ実行します。また、必要に応じて、スレッド内で呼び出される関数を使用したシングルステップ実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="a2267-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="a2267-119">StepOut メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-119">StepOut Method</span></span>](icordebugstepper-stepout-method.md)|<span data-ttu-id="a2267-120">この `ICorDebugStepper` は、そのコンテナーのスレッドを1ステップずつ実行し、現在のフレームが呼び出し元のフレームに制御を返すときに完了します。</span><span class="sxs-lookup"><span data-stu-id="a2267-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="a2267-121">StepRange メソッド</span><span class="sxs-lookup"><span data-stu-id="a2267-121">StepRange Method</span></span>](icordebugstepper-steprange-method.md)|<span data-ttu-id="a2267-122">この `ICorDebugStepper` は、そのスレッドを含むスレッドを1ステップずつ実行し、指定された範囲の最後のコードに到達したときにを返します。</span><span class="sxs-lookup"><span data-stu-id="a2267-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2267-123">コメント</span><span class="sxs-lookup"><span data-stu-id="a2267-123">Remarks</span></span>  
 <span data-ttu-id="a2267-124">`ICorDebugStepper` インターフェイスは、次の目的で機能します。</span><span class="sxs-lookup"><span data-stu-id="a2267-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="a2267-125">発行されたステップコマンドとそのコマンドの完了の間の識別子として機能します。</span><span class="sxs-lookup"><span data-stu-id="a2267-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="a2267-126">これは、実行可能なすべてのステップをカプセル化するための中心的なインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a2267-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="a2267-127">これにより、ステップ実行操作を途中で取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="a2267-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="a2267-128">スレッドごとに複数のステッパが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2267-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="a2267-129">たとえば、関数をステップオーバーしている間にブレークポイントがヒットし、ユーザーがその関数内で新しいステップ実行操作を開始する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2267-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="a2267-130">この状況をどのように処理するかは、デバッガーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a2267-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="a2267-131">デバッガーでは、元のステップ実行操作をキャンセルするか、2つの操作を入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2267-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="a2267-132">`ICorDebugStepper` インターフェイスでは、両方の選択肢がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a2267-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="a2267-133">共通言語ランタイム (CLR) がクロススレッドでマーシャリングされた呼び出しを行う場合、ステッパはスレッド間で移行される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2267-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2267-134">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a2267-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2267-135">要件</span><span class="sxs-lookup"><span data-stu-id="a2267-135">Requirements</span></span>  
 <span data-ttu-id="a2267-136">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2267-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2267-137">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2267-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2267-138">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2267-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2267-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2267-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2267-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2267-140">See also</span></span>

- [<span data-ttu-id="a2267-141">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2267-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
