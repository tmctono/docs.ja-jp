---
title: ICorDebugInternalFrame2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
ms.openlocfilehash: 5a451218e0fdc32132a4e79d091ada8355d32fe7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122693"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="72e02-102">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72e02-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="72e02-103">スタックアドレスや、テキストフレームオブジェクトに対する位置など、内部フレームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="72e02-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72e02-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="72e02-104">Methods</span></span>  
  
|<span data-ttu-id="72e02-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="72e02-105">Method</span></span>|<span data-ttu-id="72e02-106">説明</span><span class="sxs-lookup"><span data-stu-id="72e02-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72e02-107">GetFrameAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="72e02-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="72e02-108">内部フレームのスタックアドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="72e02-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="72e02-109">IsCloserToLeaf メソッド</span><span class="sxs-lookup"><span data-stu-id="72e02-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="72e02-110">`this` 内部フレームが、指定されたは、指定されたテキストボックスオブジェクトよりもリーフに近いかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="72e02-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72e02-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="72e02-111">Remarks</span></span>  
 <span data-ttu-id="72e02-112">このインターフェイスは、によって、、の各フレームインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="72e02-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72e02-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="72e02-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72e02-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="72e02-114">Requirements</span></span>  
 <span data-ttu-id="72e02-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72e02-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72e02-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72e02-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72e02-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72e02-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72e02-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72e02-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e02-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="72e02-119">See also</span></span>

- [<span data-ttu-id="72e02-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72e02-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="72e02-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="72e02-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
