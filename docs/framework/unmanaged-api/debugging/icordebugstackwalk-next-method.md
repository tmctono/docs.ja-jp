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
ms.openlocfilehash: 724db50285532c20132fbfd5262df26227db6742
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782669"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="65162-102">ICorDebugStackWalk::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="65162-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="65162-103">移動、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)次のフレームにオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="65162-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65162-104">構文</span><span class="sxs-lookup"><span data-stu-id="65162-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="65162-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="65162-105">Return Value</span></span>  
 <span data-ttu-id="65162-106">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="65162-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="65162-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65162-107">HRESULT</span></span>|<span data-ttu-id="65162-108">説明</span><span class="sxs-lookup"><span data-stu-id="65162-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65162-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="65162-109">S_OK</span></span>|<span data-ttu-id="65162-110">次のフレームに、ランタイムが正常にアンワインドされました (「解説」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="65162-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="65162-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65162-111">E_FAIL</span></span>|<span data-ttu-id="65162-112">`ICorDebugStackWalk`オブジェクトを移すことができません。</span><span class="sxs-lookup"><span data-stu-id="65162-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="65162-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="65162-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="65162-114">このアンワインドの結果として、スタックの末尾に達しました。</span><span class="sxs-lookup"><span data-stu-id="65162-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="65162-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="65162-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="65162-116">フレーム ポインターがスタックの末尾に達してそのため、追加のフレームにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="65162-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="65162-117">例外</span><span class="sxs-lookup"><span data-stu-id="65162-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65162-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="65162-118">Remarks</span></span>  
 <span data-ttu-id="65162-119">`Next`メソッドの進歩、`ICorDebugStackWalk`呼び出し元のフレームにオブジェクトの場合にのみ、ランタイムは、現在のフレームをアンワインドできます。</span><span class="sxs-lookup"><span data-stu-id="65162-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="65162-120">それ以外の場合、オブジェクトは、ランタイムは、アンワインド可能な次のフレームを進めます。</span><span class="sxs-lookup"><span data-stu-id="65162-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65162-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="65162-121">Requirements</span></span>  
 <span data-ttu-id="65162-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65162-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65162-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65162-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65162-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65162-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65162-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65162-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65162-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="65162-126">See also</span></span>

- [<span data-ttu-id="65162-127">ICorDebugStackWalk インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65162-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="65162-128">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="65162-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="65162-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="65162-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
