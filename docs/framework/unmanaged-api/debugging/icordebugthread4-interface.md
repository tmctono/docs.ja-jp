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
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791335"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="039b7-102">ICorDebugThread4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="039b7-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="039b7-103">スレッドのブロック情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="039b7-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="039b7-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="039b7-104">Methods</span></span>  
  
|<span data-ttu-id="039b7-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="039b7-105">Method</span></span>|<span data-ttu-id="039b7-106">説明</span><span class="sxs-lookup"><span data-stu-id="039b7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="039b7-107">GetBlockingObjects メソッド</span><span class="sxs-lookup"><span data-stu-id="039b7-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="039b7-108">スレッドブロック情報を提供する[CorDebugBlockingObject](cordebugblockingobject-structure.md)構造体の順序付けられた列挙体を提供します。</span><span class="sxs-lookup"><span data-stu-id="039b7-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="039b7-109">HadUnhandledException メソッド</span><span class="sxs-lookup"><span data-stu-id="039b7-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="039b7-110">スレッドで未処理の例外が発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="039b7-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="039b7-111">GetCurrentCustomDebuggerNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="039b7-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="039b7-112">現在のスレッドの現在の[ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md)オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="039b7-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="039b7-113">コメント</span><span class="sxs-lookup"><span data-stu-id="039b7-113">Remarks</span></span>  
 <span data-ttu-id="039b7-114">このインターフェイスは、ICorDebugThread2、 [ICorDebugThread3](icordebugthread3-interface.md)の各インターフェイスの論理的な拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="039b7-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="039b7-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="039b7-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="039b7-116">要件</span><span class="sxs-lookup"><span data-stu-id="039b7-116">Requirements</span></span>  
 <span data-ttu-id="039b7-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="039b7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="039b7-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="039b7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="039b7-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="039b7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="039b7-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="039b7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="039b7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="039b7-121">See also</span></span>

- [<span data-ttu-id="039b7-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="039b7-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="039b7-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="039b7-123">Debugging</span></span>](index.md)
