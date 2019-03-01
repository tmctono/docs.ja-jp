---
title: ICorDebugBreakpointEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b5268eb4240f7c3ff254f4d3d9a13ab494530a1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968739"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="b9d66-102">ICorDebugBreakpointEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9d66-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="b9d66-103">ICorDebugEnum のメソッドを実装し、ICorDebugBreakpoint 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="b9d66-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9d66-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b9d66-104">Methods</span></span>  
  
|<span data-ttu-id="b9d66-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b9d66-105">Method</span></span>|<span data-ttu-id="b9d66-106">説明</span><span class="sxs-lookup"><span data-stu-id="b9d66-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9d66-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="b9d66-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="b9d66-108">指定した数を取得`ICorDebugBreakpoint`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="b9d66-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9d66-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9d66-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9d66-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b9d66-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9d66-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9d66-111">Requirements</span></span>  
 <span data-ttu-id="b9d66-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9d66-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9d66-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9d66-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9d66-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9d66-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9d66-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9d66-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d66-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9d66-116">See also</span></span>
- [<span data-ttu-id="b9d66-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b9d66-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
