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
ms.openlocfilehash: 9e333d71505a055cfe27df2c79a102c939bafc9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788474"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="fe682-102">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe682-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="fe682-103">内部フレームに関する情報を提供します。この情報には、スタック アドレス、および ICorDebugFrame オブジェクトを基準にした位置などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe682-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe682-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fe682-104">Methods</span></span>  
  
|<span data-ttu-id="fe682-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fe682-105">Method</span></span>|<span data-ttu-id="fe682-106">説明</span><span class="sxs-lookup"><span data-stu-id="fe682-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe682-107">GetFrameAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="fe682-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="fe682-108">内部フレームのスタックアドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="fe682-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="fe682-109">IsCloserToLeaf メソッド</span><span class="sxs-lookup"><span data-stu-id="fe682-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="fe682-110">`this` 内部フレームが、指定されたは、指定されたテキストボックスオブジェクトよりもリーフに近いかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe682-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe682-111">コメント</span><span class="sxs-lookup"><span data-stu-id="fe682-111">Remarks</span></span>  
 <span data-ttu-id="fe682-112">このインターフェイスは、によって、、の各フレームインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="fe682-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe682-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fe682-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe682-114">要件</span><span class="sxs-lookup"><span data-stu-id="fe682-114">Requirements</span></span>  
 <span data-ttu-id="fe682-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe682-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe682-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe682-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe682-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe682-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe682-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe682-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe682-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe682-119">See also</span></span>

- [<span data-ttu-id="fe682-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe682-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fe682-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fe682-121">Debugging</span></span>](index.md)
