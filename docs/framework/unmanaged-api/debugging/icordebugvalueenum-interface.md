---
title: ICorDebugValueEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: 4cc9849ee8cd160a33ae9c769f7b98a87eafb8dd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134608"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="19e07-102">ICorDebugValueEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19e07-102">ICorDebugValueEnum Interface</span></span>
<span data-ttu-id="19e07-103">"ICorDebugEnum" メソッドを実装し、"ICorDebugValue" 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="19e07-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19e07-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="19e07-104">Methods</span></span>  
  
|<span data-ttu-id="19e07-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="19e07-105">Method</span></span>|<span data-ttu-id="19e07-106">説明</span><span class="sxs-lookup"><span data-stu-id="19e07-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19e07-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="19e07-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalueenum-next-method.md)|<span data-ttu-id="19e07-108">現在の位置から開始して、指定した数の `ICorDebugValue` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="19e07-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19e07-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="19e07-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19e07-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="19e07-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19e07-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="19e07-111">Requirements</span></span>  
 <span data-ttu-id="19e07-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19e07-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19e07-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19e07-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19e07-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19e07-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19e07-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19e07-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e07-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="19e07-116">See also</span></span>

- [<span data-ttu-id="19e07-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19e07-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
