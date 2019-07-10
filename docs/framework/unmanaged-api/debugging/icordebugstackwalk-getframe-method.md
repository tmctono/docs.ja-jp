---
title: ICorDebugStackWalk::GetFrame メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81c3eec9b33f51bd30cf8724eaf010d7cd0b6cd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760920"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="29135-102">ICorDebugStackWalk::GetFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="29135-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="29135-103">内の現在のフレームを取得、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="29135-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29135-104">構文</span><span class="sxs-lookup"><span data-stu-id="29135-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29135-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29135-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="29135-106">[in]現在のスタック フレームを表すフレームを作成したオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="29135-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29135-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="29135-107">Return Value</span></span>  
 <span data-ttu-id="29135-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="29135-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="29135-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="29135-109">HRESULT</span></span>|<span data-ttu-id="29135-110">説明</span><span class="sxs-lookup"><span data-stu-id="29135-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29135-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="29135-111">S_OK</span></span>|<span data-ttu-id="29135-112">ランタイムには、現在のフレームが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="29135-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="29135-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="29135-113">E_FAIL</span></span>|<span data-ttu-id="29135-114">現在のフレームは返されませんでした。</span><span class="sxs-lookup"><span data-stu-id="29135-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="29135-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="29135-115">S_FALSE</span></span>|<span data-ttu-id="29135-116">現在のフレームは、ネイティブ スタック フレームです。</span><span class="sxs-lookup"><span data-stu-id="29135-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="29135-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="29135-117">E_INVALIDARG</span></span>|<span data-ttu-id="29135-118">`pFrame` が null です。</span><span class="sxs-lookup"><span data-stu-id="29135-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="29135-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="29135-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="29135-120">フレーム ポインターがスタックの末尾に達してそのため、追加のフレームにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="29135-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="29135-121">例外</span><span class="sxs-lookup"><span data-stu-id="29135-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29135-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="29135-122">Remarks</span></span>  
 <span data-ttu-id="29135-123">`ICorDebugStackWalk` 実際のスタック フレームのみを返します。</span><span class="sxs-lookup"><span data-stu-id="29135-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="29135-124">使用して、 [icordebugthread 3::getactiveinternalframes](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)内部フレームを返すメソッド。</span><span class="sxs-lookup"><span data-stu-id="29135-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="29135-125">(内部フレームとは、一時データを格納する、ランタイムによってスタックにプッシュするデータ構造のことです)。</span><span class="sxs-lookup"><span data-stu-id="29135-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29135-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="29135-126">Requirements</span></span>  
 <span data-ttu-id="29135-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29135-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29135-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29135-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29135-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29135-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29135-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29135-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29135-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="29135-131">See also</span></span>

- [<span data-ttu-id="29135-132">ICorDebugStackWalk インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29135-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="29135-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29135-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="29135-134">デバッグ</span><span class="sxs-lookup"><span data-stu-id="29135-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
