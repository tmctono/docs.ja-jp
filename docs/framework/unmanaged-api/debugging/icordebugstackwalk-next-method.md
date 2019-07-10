---
title: ICorDebugStackWalk::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82f6c96e64b1197b5762c0ad7dbed5458b5d71a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760896"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="6641a-102">ICorDebugStackWalk::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="6641a-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="6641a-103">移動、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)次のフレームにオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6641a-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6641a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6641a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6641a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="6641a-105">Return Value</span></span>  
 <span data-ttu-id="6641a-106">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="6641a-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6641a-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6641a-107">HRESULT</span></span>|<span data-ttu-id="6641a-108">説明</span><span class="sxs-lookup"><span data-stu-id="6641a-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6641a-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6641a-109">S_OK</span></span>|<span data-ttu-id="6641a-110">次のフレームに、ランタイムが正常にアンワインドされました (「解説」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="6641a-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="6641a-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6641a-111">E_FAIL</span></span>|<span data-ttu-id="6641a-112">`ICorDebugStackWalk`オブジェクトを移すことができません。</span><span class="sxs-lookup"><span data-stu-id="6641a-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="6641a-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="6641a-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="6641a-114">このアンワインドの結果として、スタックの末尾に達しました。</span><span class="sxs-lookup"><span data-stu-id="6641a-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="6641a-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="6641a-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="6641a-116">フレーム ポインターがスタックの末尾に達してそのため、追加のフレームにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6641a-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="6641a-117">例外</span><span class="sxs-lookup"><span data-stu-id="6641a-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6641a-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="6641a-118">Remarks</span></span>  
 <span data-ttu-id="6641a-119">`Next`メソッドの進歩、`ICorDebugStackWalk`呼び出し元のフレームにオブジェクトの場合にのみ、ランタイムは、現在のフレームをアンワインドできます。</span><span class="sxs-lookup"><span data-stu-id="6641a-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="6641a-120">それ以外の場合、オブジェクトは、ランタイムは、アンワインド可能な次のフレームを進めます。</span><span class="sxs-lookup"><span data-stu-id="6641a-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6641a-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="6641a-121">Requirements</span></span>  
 <span data-ttu-id="6641a-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6641a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6641a-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6641a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6641a-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6641a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6641a-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6641a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6641a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6641a-126">See also</span></span>

- [<span data-ttu-id="6641a-127">ICorDebugStackWalk インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6641a-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="6641a-128">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6641a-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6641a-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="6641a-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
