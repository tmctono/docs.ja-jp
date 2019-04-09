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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159732"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="2ba14-102">ICorDebugBreakpoint インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ba14-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="2ba14-103">関数、または値のウォッチ ポイントでのブレークポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="2ba14-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ba14-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ba14-104">Methods</span></span>  
  
|<span data-ttu-id="2ba14-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ba14-105">Method</span></span>|<span data-ttu-id="2ba14-106">説明</span><span class="sxs-lookup"><span data-stu-id="2ba14-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ba14-107">Activate メソッド</span><span class="sxs-lookup"><span data-stu-id="2ba14-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="2ba14-108">このアクティブな状態を設定`ICorDebugBreakpoint`します。</span><span class="sxs-lookup"><span data-stu-id="2ba14-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="2ba14-109">IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="2ba14-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="2ba14-110">示す値を取得するかどうかこの`ICorDebugBreakpoint`がアクティブです。</span><span class="sxs-lookup"><span data-stu-id="2ba14-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ba14-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ba14-111">Remarks</span></span>  
 <span data-ttu-id="2ba14-112">ブレークポイントは、条件式を直接はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2ba14-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="2ba14-113">デバッガーがの上で実装する必要がありますこのような機能を使用する場合は、`ICorDebugBreakpoint`します。</span><span class="sxs-lookup"><span data-stu-id="2ba14-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="2ba14-114">ICorDebugFunctionBreakpoint インターフェイスは、拡張`ICorDebugBreakpoint`関数内のブレークポイントをサポートするためにします。</span><span class="sxs-lookup"><span data-stu-id="2ba14-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ba14-115">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2ba14-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba14-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="2ba14-116">Requirements</span></span>  
 <span data-ttu-id="2ba14-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba14-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba14-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ba14-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ba14-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ba14-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2ba14-120">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="2ba14-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ba14-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ba14-121">See also</span></span>

- [<span data-ttu-id="2ba14-122">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2ba14-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
