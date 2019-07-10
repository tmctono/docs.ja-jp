---
title: ICorDebugHeapValue3::GetMonitorEventWaitList メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db34d56fd4d074551ca4823681bc5d94e76df758
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756620"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="aedb0-102">ICorDebugHeapValue3::GetMonitorEventWaitList メソッド</span><span class="sxs-lookup"><span data-stu-id="aedb0-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="aedb0-103">モニター ロックに関連付けられているイベントをキューに置かれたスレッドの順序付きリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="aedb0-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aedb0-104">構文</span><span class="sxs-lookup"><span data-stu-id="aedb0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aedb0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aedb0-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="aedb0-106">[out]スレッドの順序付きリストを提供する ICorDebugThreadEnum 列挙子。</span><span class="sxs-lookup"><span data-stu-id="aedb0-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aedb0-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="aedb0-107">Return Value</span></span>  
 <span data-ttu-id="aedb0-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="aedb0-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="aedb0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aedb0-109">HRESULT</span></span>|<span data-ttu-id="aedb0-110">説明</span><span class="sxs-lookup"><span data-stu-id="aedb0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aedb0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aedb0-111">S_OK</span></span>|<span data-ttu-id="aedb0-112">The list is not empty.</span><span class="sxs-lookup"><span data-stu-id="aedb0-112">The list is not empty.</span></span>|  
|<span data-ttu-id="aedb0-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="aedb0-113">S_FALSE</span></span>|<span data-ttu-id="aedb0-114">リストが空です。</span><span class="sxs-lookup"><span data-stu-id="aedb0-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="aedb0-115">例外</span><span class="sxs-lookup"><span data-stu-id="aedb0-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aedb0-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="aedb0-116">Remarks</span></span>  
 <span data-ttu-id="aedb0-117">一覧の最初のスレッドは、次回の呼び出しからリリースされる最初のスレッド<xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="aedb0-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aedb0-118">次の呼び出しでは、上の一覧で、次のスレッドが解放されます。</span><span class="sxs-lookup"><span data-stu-id="aedb0-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="aedb0-119">リストが空でない場合、このメソッドは、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="aedb0-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="aedb0-120">リストが空の場合、メソッドは S_FALSE; を返しますこの場合、列挙型がまだ有効で空ですが。</span><span class="sxs-lookup"><span data-stu-id="aedb0-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="aedb0-121">いずれの場合も、列挙インターフェイスは、現在の同期状態の期間に対してのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="aedb0-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="aedb0-122">ただし、スレッドが終了するまでは、そこから割り当てられたスレッドのインターフェイスは有効です。</span><span class="sxs-lookup"><span data-stu-id="aedb0-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="aedb0-123">場合`ppThreadEnum`有効なポインターでない、結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="aedb0-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="aedb0-124">モニタのスレッドが待機している場合に、これを特定できないように、エラーが発生した場合、メソッドは失敗を示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="aedb0-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aedb0-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="aedb0-125">Requirements</span></span>  
 <span data-ttu-id="aedb0-126">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aedb0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aedb0-127">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aedb0-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aedb0-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aedb0-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aedb0-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aedb0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedb0-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="aedb0-130">See also</span></span>

- [<span data-ttu-id="aedb0-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aedb0-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="aedb0-132">デバッグ</span><span class="sxs-lookup"><span data-stu-id="aedb0-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
