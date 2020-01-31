---
title: ICorDebug::Terminate メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 2d3f8360a1fb1164fd4e26f85246251409bee376
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788961"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="8a3ea-102">ICorDebug::Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="8a3ea-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="8a3ea-103">`ICorDebug` オブジェクトを終了します。</span><span class="sxs-lookup"><span data-stu-id="8a3ea-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a3ea-104">デバッグ中のすべてのプロセスに対して、 [ExitProcess callback::](icordebugmanagedcallback-exitprocess-method.md)コールバックを受信するまでは、`Terminate` を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8a3ea-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3ea-105">構文</span><span class="sxs-lookup"><span data-stu-id="8a3ea-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8a3ea-106">コメント</span><span class="sxs-lookup"><span data-stu-id="8a3ea-106">Remarks</span></span>  
 <span data-ttu-id="8a3ea-107">`ICorDebug` オブジェクトが不要になった場合は、`Terminate` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a3ea-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3ea-108">要件</span><span class="sxs-lookup"><span data-stu-id="8a3ea-108">Requirements</span></span>  
 <span data-ttu-id="8a3ea-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a3ea-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3ea-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a3ea-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a3ea-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a3ea-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a3ea-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3ea-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3ea-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a3ea-113">See also</span></span>

- [<span data-ttu-id="8a3ea-114">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a3ea-114">ICorDebug Interface</span></span>](icordebug-interface.md)
