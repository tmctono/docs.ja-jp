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
ms.openlocfilehash: 896e797acc76e8d8034bd964e488317a62eed97b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378773"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="9170b-102">ICorDebugStackWalk::SetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="9170b-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="9170b-103">[オブジェクトの現在のコンテキスト](icordebugstackwalk-interface.md)をスレッドの有効なコンテキストに設定します。</span><span class="sxs-lookup"><span data-stu-id="9170b-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9170b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9170b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9170b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9170b-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="9170b-106">からコンテキストがスタックのアクティブなフレームからのものであるか、またはスタックのアンワインドによって取得されたコンテキストであるかを示す[Cordebugsetcontextflag](cordebugsetcontextflag-enumeration.md)フラグ。</span><span class="sxs-lookup"><span data-stu-id="9170b-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="9170b-107">からバッファーに割り当てられたサイズ `CONTEXT` 。</span><span class="sxs-lookup"><span data-stu-id="9170b-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="9170b-108">から`CONTEXT`バッファー。</span><span class="sxs-lookup"><span data-stu-id="9170b-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9170b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="9170b-109">Return Value</span></span>  
 <span data-ttu-id="9170b-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="9170b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9170b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9170b-111">HRESULT</span></span>|<span data-ttu-id="9170b-112">説明</span><span class="sxs-lookup"><span data-stu-id="9170b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9170b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9170b-113">S_OK</span></span>|<span data-ttu-id="9170b-114">`ICorDebugStackWalk`オブジェクトのコンテキストが正常に設定されました。</span><span class="sxs-lookup"><span data-stu-id="9170b-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="9170b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9170b-115">E_FAIL</span></span>|<span data-ttu-id="9170b-116">`ICorDebugStackWalk`オブジェクトのコンテキストが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="9170b-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="9170b-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9170b-117">E_INVALIDARG</span></span>|<span data-ttu-id="9170b-118">コンテキストが null です。</span><span class="sxs-lookup"><span data-stu-id="9170b-118">The context is null.</span></span>|  
|<span data-ttu-id="9170b-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="9170b-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="9170b-120">コンテキストバッファーが小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="9170b-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9170b-121">例外</span><span class="sxs-lookup"><span data-stu-id="9170b-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9170b-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="9170b-122">Remarks</span></span>  
 <span data-ttu-id="9170b-123">このメソッドは、スレッドの現在のコンテキストを変更しません。</span><span class="sxs-lookup"><span data-stu-id="9170b-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="9170b-124">現在のコンテキストを無効なコンテキストに設定すると、スタックウォーカーから予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9170b-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="9170b-125">このコンテキストの完全なビットごとのコピーを取得するには、次のようにして、" [GetContext](icordebugstackwalk-getcontext-method.md) " メソッドを直ちに呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9170b-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9170b-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="9170b-126">Requirements</span></span>  
 <span data-ttu-id="9170b-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9170b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9170b-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9170b-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9170b-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9170b-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9170b-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9170b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9170b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9170b-131">See also</span></span>

- [<span data-ttu-id="9170b-132">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9170b-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9170b-133">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9170b-133">Debugging</span></span>](index.md)
