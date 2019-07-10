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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b577e915422814fbd0060fdda53b9e2bf7cd091a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760730"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="8d531-102">ICorDebugStepper::Deactivate メソッド</span><span class="sxs-lookup"><span data-stu-id="8d531-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="8d531-103">Icordebugstepper にすると、受信した最後の手順のコマンドをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="8d531-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d531-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d531-104">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8d531-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d531-105">Remarks</span></span>  
 <span data-ttu-id="8d531-106">最後に受信したステップ コマンドが取り消された後、新しいステップ実行コマンドを発行できます。</span><span class="sxs-lookup"><span data-stu-id="8d531-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d531-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="8d531-107">Requirements</span></span>  
 <span data-ttu-id="8d531-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d531-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d531-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d531-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d531-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d531-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d531-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d531-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
