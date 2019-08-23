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
ms.openlocfilehash: de37bb34aee9b6536ff892ac30855761bcc69445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963129"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="1c427-102">ICorDebug::Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="1c427-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="1c427-103">オブジェクトを`ICorDebug`終了します。</span><span class="sxs-lookup"><span data-stu-id="1c427-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c427-104">`Terminate`デバッグされているすべてのプロセスに対して、 [ExitProcess Callback callback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback が受信されるまでは呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="1c427-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c427-105">構文</span><span class="sxs-lookup"><span data-stu-id="1c427-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c427-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c427-106">Remarks</span></span>  
 <span data-ttu-id="1c427-107">`Terminate`オブジェクトが不要になっ`ICorDebug`た場合は、を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c427-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c427-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="1c427-108">Requirements</span></span>  
 <span data-ttu-id="1c427-109">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c427-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c427-110">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1c427-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c427-111">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="1c427-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c427-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c427-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c427-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c427-113">See also</span></span>

- [<span data-ttu-id="1c427-114">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1c427-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
