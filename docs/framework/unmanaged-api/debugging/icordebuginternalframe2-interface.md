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
ms.openlocfilehash: ce3ca4745727a1738fdc1a526480d70ffc55ccf8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209904"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="71547-102">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71547-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="71547-103">内部フレームに関する情報を提供します。この情報には、スタック アドレス、および ICorDebugFrame オブジェクトを基準にした位置などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71547-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71547-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="71547-104">Methods</span></span>  
  
|<span data-ttu-id="71547-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="71547-105">Method</span></span>|<span data-ttu-id="71547-106">説明</span><span class="sxs-lookup"><span data-stu-id="71547-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71547-107">GetFrameAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="71547-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="71547-108">内部フレームのスタックアドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="71547-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="71547-109">IsCloserToLeaf メソッド</span><span class="sxs-lookup"><span data-stu-id="71547-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="71547-110">内部フレームが、指定されたのは、指定されたとしての `this` オブジェクトよりもリーフの近くにあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="71547-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71547-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="71547-111">Remarks</span></span>  
 <span data-ttu-id="71547-112">このインターフェイスは、によって、、の各フレームインターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="71547-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71547-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="71547-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71547-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="71547-114">Requirements</span></span>  
 <span data-ttu-id="71547-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71547-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71547-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71547-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71547-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71547-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71547-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71547-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71547-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="71547-119">See also</span></span>

- [<span data-ttu-id="71547-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="71547-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="71547-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="71547-121">Debugging</span></span>](index.md)
