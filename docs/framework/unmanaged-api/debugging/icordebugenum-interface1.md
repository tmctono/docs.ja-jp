---
title: ICorDebugEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b25c47e101ad0fb8e8cbdbb2718a41c9be6c0c22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931984"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="6b79b-102">ICorDebugEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b79b-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="6b79b-103">デバッグアプリケーションで使用される列挙子の抽象基本インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6b79b-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b79b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b79b-104">Methods</span></span>  
  
|<span data-ttu-id="6b79b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6b79b-105">Method</span></span>|<span data-ttu-id="6b79b-106">説明</span><span class="sxs-lookup"><span data-stu-id="6b79b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b79b-107">Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="6b79b-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="6b79b-108">この`ICorDebugEnum`オブジェクトのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b79b-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="6b79b-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="6b79b-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="6b79b-110">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b79b-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="6b79b-111">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="6b79b-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="6b79b-112">カーソルを列挙体の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="6b79b-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="6b79b-113">Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="6b79b-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="6b79b-114">指定した数の項目だけ、列挙内でカーソルを前方に移動します。</span><span class="sxs-lookup"><span data-stu-id="6b79b-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b79b-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b79b-115">Remarks</span></span>  
 <span data-ttu-id="6b79b-116">次の列挙子は`ICorDebugEnum`、から派生します。</span><span class="sxs-lookup"><span data-stu-id="6b79b-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="6b79b-117">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="6b79b-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="6b79b-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="6b79b-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="6b79b-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="6b79b-122">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="6b79b-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="6b79b-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="6b79b-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="6b79b-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="6b79b-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="6b79b-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="6b79b-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="6b79b-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="6b79b-131">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="6b79b-132">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="6b79b-133">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="6b79b-134">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="6b79b-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="6b79b-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="6b79b-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="6b79b-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="6b79b-138">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6b79b-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b79b-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b79b-139">Requirements</span></span>  
 <span data-ttu-id="6b79b-140">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b79b-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b79b-141">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6b79b-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b79b-142">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="6b79b-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b79b-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b79b-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b79b-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b79b-144">See also</span></span>

- [<span data-ttu-id="6b79b-145">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6b79b-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
