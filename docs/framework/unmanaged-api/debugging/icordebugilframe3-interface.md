---
title: ICorDebugILFrame3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: b3094eb6e3006be49cf17c1ca2a220b8ec58b673
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139060"
---
# <a name="icordebugilframe3-interface"></a><span data-ttu-id="b7a18-102">ICorDebugILFrame3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7a18-102">ICorDebugILFrame3 Interface</span></span>
<span data-ttu-id="b7a18-103">関数の戻り値をカプセル化するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b7a18-103">Provides a method that encapsulates the return value of a function.</span></span> <span data-ttu-id="b7a18-104">`ICorDebugILFrame3` は、ICorDebugILFrame2 インターフェイスとインターフェイスを論理的に拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="b7a18-104">`ICorDebugILFrame3` is a logical extension of the ICorDebugILFrame and ICorDebugILFrame2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7a18-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b7a18-105">Methods</span></span>  
  
|<span data-ttu-id="b7a18-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="b7a18-106">Method</span></span>|<span data-ttu-id="b7a18-107">説明</span><span class="sxs-lookup"><span data-stu-id="b7a18-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7a18-108">GetReturnValueForILOffSet メソッド</span><span class="sxs-lookup"><span data-stu-id="b7a18-108">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)|<span data-ttu-id="b7a18-109">関数の戻り値をカプセル化する ICorDebugValue オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="b7a18-109">Gets an ICorDebugValue object that encapsulates the return value of a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a18-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7a18-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7a18-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b7a18-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7a18-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="b7a18-112">Requirements</span></span>  
 <span data-ttu-id="b7a18-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7a18-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a18-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7a18-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7a18-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7a18-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7a18-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a18-116">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a18-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7a18-117">See also</span></span>

- [<span data-ttu-id="b7a18-118">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7a18-118">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="b7a18-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7a18-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
