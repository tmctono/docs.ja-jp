---
title: ICorDebugAppDomain::Attach メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: 66ec64b1a855a3d31f14f3ef29dde0b82361f5d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133980"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="50088-102">ICorDebugAppDomain::Attach メソッド</span><span class="sxs-lookup"><span data-stu-id="50088-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="50088-103">デバッガーをアプリケーションドメインにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="50088-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50088-104">構文</span><span class="sxs-lookup"><span data-stu-id="50088-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="50088-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="50088-105">Remarks</span></span>  
 <span data-ttu-id="50088-106">イベントを受信し、アプリケーションドメインのデバッグを有効にするには、デバッガーがアプリケーションドメインにアタッチされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50088-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50088-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="50088-107">Requirements</span></span>  
 <span data-ttu-id="50088-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50088-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50088-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50088-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50088-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50088-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50088-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50088-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
