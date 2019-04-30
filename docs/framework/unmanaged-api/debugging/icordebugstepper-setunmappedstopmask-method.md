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
ms.openlocfilehash: da799b0d4f4e5e4b281445baa35d95f992ba0b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987455"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="1891c-102">ICorDebugStepper::SetUnmappedStopMask メソッド</span><span class="sxs-lookup"><span data-stu-id="1891c-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="1891c-103">マップされていないコードが実行を中断の種類を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1891c-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1891c-104">構文</span><span class="sxs-lookup"><span data-stu-id="1891c-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1891c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1891c-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="1891c-106">[in]デバッガーが実行を停止がマップされていないコードの種類を指定する CorDebugUnmappedStop 列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="1891c-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="1891c-107">既定値は、STOP_OTHER_UNMAPPED です。</span><span class="sxs-lookup"><span data-stu-id="1891c-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="1891c-108">STOP_UNMANAGED 値は相互運用機能デバッグでのみです。</span><span class="sxs-lookup"><span data-stu-id="1891c-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1891c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1891c-109">Remarks</span></span>  
 <span data-ttu-id="1891c-110">マップされていないコードの種類を指定するフラグが設定されている場合は、実行を停止、デバッガーには、Microsoft intermediate language (MSIL) に対応するマッピングされていないこと、ジャストイン タイム (JIT) コンパイルが検出されると、それ以外の場合、透過的にステップ実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="1891c-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="1891c-111">場合は、デバッガーは、ステッパを使用して、メソッドの入力は、マップされていないコードをステップしないとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1891c-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1891c-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="1891c-112">Requirements</span></span>  
 <span data-ttu-id="1891c-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1891c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1891c-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1891c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1891c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1891c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1891c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1891c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
