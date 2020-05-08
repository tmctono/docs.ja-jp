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
ms.openlocfilehash: b92c3d3328c657762ed002155ef4947a9292b19e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894726"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="8a3eb-102">ICorDebugBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a3eb-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="8a3eb-103">関数内のブレークポイント、または値のウォッチポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a3eb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a3eb-104">Methods</span></span>  
  
|<span data-ttu-id="8a3eb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a3eb-105">Method</span></span>|<span data-ttu-id="8a3eb-106">説明</span><span class="sxs-lookup"><span data-stu-id="8a3eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a3eb-107">Activate メソッド</span><span class="sxs-lookup"><span data-stu-id="8a3eb-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="8a3eb-108">この`ICorDebugBreakpoint`のアクティブな状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="8a3eb-109">IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="8a3eb-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="8a3eb-110">この`ICorDebugBreakpoint`がアクティブかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a3eb-111">解説</span><span class="sxs-lookup"><span data-stu-id="8a3eb-111">Remarks</span></span>  
 <span data-ttu-id="8a3eb-112">ブレークポイントは、条件式を直接サポートしません。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="8a3eb-113">このような機能が必要な場合は、デバッガーでを上`ICorDebugBreakpoint`に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="8a3eb-114">は、関数内のブレーク`ICorDebugBreakpoint`ポイントをサポートするために、によって拡張されます。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a3eb-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3eb-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a3eb-116">Requirements</span></span>  
 <span data-ttu-id="8a3eb-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a3eb-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3eb-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a3eb-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a3eb-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a3eb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a3eb-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3eb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3eb-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a3eb-121">See also</span></span>

- [<span data-ttu-id="8a3eb-122">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a3eb-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
