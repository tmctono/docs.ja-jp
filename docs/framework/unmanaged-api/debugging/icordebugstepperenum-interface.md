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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89552a099241f1bec61f9aa8a8321ef9932e886c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173226"
---
# <a name="icordebugstepperenum-interface"></a><span data-ttu-id="c6c15-102">ICorDebugStepperEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6c15-102">ICorDebugStepperEnum Interface</span></span>
<span data-ttu-id="c6c15-103">ICorDebugEnum のメソッドを実装し、ICorDebugStepper 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="c6c15-103">Implements ICorDebugEnum methods, and enumerates ICorDebugStepper arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6c15-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c6c15-104">Methods</span></span>  
  
|<span data-ttu-id="c6c15-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c6c15-105">Method</span></span>|<span data-ttu-id="c6c15-106">説明</span><span class="sxs-lookup"><span data-stu-id="c6c15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6c15-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="c6c15-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|<span data-ttu-id="c6c15-108">指定した数を取得`ICorDebugStepper`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="c6c15-108">Gets the specified number of `ICorDebugStepper` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6c15-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6c15-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6c15-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c6c15-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c15-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6c15-111">Requirements</span></span>  
 <span data-ttu-id="c6c15-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6c15-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c15-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6c15-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6c15-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6c15-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c6c15-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c6c15-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6c15-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6c15-116">See also</span></span>

- [<span data-ttu-id="c6c15-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6c15-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
