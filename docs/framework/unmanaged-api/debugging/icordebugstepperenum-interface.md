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
ms.openlocfilehash: aa0ff0ff7c8fe32f181fb86ee5b778ea618df3b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791700"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="57390-102">ICorDebugStepperEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57390-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="57390-103">ICorDebugEnum メソッドを実装し、ICorDebugStepper 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="57390-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57390-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="57390-104">Methods</span></span>  
  
|<span data-ttu-id="57390-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="57390-105">Method</span></span>|<span data-ttu-id="57390-106">説明</span><span class="sxs-lookup"><span data-stu-id="57390-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57390-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="57390-107">Next Method</span></span>](icordebugstepperenum-next-method.md)|<span data-ttu-id="57390-108">現在の位置から開始して、指定した数の `ICorDebugStepper` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="57390-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57390-109">コメント</span><span class="sxs-lookup"><span data-stu-id="57390-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57390-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="57390-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57390-111">要件</span><span class="sxs-lookup"><span data-stu-id="57390-111">Requirements</span></span>  
 <span data-ttu-id="57390-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57390-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57390-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57390-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57390-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57390-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57390-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57390-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57390-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="57390-116">See also</span></span>

- [<span data-ttu-id="57390-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57390-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
