---
title: ICorDebugThread4 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d66a1aed1936d0146d42c8e4a5ad06dfa39c802
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962961"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="29e16-102">ICorDebugThread4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29e16-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="29e16-103">スレッドのブロック情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="29e16-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29e16-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="29e16-104">Methods</span></span>  
  
|<span data-ttu-id="29e16-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="29e16-105">Method</span></span>|<span data-ttu-id="29e16-106">説明</span><span class="sxs-lookup"><span data-stu-id="29e16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29e16-107">GetBlockingObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="29e16-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="29e16-108">スレッドブロック情報を提供する[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体の順序付けられた列挙体を提供します。</span><span class="sxs-lookup"><span data-stu-id="29e16-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="29e16-109">HadUnhandledException メソッド</span><span class="sxs-lookup"><span data-stu-id="29e16-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="29e16-110">スレッドで未処理の例外が発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="29e16-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="29e16-111">GetCurrentCustomDebuggerNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="29e16-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="29e16-112">現在のスレッドの現在の[ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="29e16-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29e16-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="29e16-113">Remarks</span></span>  
 <span data-ttu-id="29e16-114">このインターフェイスは、ICorDebugThread2、 [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)の各インターフェイスの論理的な拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="29e16-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29e16-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="29e16-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29e16-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="29e16-116">Requirements</span></span>  
 <span data-ttu-id="29e16-117">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e16-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29e16-118">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="29e16-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29e16-119">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="29e16-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29e16-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29e16-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e16-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="29e16-121">See also</span></span>

- [<span data-ttu-id="29e16-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29e16-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="29e16-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="29e16-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
