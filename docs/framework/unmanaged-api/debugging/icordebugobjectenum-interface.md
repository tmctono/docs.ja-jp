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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1faa78150659b4397cd4174583b607e1f7841b8f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943357"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="70de9-102">ICorDebugObjectEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70de9-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="70de9-103">ICorDebugEnum メソッドを実装し、相対仮想アドレス (RVAs) によってオブジェクトの配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="70de9-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70de9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="70de9-104">Methods</span></span>  
  
|<span data-ttu-id="70de9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="70de9-105">Method</span></span>|<span data-ttu-id="70de9-106">説明</span><span class="sxs-lookup"><span data-stu-id="70de9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70de9-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="70de9-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="70de9-108">現在の位置から開始して、指定した数のオブジェクトの RVAs を列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="70de9-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70de9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="70de9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70de9-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="70de9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70de9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="70de9-111">Requirements</span></span>  
 <span data-ttu-id="70de9-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70de9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70de9-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="70de9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70de9-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="70de9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70de9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70de9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70de9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="70de9-116">See also</span></span>

- [<span data-ttu-id="70de9-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70de9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
