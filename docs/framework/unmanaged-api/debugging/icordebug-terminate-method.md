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
ms.openlocfilehash: 44bb98f54debb129f951cc388fea81ca0f17b20c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895318"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="dcb2f-102">ICorDebug::Terminate メソッド</span><span class="sxs-lookup"><span data-stu-id="dcb2f-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="dcb2f-103">オブジェクトを`ICorDebug`終了します。</span><span class="sxs-lookup"><span data-stu-id="dcb2f-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dcb2f-104">`Terminate`デバッグされているすべてのプロセスに対して、 [ExitProcess Callback callback::](icordebugmanagedcallback-exitprocess-method.md) callback が受信されるまでは呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="dcb2f-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcb2f-105">構文</span><span class="sxs-lookup"><span data-stu-id="dcb2f-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="dcb2f-106">解説</span><span class="sxs-lookup"><span data-stu-id="dcb2f-106">Remarks</span></span>  
 <span data-ttu-id="dcb2f-107">`Terminate`オブジェクトが不要になっ`ICorDebug`た場合は、を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcb2f-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcb2f-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="dcb2f-108">Requirements</span></span>  
 <span data-ttu-id="dcb2f-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcb2f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcb2f-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcb2f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcb2f-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcb2f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcb2f-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcb2f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb2f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcb2f-113">See also</span></span>

- [<span data-ttu-id="dcb2f-114">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dcb2f-114">ICorDebug Interface</span></span>](icordebug-interface.md)
