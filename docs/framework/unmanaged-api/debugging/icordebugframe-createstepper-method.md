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
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205446"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="8a5c1-102">ICorDebugFrame::CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="8a5c1-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="8a5c1-103">デバッガーがこのテキストフレームに対して相対的なステップ実行操作を実行できるようにするステッパを取得します。</span><span class="sxs-lookup"><span data-stu-id="8a5c1-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a5c1-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a5c1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a5c1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a5c1-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="8a5c1-106">入出力デバッガーが現在のフレームに対して相対的なステップ実行操作を実行できるようにする ICorDebugStepper オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8a5c1-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a5c1-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a5c1-107">Remarks</span></span>  
 <span data-ttu-id="8a5c1-108">フレームがアクティブでない場合、通常、ステッパオブジェクトは、手順が完了する前にフレームに戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a5c1-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a5c1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a5c1-109">Requirements</span></span>  
 <span data-ttu-id="8a5c1-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a5c1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a5c1-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a5c1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a5c1-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a5c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a5c1-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a5c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
