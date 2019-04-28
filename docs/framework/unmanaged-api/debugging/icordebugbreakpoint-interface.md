---
title: ICorDebugBreakpoint インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a68e061c6def61746ee65f8a25818f8dbcd785b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645358"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="d079c-102">ICorDebugBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d079c-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="d079c-103">関数、または値のウォッチ ポイントでのブレークポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="d079c-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d079c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d079c-104">Methods</span></span>  
  
|<span data-ttu-id="d079c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d079c-105">Method</span></span>|<span data-ttu-id="d079c-106">説明</span><span class="sxs-lookup"><span data-stu-id="d079c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d079c-107">Activate メソッド</span><span class="sxs-lookup"><span data-stu-id="d079c-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="d079c-108">このアクティブな状態を設定`ICorDebugBreakpoint`します。</span><span class="sxs-lookup"><span data-stu-id="d079c-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="d079c-109">IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="d079c-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="d079c-110">示す値を取得するかどうかこの`ICorDebugBreakpoint`がアクティブです。</span><span class="sxs-lookup"><span data-stu-id="d079c-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d079c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="d079c-111">Remarks</span></span>  
 <span data-ttu-id="d079c-112">ブレークポイントは、条件式を直接はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d079c-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="d079c-113">デバッガーがの上で実装する必要がありますこのような機能を使用する場合は、`ICorDebugBreakpoint`します。</span><span class="sxs-lookup"><span data-stu-id="d079c-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="d079c-114">ICorDebugFunctionBreakpoint インターフェイスは、拡張`ICorDebugBreakpoint`関数内のブレークポイントをサポートするためにします。</span><span class="sxs-lookup"><span data-stu-id="d079c-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d079c-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d079c-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d079c-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="d079c-116">Requirements</span></span>  
 <span data-ttu-id="d079c-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d079c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d079c-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d079c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d079c-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d079c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d079c-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d079c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d079c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d079c-121">See also</span></span>

- [<span data-ttu-id="d079c-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d079c-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
