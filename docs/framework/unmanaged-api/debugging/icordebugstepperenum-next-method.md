---
title: ICorDebugStepperEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
ms.openlocfilehash: 11d9c7393827b613d49e23972b4896bfe657a544
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138981"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="341f5-102">ICorDebugStepperEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="341f5-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="341f5-103">現在の位置から開始して、指定した数の ICorDebugStepper インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="341f5-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="341f5-104">構文</span><span class="sxs-lookup"><span data-stu-id="341f5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="341f5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="341f5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="341f5-106">から取得する `ICorDebugStepper` インスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="341f5-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="341f5-107">入出力ポインターの配列。それぞれが `ICorDebugStepper` オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="341f5-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="341f5-108">入出力実際に返された `ICorDebugStepper` インスタンスの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="341f5-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="341f5-109">`celt` が1の場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="341f5-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="341f5-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="341f5-110">Requirements</span></span>  
 <span data-ttu-id="341f5-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="341f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="341f5-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="341f5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="341f5-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="341f5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="341f5-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="341f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
