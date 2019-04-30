---
title: ICorDebugStepper::StepOut メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663f5134cf34bf9beb66da20bbb5886baff5415
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987429"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="4235e-102">ICorDebugStepper::StepOut メソッド</span><span class="sxs-lookup"><span data-stu-id="4235e-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="4235e-103">Icordebugstepper シングル ステップ実行し、その格納のスレッドでは、現在のフレームが呼び出し元のフレームにコントロールを返されるときに完了するを表示します。</span><span class="sxs-lookup"><span data-stu-id="4235e-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4235e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4235e-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4235e-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="4235e-105">Remarks</span></span>  
 <span data-ttu-id="4235e-106">A`StepOut`呼び出し元のフレームに、現在のフレームから正常に戻った後操作が完了します。</span><span class="sxs-lookup"><span data-stu-id="4235e-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="4235e-107">場合`StepOut`時に呼び出される、現在のフレームがそれを呼び出したマネージ コードに返されるときに、アンマネージ コードでの手順を行います。</span><span class="sxs-lookup"><span data-stu-id="4235e-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="4235e-108">.NET Framework version 2.0 では使用しません`StepOut`STOP_UNMANAGED フラグ セット失敗します。</span><span class="sxs-lookup"><span data-stu-id="4235e-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="4235e-109">(使用[icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)ステップ実行するためのフラグを設定します)。デバッガーの相互運用する必要があります ステップ アウトをネイティブ コードに自体。</span><span class="sxs-lookup"><span data-stu-id="4235e-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4235e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4235e-110">Requirements</span></span>  
 <span data-ttu-id="4235e-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4235e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4235e-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4235e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4235e-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4235e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4235e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4235e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
