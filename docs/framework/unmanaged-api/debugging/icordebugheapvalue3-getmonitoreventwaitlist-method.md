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
ms.openlocfilehash: 15900fab59d172ada67d8aefeab698e1b44f808e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794389"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="b1991-102">ICorDebugHeapValue3::GetMonitorEventWaitList メソッド</span><span class="sxs-lookup"><span data-stu-id="b1991-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="b1991-103">モニターロックに関連付けられているイベントでキューに登録されているスレッドの順序付きリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1991-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1991-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1991-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1991-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1991-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="b1991-106">入出力順序付けされたスレッドのリストを提供する、の型の定数列挙子。</span><span class="sxs-lookup"><span data-stu-id="b1991-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1991-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b1991-107">Return Value</span></span>  
 <span data-ttu-id="b1991-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="b1991-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b1991-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1991-109">HRESULT</span></span>|<span data-ttu-id="b1991-110">説明</span><span class="sxs-lookup"><span data-stu-id="b1991-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1991-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1991-111">S_OK</span></span>|<span data-ttu-id="b1991-112">The list is not empty.</span><span class="sxs-lookup"><span data-stu-id="b1991-112">The list is not empty.</span></span>|  
|<span data-ttu-id="b1991-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b1991-113">S_FALSE</span></span>|<span data-ttu-id="b1991-114">リストが空です。</span><span class="sxs-lookup"><span data-stu-id="b1991-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b1991-115">例外</span><span class="sxs-lookup"><span data-stu-id="b1991-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1991-116">コメント</span><span class="sxs-lookup"><span data-stu-id="b1991-116">Remarks</span></span>  
 <span data-ttu-id="b1991-117">リスト内の最初のスレッドは、次に <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>を呼び出すことによって解放される最初のスレッドです。</span><span class="sxs-lookup"><span data-stu-id="b1991-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b1991-118">リスト内の次のスレッドは、次の呼び出しで解放されます。</span><span class="sxs-lookup"><span data-stu-id="b1991-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="b1991-119">リストが空でない場合、このメソッドは S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="b1991-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="b1991-120">リストが空の場合、メソッドは S_FALSE を返します。この場合、列挙体は空ですが、有効です。</span><span class="sxs-lookup"><span data-stu-id="b1991-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="b1991-121">どちらの場合も、列挙インターフェイスは、現在の同期された状態の間のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1991-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="b1991-122">ただし、スレッドのインターフェイスディスペンサーは、スレッドが終了するまで有効です。</span><span class="sxs-lookup"><span data-stu-id="b1991-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="b1991-123">`ppThreadEnum` が有効なポインターでない場合、結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="b1991-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="b1991-124">どのスレッドがモニターを待機しているかを特定できないようなエラーが発生した場合、メソッドはエラーを示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="b1991-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1991-125">要件</span><span class="sxs-lookup"><span data-stu-id="b1991-125">Requirements</span></span>  
 <span data-ttu-id="b1991-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1991-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1991-127">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1991-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1991-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1991-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1991-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1991-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1991-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1991-130">See also</span></span>

- [<span data-ttu-id="b1991-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1991-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b1991-132">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b1991-132">Debugging</span></span>](index.md)
