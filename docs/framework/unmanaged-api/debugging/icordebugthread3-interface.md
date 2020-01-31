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
ms.openlocfilehash: 19bd869aec7e4d046890d2314f5142753ba0b112
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791385"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="da12e-102">ICorDebugThread3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da12e-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="da12e-103">とそれに対応するインターフェイス[へのエントリ](icordebugstackwalk-interface.md)ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="da12e-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da12e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="da12e-104">Methods</span></span>  
  
|<span data-ttu-id="da12e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="da12e-105">Method</span></span>|<span data-ttu-id="da12e-106">説明</span><span class="sxs-lookup"><span data-stu-id="da12e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da12e-107">CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="da12e-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="da12e-108">スタックをアンワインドするスレッドに対し[て、このオブジェクトを](icordebugstackwalk-interface.md)作成します。</span><span class="sxs-lookup"><span data-stu-id="da12e-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="da12e-109">GetActiveInternalFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="da12e-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="da12e-110">スタック上の内部フレーム ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="da12e-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da12e-111">コメント</span><span class="sxs-lookup"><span data-stu-id="da12e-111">Remarks</span></span>  
 <span data-ttu-id="da12e-112">`ICorDebugThread3` は、のように、のような論理上の拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="da12e-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da12e-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="da12e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da12e-114">要件</span><span class="sxs-lookup"><span data-stu-id="da12e-114">Requirements</span></span>  
 <span data-ttu-id="da12e-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da12e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da12e-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da12e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da12e-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da12e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da12e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da12e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da12e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="da12e-119">See also</span></span>

- [<span data-ttu-id="da12e-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da12e-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="da12e-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="da12e-121">Debugging</span></span>](index.md)
