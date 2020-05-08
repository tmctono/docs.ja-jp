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
ms.openlocfilehash: 92cc6c3ce15d8391a43ff130a82476a4363ff5bd
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895307"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="828f4-102">ICorDebugAppDomain::Attach メソッド</span><span class="sxs-lookup"><span data-stu-id="828f4-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="828f4-103">デバッガーをアプリケーションドメインにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="828f4-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="828f4-104">構文</span><span class="sxs-lookup"><span data-stu-id="828f4-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="828f4-105">解説</span><span class="sxs-lookup"><span data-stu-id="828f4-105">Remarks</span></span>  
 <span data-ttu-id="828f4-106">イベントを受信し、アプリケーションドメインのデバッグを有効にするには、デバッガーがアプリケーションドメインにアタッチされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="828f4-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="828f4-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="828f4-107">Requirements</span></span>  
 <span data-ttu-id="828f4-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="828f4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="828f4-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="828f4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="828f4-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="828f4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="828f4-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="828f4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
