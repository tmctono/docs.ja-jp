---
title: ICorDebugController::Detach メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f687e48413cb227ad715720e24bd645065309553
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748843"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="ccbae-102">ICorDebugController::Detach メソッド</span><span class="sxs-lookup"><span data-stu-id="ccbae-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="ccbae-103">プロセスまたはアプリケーション ドメインからデバッガーをデタッチします。</span><span class="sxs-lookup"><span data-stu-id="ccbae-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbae-104">構文</span><span class="sxs-lookup"><span data-stu-id="ccbae-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ccbae-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="ccbae-105">Remarks</span></span>  
 <span data-ttu-id="ccbae-106">プロセスまたはアプリケーション ドメインは通常、実行を継続し、"ICorDebugProcess"または"ICorDebugAppDomain"オブジェクトが無効になってがさらにコールバックが行われません。</span><span class="sxs-lookup"><span data-stu-id="ccbae-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="ccbae-107">.NET framework version 2.0 では、アンマネージ デバッグが有効になっている場合は、このメソッドはオペレーティング システムの制限により失敗します。</span><span class="sxs-lookup"><span data-stu-id="ccbae-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccbae-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ccbae-108">Requirements</span></span>  
 <span data-ttu-id="ccbae-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccbae-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccbae-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccbae-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccbae-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccbae-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccbae-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccbae-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccbae-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccbae-113">See also</span></span>
