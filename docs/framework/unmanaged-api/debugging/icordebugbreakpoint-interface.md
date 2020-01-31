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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784374"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="0eec9-102">ICorDebugBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0eec9-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="0eec9-103">関数内のブレークポイント、または値のウォッチポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="0eec9-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0eec9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0eec9-104">Methods</span></span>  
  
|<span data-ttu-id="0eec9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0eec9-105">Method</span></span>|<span data-ttu-id="0eec9-106">説明</span><span class="sxs-lookup"><span data-stu-id="0eec9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0eec9-107">Activate メソッド</span><span class="sxs-lookup"><span data-stu-id="0eec9-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="0eec9-108">この `ICorDebugBreakpoint`のアクティブな状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="0eec9-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="0eec9-109">IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="0eec9-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="0eec9-110">この `ICorDebugBreakpoint` がアクティブかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0eec9-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eec9-111">コメント</span><span class="sxs-lookup"><span data-stu-id="0eec9-111">Remarks</span></span>  
 <span data-ttu-id="0eec9-112">ブレークポイントは、条件式を直接サポートしません。</span><span class="sxs-lookup"><span data-stu-id="0eec9-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="0eec9-113">このような機能が必要な場合は、デバッガーが `ICorDebugBreakpoint`上に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0eec9-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="0eec9-114">は、関数内のブレークポイントをサポートするために `ICorDebugBreakpoint` を拡張します。</span><span class="sxs-lookup"><span data-stu-id="0eec9-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0eec9-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0eec9-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eec9-116">要件</span><span class="sxs-lookup"><span data-stu-id="0eec9-116">Requirements</span></span>  
 <span data-ttu-id="0eec9-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0eec9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eec9-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eec9-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eec9-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eec9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eec9-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eec9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eec9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0eec9-121">See also</span></span>

- [<span data-ttu-id="0eec9-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0eec9-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
