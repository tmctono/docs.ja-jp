---
title: ICorDebugThread3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d34a3395605505ca0ebda072e33d8083d51123a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902422"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="56de9-102">ICorDebugThread3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56de9-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="56de9-103">エントリ ポイントを提供します、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)と対応するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="56de9-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56de9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="56de9-104">Methods</span></span>  
  
|<span data-ttu-id="56de9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="56de9-105">Method</span></span>|<span data-ttu-id="56de9-106">説明</span><span class="sxs-lookup"><span data-stu-id="56de9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56de9-107">CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="56de9-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="56de9-108">作成、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)がスタックをアンワインドするスレッドのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56de9-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="56de9-109">GetActiveInternalFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="56de9-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="56de9-110">内部フレームの配列を返します ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)オブジェクト)、スタックにします。</span><span class="sxs-lookup"><span data-stu-id="56de9-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56de9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="56de9-111">Remarks</span></span>  
 <span data-ttu-id="56de9-112">`ICorDebugThread3` ICorDebugThread インターフェイスを論理的な拡張です。</span><span class="sxs-lookup"><span data-stu-id="56de9-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56de9-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="56de9-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56de9-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="56de9-114">Requirements</span></span>  
 <span data-ttu-id="56de9-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56de9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56de9-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56de9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56de9-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56de9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56de9-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56de9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56de9-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="56de9-119">See also</span></span>

- [<span data-ttu-id="56de9-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56de9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="56de9-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="56de9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
