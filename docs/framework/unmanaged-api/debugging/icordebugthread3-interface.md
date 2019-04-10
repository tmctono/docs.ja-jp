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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185875"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="f0dba-102">ICorDebugThread3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0dba-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="f0dba-103">エントリ ポイントを提供します、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)と対応するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f0dba-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0dba-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f0dba-104">Methods</span></span>  
  
|<span data-ttu-id="f0dba-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f0dba-105">Method</span></span>|<span data-ttu-id="f0dba-106">説明</span><span class="sxs-lookup"><span data-stu-id="f0dba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0dba-107">CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="f0dba-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="f0dba-108">作成、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)がスタックをアンワインドするスレッドのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f0dba-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="f0dba-109">GetActiveInternalFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="f0dba-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="f0dba-110">内部フレームの配列を返します ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)オブジェクト)、スタックにします。</span><span class="sxs-lookup"><span data-stu-id="f0dba-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0dba-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0dba-111">Remarks</span></span>  
 `ICorDebugThread3` <span data-ttu-id="f0dba-112">ICorDebugThread インターフェイスを論理的な拡張です。</span><span class="sxs-lookup"><span data-stu-id="f0dba-112">is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0dba-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f0dba-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0dba-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0dba-114">Requirements</span></span>  
 <span data-ttu-id="f0dba-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0dba-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0dba-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0dba-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0dba-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0dba-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f0dba-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="f0dba-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0dba-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0dba-119">See also</span></span>

- [<span data-ttu-id="f0dba-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0dba-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f0dba-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f0dba-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
