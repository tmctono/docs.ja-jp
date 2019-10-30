---
title: ICorDebugFrame::CreateStepper メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 6ea2b24d37f56a5cb9e6b3dea0d666c8acc719dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091028"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="e5ad0-102">ICorDebugFrame::CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="e5ad0-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="e5ad0-103">デバッガーがこのテキストフレームに対して相対的なステップ実行操作を実行できるようにするステッパを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5ad0-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ad0-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5ad0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5ad0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5ad0-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="e5ad0-106">入出力デバッガーが現在のフレームに対して相対的なステップ実行操作を実行できるようにする ICorDebugStepper オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e5ad0-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5ad0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5ad0-107">Remarks</span></span>  
 <span data-ttu-id="e5ad0-108">フレームがアクティブでない場合、通常、ステッパオブジェクトは、手順が完了する前にフレームに戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5ad0-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ad0-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="e5ad0-109">Requirements</span></span>  
 <span data-ttu-id="e5ad0-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5ad0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5ad0-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5ad0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5ad0-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5ad0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5ad0-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5ad0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
