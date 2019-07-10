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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0a273c54559e8e297e09740ba9c770ce12d72d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760586"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="ebc0d-102">ICorDebugStepper::SetUnmappedStopMask メソッド</span><span class="sxs-lookup"><span data-stu-id="ebc0d-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="ebc0d-103">マップされていないコードが実行を中断の種類を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="ebc0d-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc0d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ebc0d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebc0d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebc0d-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="ebc0d-106">[in]デバッガーが実行を停止がマップされていないコードの種類を指定する CorDebugUnmappedStop 列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="ebc0d-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="ebc0d-107">既定値は、STOP_OTHER_UNMAPPED です。</span><span class="sxs-lookup"><span data-stu-id="ebc0d-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="ebc0d-108">STOP_UNMANAGED 値は相互運用機能デバッグでのみです。</span><span class="sxs-lookup"><span data-stu-id="ebc0d-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebc0d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ebc0d-109">Remarks</span></span>  
 <span data-ttu-id="ebc0d-110">マップされていないコードの種類を指定するフラグが設定されている場合は、実行を停止、デバッガーには、Microsoft intermediate language (MSIL) に対応するマッピングされていないこと、ジャストイン タイム (JIT) コンパイルが検出されると、それ以外の場合、透過的にステップ実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="ebc0d-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="ebc0d-111">場合は、デバッガーは、ステッパを使用して、メソッドの入力は、マップされていないコードをステップしないとは限りません。</span><span class="sxs-lookup"><span data-stu-id="ebc0d-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc0d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ebc0d-112">Requirements</span></span>  
 <span data-ttu-id="ebc0d-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebc0d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc0d-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebc0d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebc0d-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebc0d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebc0d-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc0d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
