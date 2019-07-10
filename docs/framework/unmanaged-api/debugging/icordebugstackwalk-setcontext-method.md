---
title: ICorDebugStackWalk::SetContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6eb97fc70fec25f4b225c3fd5bad1e780091f7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771034"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="68a2e-102">ICorDebugStackWalk::SetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="68a2e-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="68a2e-103">セット、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)オブジェクトの現在のスレッドの有効なコンテキストのコンテキスト。</span><span class="sxs-lookup"><span data-stu-id="68a2e-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a2e-104">構文</span><span class="sxs-lookup"><span data-stu-id="68a2e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68a2e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68a2e-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="68a2e-106">[in]A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)かどうか、コンテキストは、スタックのアクティブなフレームから、またはスタックのアンワインドで取得したコンテキストを示すフラグです。</span><span class="sxs-lookup"><span data-stu-id="68a2e-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="68a2e-107">[in]割り当てのサイズ、`CONTEXT`バッファー。</span><span class="sxs-lookup"><span data-stu-id="68a2e-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="68a2e-108">[in]`CONTEXT`バッファー。</span><span class="sxs-lookup"><span data-stu-id="68a2e-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68a2e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="68a2e-109">Return Value</span></span>  
 <span data-ttu-id="68a2e-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="68a2e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="68a2e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68a2e-111">HRESULT</span></span>|<span data-ttu-id="68a2e-112">説明</span><span class="sxs-lookup"><span data-stu-id="68a2e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68a2e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="68a2e-113">S_OK</span></span>|<span data-ttu-id="68a2e-114">`ICorDebugStackWalk`オブジェクトのコンテキストが正常に設定します。</span><span class="sxs-lookup"><span data-stu-id="68a2e-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="68a2e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68a2e-115">E_FAIL</span></span>|<span data-ttu-id="68a2e-116">`ICorDebugStackWalk`オブジェクトのコンテキストが設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="68a2e-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="68a2e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="68a2e-117">E_INVALIDARG</span></span>|<span data-ttu-id="68a2e-118">コンテキストが null です。</span><span class="sxs-lookup"><span data-stu-id="68a2e-118">The context is null.</span></span>|  
|<span data-ttu-id="68a2e-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="68a2e-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="68a2e-120">コンテキスト バッファーが小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="68a2e-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="68a2e-121">例外</span><span class="sxs-lookup"><span data-stu-id="68a2e-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68a2e-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="68a2e-122">Remarks</span></span>  
 <span data-ttu-id="68a2e-123">このメソッドでは、スレッドの現在のコンテキストは変更されません。</span><span class="sxs-lookup"><span data-stu-id="68a2e-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="68a2e-124">無効なコンテキストを現在のコンテキストを設定すると、スタック ウォーカーから予期しない結果があります可能性。</span><span class="sxs-lookup"><span data-stu-id="68a2e-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="68a2e-125">このコンテキストの正確なビットごとのコピーを取得するにはすぐに呼び出すことによって、 [icordebugstackwalk::getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="68a2e-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68a2e-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="68a2e-126">Requirements</span></span>  
 <span data-ttu-id="68a2e-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68a2e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a2e-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68a2e-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68a2e-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68a2e-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68a2e-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a2e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a2e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a2e-131">See also</span></span>

- [<span data-ttu-id="68a2e-132">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68a2e-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="68a2e-133">デバッグ</span><span class="sxs-lookup"><span data-stu-id="68a2e-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
