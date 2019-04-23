---
title: ICorDebugManagedCallback3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acab49097059081540ec364d7f134d31432988a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108278"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="c6af7-102">ICorDebugManagedCallback3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6af7-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="c6af7-103">有効なカスタムのデバッガー通知が発生したことを示すコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6af7-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6af7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c6af7-104">Methods</span></span>  
  
|<span data-ttu-id="c6af7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c6af7-105">Method</span></span>|<span data-ttu-id="c6af7-106">説明</span><span class="sxs-lookup"><span data-stu-id="c6af7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6af7-107">CustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="c6af7-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="c6af7-108">有効になっているカスタムのデバッガー通知が発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c6af7-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6af7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6af7-109">Remarks</span></span>  
 <span data-ttu-id="c6af7-110">このインターフェイスはの論理拡張機能、 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)と[ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="c6af7-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6af7-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c6af7-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6af7-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6af7-112">Requirements</span></span>  
 <span data-ttu-id="c6af7-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6af7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6af7-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6af7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6af7-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6af7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6af7-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6af7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6af7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6af7-117">See also</span></span>

- [<span data-ttu-id="c6af7-118">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6af7-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="c6af7-119">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6af7-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="c6af7-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6af7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c6af7-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c6af7-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
