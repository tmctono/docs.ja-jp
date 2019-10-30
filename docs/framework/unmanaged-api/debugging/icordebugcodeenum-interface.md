---
title: ICorDebugCodeEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
ms.openlocfilehash: f4baaf5e4f5117ee936fa6d758798c340551c48b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121081"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="7a44c-102">ICorDebugCodeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a44c-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="7a44c-103">"ICorDebugEnum" メソッドを実装し、"コード" 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="7a44c-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a44c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7a44c-104">Methods</span></span>  
  
|<span data-ttu-id="7a44c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7a44c-105">Method</span></span>|<span data-ttu-id="7a44c-106">説明</span><span class="sxs-lookup"><span data-stu-id="7a44c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a44c-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="7a44c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-next-method.md)|<span data-ttu-id="7a44c-108">現在の位置から開始して、指定した数の `ICorDebugCode` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="7a44c-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a44c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a44c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a44c-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7a44c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a44c-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="7a44c-111">Requirements</span></span>  
 <span data-ttu-id="7a44c-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a44c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a44c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a44c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a44c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a44c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a44c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a44c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a44c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a44c-116">See also</span></span>

- [<span data-ttu-id="7a44c-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a44c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
