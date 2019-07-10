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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3037fc704ffc3aac4d050cef7857261f138f7d35
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738069"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="8ce21-102">ICorDebug::Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="8ce21-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="8ce21-103">終了、`ICorDebug`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ce21-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ce21-104">`Terminate` まで呼び出すことはできません、 [icordebugmanagedcallback::exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)デバッグ中のすべてのプロセスのコールバックを受け取りました。</span><span class="sxs-lookup"><span data-stu-id="8ce21-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ce21-105">構文</span><span class="sxs-lookup"><span data-stu-id="8ce21-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ce21-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ce21-106">Remarks</span></span>  
 <span data-ttu-id="8ce21-107">`Terminate` ときに呼び出す必要があります、`ICorDebug`オブジェクトが不要です。</span><span class="sxs-lookup"><span data-stu-id="8ce21-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ce21-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ce21-108">Requirements</span></span>  
 <span data-ttu-id="8ce21-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ce21-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ce21-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ce21-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ce21-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ce21-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ce21-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ce21-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce21-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ce21-113">See also</span></span>

- [<span data-ttu-id="8ce21-114">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ce21-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
