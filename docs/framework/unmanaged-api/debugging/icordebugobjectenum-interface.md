---
title: ICorDebugObjectEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: b77d5859986c90d6ef61c02547014d0bec354106
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096141"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="1718a-102">ICorDebugObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1718a-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="1718a-103">ICorDebugEnum メソッドを実装し、相対仮想アドレス (RVAs) によってオブジェクトの配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="1718a-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1718a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="1718a-104">Methods</span></span>  
  
|<span data-ttu-id="1718a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1718a-105">Method</span></span>|<span data-ttu-id="1718a-106">説明</span><span class="sxs-lookup"><span data-stu-id="1718a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1718a-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="1718a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="1718a-108">現在の位置から開始して、指定した数のオブジェクトの RVAs を列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="1718a-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1718a-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1718a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1718a-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1718a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1718a-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="1718a-111">Requirements</span></span>  
 <span data-ttu-id="1718a-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1718a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1718a-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1718a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1718a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1718a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1718a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1718a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1718a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1718a-116">See also</span></span>

- [<span data-ttu-id="1718a-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1718a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
