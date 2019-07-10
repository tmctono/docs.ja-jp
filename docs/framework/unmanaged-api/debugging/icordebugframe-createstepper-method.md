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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd105a5cbdb857aaa902e60968ff1d94473259b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754238"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="38377-102">ICorDebugFrame::CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="38377-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="38377-103">この ICorDebugFrame 基準としたステップ実行操作を実行するデバッガーを許可するステッパを取得します。</span><span class="sxs-lookup"><span data-stu-id="38377-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38377-104">構文</span><span class="sxs-lookup"><span data-stu-id="38377-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38377-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38377-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="38377-106">[out]現在のフレームに合わせてステップ実行操作を実行するデバッガーをできるようにする ICorDebugStepper オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="38377-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38377-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="38377-107">Remarks</span></span>  
 <span data-ttu-id="38377-108">フレームがアクティブでない場合、ステッパ オブジェクト通常の手順を完了する前に、フレームに返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="38377-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38377-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="38377-109">Requirements</span></span>  
 <span data-ttu-id="38377-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38377-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38377-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38377-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38377-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38377-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38377-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38377-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
