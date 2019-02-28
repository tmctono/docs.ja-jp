---
title: ICorDebugFunctionBreakpoint インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c3c11d3b6a6daec7b35377ef24557dd5077af21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977722"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="3afda-102">ICorDebugFunctionBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3afda-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="3afda-103">関数内のブレークポイントをサポートするために ICorDebugBreakpoint インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="3afda-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3afda-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3afda-104">Methods</span></span>  
  
|<span data-ttu-id="3afda-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3afda-105">Method</span></span>|<span data-ttu-id="3afda-106">説明</span><span class="sxs-lookup"><span data-stu-id="3afda-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3afda-107">GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="3afda-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="3afda-108">ブレークポイントが設定されている関数を参照する、ICorDebugFunction にインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3afda-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="3afda-109">GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="3afda-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="3afda-110">関数内でのブレークポイントのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="3afda-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3afda-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="3afda-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3afda-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3afda-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3afda-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="3afda-113">Requirements</span></span>  
 <span data-ttu-id="3afda-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3afda-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3afda-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3afda-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3afda-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3afda-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3afda-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3afda-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3afda-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3afda-118">See also</span></span>
- [<span data-ttu-id="3afda-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3afda-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
