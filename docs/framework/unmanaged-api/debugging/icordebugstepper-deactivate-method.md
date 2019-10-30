---
title: ICorDebugStepper::Deactivate メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 1d75897e00c36bd5c484e837ee68e54443168e77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131763"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="655b7-102">ICorDebugStepper::Deactivate メソッド</span><span class="sxs-lookup"><span data-stu-id="655b7-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="655b7-103">この ICorDebugStepper は、受け取った最後のステップコマンドをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="655b7-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="655b7-104">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="655b7-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="655b7-105">Remarks</span></span>  
 <span data-ttu-id="655b7-106">最後に受信したステップコマンドが取り消された後に、新しいステップ実行コマンドが発行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="655b7-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="655b7-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="655b7-107">Requirements</span></span>  
 <span data-ttu-id="655b7-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="655b7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="655b7-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="655b7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="655b7-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="655b7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="655b7-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="655b7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
