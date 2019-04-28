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
ms.openlocfilehash: 0f15b9f5961699f905e765426576bdf6f3416793
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651650"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="19099-102">ICorDebugFunctionBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19099-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="19099-103">関数内のブレークポイントをサポートするために ICorDebugBreakpoint インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="19099-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19099-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="19099-104">Methods</span></span>  
  
|<span data-ttu-id="19099-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="19099-105">Method</span></span>|<span data-ttu-id="19099-106">説明</span><span class="sxs-lookup"><span data-stu-id="19099-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19099-107">GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="19099-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="19099-108">ブレークポイントが設定されている関数を参照する、ICorDebugFunction にインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="19099-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="19099-109">GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="19099-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="19099-110">関数内でのブレークポイントのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="19099-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19099-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="19099-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19099-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="19099-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19099-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="19099-113">Requirements</span></span>  
 <span data-ttu-id="19099-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19099-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19099-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19099-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19099-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19099-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19099-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19099-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19099-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="19099-118">See also</span></span>

- [<span data-ttu-id="19099-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19099-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
