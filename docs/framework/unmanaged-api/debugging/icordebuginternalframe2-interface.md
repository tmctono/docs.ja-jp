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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cf75de6a71cfbe25cbde281f837060b88e93753
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087236"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="8a88e-102">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a88e-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="8a88e-103">スタックのアドレスと関連 ICorDebugFrame オブジェクトの位置を含む内部フレームに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a88e-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a88e-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a88e-104">Methods</span></span>  
  
|<span data-ttu-id="8a88e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a88e-105">Method</span></span>|<span data-ttu-id="8a88e-106">説明</span><span class="sxs-lookup"><span data-stu-id="8a88e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a88e-107">GetFrameAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="8a88e-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="8a88e-108">内部フレームのスタック アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="8a88e-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="8a88e-109">IsCloserToLeaf メソッド</span><span class="sxs-lookup"><span data-stu-id="8a88e-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="8a88e-110">チェックするかどうか、`this`内部フレームは、指定した ICorDebugFrame オブジェクトよりも、リーフに近いです。</span><span class="sxs-lookup"><span data-stu-id="8a88e-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a88e-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a88e-111">Remarks</span></span>  
 <span data-ttu-id="8a88e-112">このインターフェイスは、ICorDebugInternalFrame インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="8a88e-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a88e-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8a88e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a88e-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a88e-114">Requirements</span></span>  
 <span data-ttu-id="8a88e-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a88e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a88e-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a88e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a88e-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a88e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a88e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a88e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a88e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a88e-119">See also</span></span>

- [<span data-ttu-id="8a88e-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a88e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8a88e-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="8a88e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
