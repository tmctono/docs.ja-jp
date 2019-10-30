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
ms.openlocfilehash: 7cddf860f044e8493a0fdf6023b2853ac16c5b14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137503"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="dd204-102">ICorDebugThread3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd204-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="dd204-103">とそれに対応するインターフェイス[へのエントリ](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="dd204-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd204-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="dd204-104">Methods</span></span>  
  
|<span data-ttu-id="dd204-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dd204-105">Method</span></span>|<span data-ttu-id="dd204-106">説明</span><span class="sxs-lookup"><span data-stu-id="dd204-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd204-107">CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="dd204-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="dd204-108">スタックをアンワインドするスレッドに対し[て、このオブジェクトを](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)作成します。</span><span class="sxs-lookup"><span data-stu-id="dd204-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="dd204-109">GetActiveInternalFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="dd204-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="dd204-110">スタック上の内部フレーム ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="dd204-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd204-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd204-111">Remarks</span></span>  
 <span data-ttu-id="dd204-112">`ICorDebugThread3` は、のように、のような論理上の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="dd204-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd204-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="dd204-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd204-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="dd204-114">Requirements</span></span>  
 <span data-ttu-id="dd204-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd204-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd204-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd204-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd204-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd204-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd204-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd204-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd204-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd204-119">See also</span></span>

- [<span data-ttu-id="dd204-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd204-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="dd204-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="dd204-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
