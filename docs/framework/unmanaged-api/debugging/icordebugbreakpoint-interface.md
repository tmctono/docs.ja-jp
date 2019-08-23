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
ms.openlocfilehash: 608c2cea79c20a43d65fcbf37ba13242fa465100
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969311"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="9e6af-102">ICorDebugBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e6af-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="9e6af-103">関数内のブレークポイント、または値のウォッチポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="9e6af-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e6af-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e6af-104">Methods</span></span>  
  
|<span data-ttu-id="9e6af-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e6af-105">Method</span></span>|<span data-ttu-id="9e6af-106">説明</span><span class="sxs-lookup"><span data-stu-id="9e6af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e6af-107">Activate メソッド</span><span class="sxs-lookup"><span data-stu-id="9e6af-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="9e6af-108">この`ICorDebugBreakpoint`のアクティブな状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="9e6af-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="9e6af-109">IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="9e6af-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="9e6af-110">この`ICorDebugBreakpoint`がアクティブかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9e6af-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e6af-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e6af-111">Remarks</span></span>  
 <span data-ttu-id="9e6af-112">ブレークポイントは、条件式を直接サポートしません。</span><span class="sxs-lookup"><span data-stu-id="9e6af-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="9e6af-113">このような機能が必要な場合は、デバッガーでを上`ICorDebugBreakpoint`に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e6af-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="9e6af-114">は、関数内のブレーク`ICorDebugBreakpoint`ポイントをサポートするために、によって拡張されます。</span><span class="sxs-lookup"><span data-stu-id="9e6af-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e6af-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9e6af-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e6af-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e6af-116">Requirements</span></span>  
 <span data-ttu-id="9e6af-117">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e6af-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e6af-118">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9e6af-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e6af-119">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="9e6af-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e6af-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e6af-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6af-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e6af-121">See also</span></span>

- [<span data-ttu-id="9e6af-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e6af-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
