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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185875"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="35a3e-102">ICorDebugThread3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35a3e-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="35a3e-103">エントリ ポイントを提供します、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)と対応するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="35a3e-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35a3e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="35a3e-104">Methods</span></span>  
  
|<span data-ttu-id="35a3e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="35a3e-105">Method</span></span>|<span data-ttu-id="35a3e-106">説明</span><span class="sxs-lookup"><span data-stu-id="35a3e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35a3e-107">CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="35a3e-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="35a3e-108">作成、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)がスタックをアンワインドするスレッドのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="35a3e-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="35a3e-109">GetActiveInternalFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="35a3e-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="35a3e-110">内部フレームの配列を返します ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)オブジェクト)、スタックにします。</span><span class="sxs-lookup"><span data-stu-id="35a3e-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35a3e-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="35a3e-111">Remarks</span></span>  
 <span data-ttu-id="35a3e-112">`ICorDebugThread3` ICorDebugThread インターフェイスを論理的な拡張です。</span><span class="sxs-lookup"><span data-stu-id="35a3e-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35a3e-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="35a3e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a3e-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="35a3e-114">Requirements</span></span>  
 <span data-ttu-id="35a3e-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35a3e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a3e-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35a3e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35a3e-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35a3e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35a3e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a3e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a3e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="35a3e-119">See also</span></span>

- [<span data-ttu-id="35a3e-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35a3e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="35a3e-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="35a3e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
