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
ms.openlocfilehash: 90156152a2c133446dedbe22426785ab63f8dfb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131812"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="93c25-102">ICorDebugStackWalk::SetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="93c25-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="93c25-103">[オブジェクトの現在のコンテキスト](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)をスレッドの有効なコンテキストに設定します。</span><span class="sxs-lookup"><span data-stu-id="93c25-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c25-104">構文</span><span class="sxs-lookup"><span data-stu-id="93c25-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93c25-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="93c25-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="93c25-106">からコンテキストがスタックのアクティブなフレームからのものであるか、またはスタックのアンワインドによって取得されたコンテキストであるかを示す[Cordebugsetcontextflag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)フラグ。</span><span class="sxs-lookup"><span data-stu-id="93c25-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="93c25-107">から`CONTEXT` バッファーに割り当てられたサイズ。</span><span class="sxs-lookup"><span data-stu-id="93c25-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="93c25-108">から`CONTEXT` バッファー。</span><span class="sxs-lookup"><span data-stu-id="93c25-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93c25-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="93c25-109">Return Value</span></span>  
 <span data-ttu-id="93c25-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="93c25-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="93c25-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93c25-111">HRESULT</span></span>|<span data-ttu-id="93c25-112">説明</span><span class="sxs-lookup"><span data-stu-id="93c25-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93c25-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="93c25-113">S_OK</span></span>|<span data-ttu-id="93c25-114">`ICorDebugStackWalk` オブジェクトのコンテキストが正常に設定されました。</span><span class="sxs-lookup"><span data-stu-id="93c25-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="93c25-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="93c25-115">E_FAIL</span></span>|<span data-ttu-id="93c25-116">`ICorDebugStackWalk` オブジェクトのコンテキストが設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="93c25-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="93c25-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="93c25-117">E_INVALIDARG</span></span>|<span data-ttu-id="93c25-118">コンテキストが null です。</span><span class="sxs-lookup"><span data-stu-id="93c25-118">The context is null.</span></span>|  
|<span data-ttu-id="93c25-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="93c25-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="93c25-120">コンテキストバッファーが小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="93c25-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="93c25-121">例外</span><span class="sxs-lookup"><span data-stu-id="93c25-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93c25-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="93c25-122">Remarks</span></span>  
 <span data-ttu-id="93c25-123">このメソッドは、スレッドの現在のコンテキストを変更しません。</span><span class="sxs-lookup"><span data-stu-id="93c25-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="93c25-124">現在のコンテキストを無効なコンテキストに設定すると、スタックウォーカーから予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93c25-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="93c25-125">このコンテキストの完全なビットごとのコピーを取得するには、次のようにして、" [GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) " メソッドを直ちに呼び出します。</span><span class="sxs-lookup"><span data-stu-id="93c25-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93c25-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="93c25-126">Requirements</span></span>  
 <span data-ttu-id="93c25-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93c25-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93c25-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93c25-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93c25-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93c25-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93c25-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93c25-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c25-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="93c25-131">See also</span></span>

- [<span data-ttu-id="93c25-132">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="93c25-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="93c25-133">デバッグ</span><span class="sxs-lookup"><span data-stu-id="93c25-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
