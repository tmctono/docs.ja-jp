---
title: ICorDebugStepperEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
ms.openlocfilehash: feaf5bd25e276bb93c076f200912965c612af453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138995"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="2624a-102">ICorDebugStepperEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2624a-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="2624a-103">ICorDebugEnum メソッドを実装し、ICorDebugStepper 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="2624a-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2624a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2624a-104">Methods</span></span>  
  
|<span data-ttu-id="2624a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2624a-105">Method</span></span>|<span data-ttu-id="2624a-106">説明</span><span class="sxs-lookup"><span data-stu-id="2624a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2624a-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="2624a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="2624a-108">現在の位置から開始して、指定した数の `ICorDebugStepper` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="2624a-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2624a-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2624a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2624a-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2624a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2624a-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="2624a-111">Requirements</span></span>  
 <span data-ttu-id="2624a-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2624a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2624a-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2624a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2624a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2624a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2624a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2624a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2624a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2624a-116">See also</span></span>

- [<span data-ttu-id="2624a-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2624a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
