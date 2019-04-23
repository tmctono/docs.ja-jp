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
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151802"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="c3447-102">ICorDebugController::Detach メソッド</span><span class="sxs-lookup"><span data-stu-id="c3447-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="c3447-103">プロセスまたはアプリケーション ドメインからデバッガーをデタッチします。</span><span class="sxs-lookup"><span data-stu-id="c3447-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3447-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3447-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c3447-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3447-105">Remarks</span></span>  
 <span data-ttu-id="c3447-106">プロセスまたはアプリケーション ドメインは通常、実行を継続し、"ICorDebugProcess"または"ICorDebugAppDomain"オブジェクトが無効になってがさらにコールバックが行われません。</span><span class="sxs-lookup"><span data-stu-id="c3447-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="c3447-107">.NET framework version 2.0 では、アンマネージ デバッグが有効になっている場合は、このメソッドはオペレーティング システムの制限により失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3447-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3447-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3447-108">Requirements</span></span>  
 <span data-ttu-id="c3447-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3447-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3447-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3447-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3447-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3447-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3447-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3447-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3447-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3447-113">See also</span></span>
