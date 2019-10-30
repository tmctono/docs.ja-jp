---
title: ICorDebugStepper::SetUnmappedStopMask メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: ff393b119c349e34898b781c3185cc82f2dba11f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137551"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="3caf5-102">ICorDebugStepper::SetUnmappedStopMask メソッド</span><span class="sxs-lookup"><span data-stu-id="3caf5-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="3caf5-103">実行が停止するマップされていないコードの種類を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3caf5-104">構文</span><span class="sxs-lookup"><span data-stu-id="3caf5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3caf5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3caf5-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="3caf5-106">からデバッガーが実行を停止するマップされていないコードの種類を指定する CorDebugUnmappedStop 列挙値。</span><span class="sxs-lookup"><span data-stu-id="3caf5-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="3caf5-107">既定値は STOP_OTHER_UNMAPPED です。</span><span class="sxs-lookup"><span data-stu-id="3caf5-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="3caf5-108">値 STOP_UNMANAGED は、相互運用機能デバッグでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="3caf5-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3caf5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3caf5-109">Remarks</span></span>  
 <span data-ttu-id="3caf5-110">デバッガーは、Microsoft 中間言語 (MSIL) への対応するマッピングがない just-in-time (JIT) コンパイルを検出すると、マップされていないコードの型を指定するフラグが設定されている場合、実行を停止します。それ以外の場合、ステップ実行は透過的に続行されます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="3caf5-111">デバッガーがステッパを使用してメソッドを入力しない場合、マップされていないコードは必ずしもステップオーバーされません。</span><span class="sxs-lookup"><span data-stu-id="3caf5-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3caf5-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="3caf5-112">Requirements</span></span>  
 <span data-ttu-id="3caf5-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3caf5-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3caf5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3caf5-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3caf5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3caf5-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3caf5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
