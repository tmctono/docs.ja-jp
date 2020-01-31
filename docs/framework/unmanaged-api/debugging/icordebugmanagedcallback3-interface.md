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
ms.openlocfilehash: b97f29b94ed4fad6892697ca1c7ed4a20c99c03e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793268"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="d7a3c-102">ICorDebugManagedCallback3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7a3c-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="d7a3c-103">有効なカスタムのデバッガー通知が発生したことを示すコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d7a3c-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7a3c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d7a3c-104">Methods</span></span>  
  
|<span data-ttu-id="d7a3c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d7a3c-105">Method</span></span>|<span data-ttu-id="d7a3c-106">説明</span><span class="sxs-lookup"><span data-stu-id="d7a3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7a3c-107">CustomNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="d7a3c-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="d7a3c-108">有効なカスタムデバッガー通知が発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="d7a3c-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7a3c-109">コメント</span><span class="sxs-lookup"><span data-stu-id="d7a3c-109">Remarks</span></span>  
 <span data-ttu-id="d7a3c-110">このインターフェイスは、" [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) [" というインターフェイスを論理的](icordebugmanagedcallback-interface.md)に拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="d7a3c-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a3c-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d7a3c-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a3c-112">要件</span><span class="sxs-lookup"><span data-stu-id="d7a3c-112">Requirements</span></span>  
 <span data-ttu-id="d7a3c-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7a3c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7a3c-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7a3c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7a3c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7a3c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7a3c-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7a3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a3c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7a3c-117">See also</span></span>

- [<span data-ttu-id="d7a3c-118">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7a3c-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="d7a3c-119">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7a3c-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="d7a3c-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7a3c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d7a3c-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d7a3c-121">Debugging</span></span>](index.md)
