---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788617"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="0a7fc-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock メソッド</span><span class="sxs-lookup"><span data-stu-id="0a7fc-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="0a7fc-103">このオブジェクトのモニターロックを所有するマネージスレッドを返します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a7fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a7fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a7fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a7fc-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="0a7fc-106">入出力このオブジェクトのモニターロックを所有するマネージスレッド。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="0a7fc-107">入出力このスレッドがロックを解除してから、所有が解除されるまでの回数。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a7fc-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0a7fc-108">Return Value</span></span>  
 <span data-ttu-id="0a7fc-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0a7fc-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a7fc-110">HRESULT</span></span>|<span data-ttu-id="0a7fc-111">説明</span><span class="sxs-lookup"><span data-stu-id="0a7fc-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a7fc-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a7fc-112">S_OK</span></span>|<span data-ttu-id="0a7fc-113">メソッドは正常に終了しました。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="0a7fc-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0a7fc-114">S_FALSE</span></span>|<span data-ttu-id="0a7fc-115">このオブジェクトのモニターロックを所有しているマネージスレッドはありません。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0a7fc-116">例外</span><span class="sxs-lookup"><span data-stu-id="0a7fc-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a7fc-117">コメント</span><span class="sxs-lookup"><span data-stu-id="0a7fc-117">Remarks</span></span>  
 <span data-ttu-id="0a7fc-118">マネージスレッドがこのオブジェクトのモニターロックを所有している場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="0a7fc-119">メソッドは S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="0a7fc-120">スレッドオブジェクトは、スレッドが終了するまで有効です。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="0a7fc-121">このオブジェクトのモニターロックを所有しているマネージスレッドが存在しない場合、`ppThread` と `pAcquisitionCount` は変更されず、メソッドは S_FALSE を返します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="0a7fc-122">`ppThread` または `pAcquisitionCount` が有効なポインターでない場合、結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="0a7fc-123">このオブジェクトのモニターロックを所有しているスレッドが特定できない場合にエラーが発生すると、メソッドはエラーを示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a7fc-124">要件</span><span class="sxs-lookup"><span data-stu-id="0a7fc-124">Requirements</span></span>  
 <span data-ttu-id="0a7fc-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a7fc-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a7fc-126">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a7fc-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a7fc-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a7fc-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a7fc-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a7fc-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a7fc-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a7fc-129">See also</span></span>

- [<span data-ttu-id="0a7fc-130">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a7fc-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0a7fc-131">デバッグ</span><span class="sxs-lookup"><span data-stu-id="0a7fc-131">Debugging</span></span>](index.md)
