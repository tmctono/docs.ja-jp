---
title: ICorDebugHeapValue2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2
helpviewer_keywords:
- ICorDebugHeapValue2 interface [.NET Framework debugging]
ms.assetid: 87360a52-90b1-4ada-80c0-589a556116d8
topic_type:
- apiref
ms.openlocfilehash: d7126222bd23548ec7013ba234c3f3eebbc8e374
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788632"
---
# <a name="icordebugheapvalue2-interface"></a><span data-ttu-id="2d1b9-102">ICorDebugHeapValue2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d1b9-102">ICorDebugHeapValue2 Interface</span></span>

<span data-ttu-id="2d1b9-103">共通言語ランタイム (CLR) ハンドルのサポートを提供する、コンポーネントの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="2d1b9-103">An extension of ICorDebugHeapValue that provides support for common language runtime (CLR) handles.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d1b9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d1b9-104">Methods</span></span>  
  
|<span data-ttu-id="2d1b9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d1b9-105">Method</span></span>|<span data-ttu-id="2d1b9-106">説明</span><span class="sxs-lookup"><span data-stu-id="2d1b9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d1b9-107">CreateHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="2d1b9-107">CreateHandle Method</span></span>](icordebugheapvalue2-createhandle-method.md)|<span data-ttu-id="2d1b9-108">この `ICorDebugHeapValue2` オブジェクトに対して指定された型のハンドルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d1b9-108">Creates a handle of the specified type for this `ICorDebugHeapValue2` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d1b9-109">コメント</span><span class="sxs-lookup"><span data-stu-id="2d1b9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d1b9-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2d1b9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d1b9-111">要件</span><span class="sxs-lookup"><span data-stu-id="2d1b9-111">Requirements</span></span>  
 <span data-ttu-id="2d1b9-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d1b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d1b9-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d1b9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d1b9-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d1b9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d1b9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d1b9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1b9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d1b9-116">See also</span></span>

- [<span data-ttu-id="2d1b9-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d1b9-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
