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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a713a7d1f6e6a9d4b22071c33ac8e7c38cd371b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665079"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="a9701-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock メソッド</span><span class="sxs-lookup"><span data-stu-id="a9701-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="a9701-103">このオブジェクトのモニター ロックを所有しているマネージ スレッドを返します。</span><span class="sxs-lookup"><span data-stu-id="a9701-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9701-104">構文</span><span class="sxs-lookup"><span data-stu-id="a9701-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9701-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9701-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="a9701-106">[out]このオブジェクトのモニター ロックを所有しているマネージ スレッド。</span><span class="sxs-lookup"><span data-stu-id="a9701-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="a9701-107">[out]このスレッドが所有されているに返す前に、ロックを解放する必要があります回数。</span><span class="sxs-lookup"><span data-stu-id="a9701-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9701-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a9701-108">Return Value</span></span>  
 <span data-ttu-id="a9701-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="a9701-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a9701-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9701-110">HRESULT</span></span>|<span data-ttu-id="a9701-111">説明</span><span class="sxs-lookup"><span data-stu-id="a9701-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9701-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9701-112">S_OK</span></span>|<span data-ttu-id="a9701-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="a9701-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="a9701-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a9701-114">S_FALSE</span></span>|<span data-ttu-id="a9701-115">マネージ スレッドでは、このオブジェクトのモニター ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a9701-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a9701-116">例外</span><span class="sxs-lookup"><span data-stu-id="a9701-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9701-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="a9701-117">Remarks</span></span>  
 <span data-ttu-id="a9701-118">マネージ スレッドは、このオブジェクトのモニター ロックを所有している: 場合</span><span class="sxs-lookup"><span data-stu-id="a9701-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="a9701-119">メソッドは、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a9701-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="a9701-120">スレッド オブジェクトは、スレッドが終了するまで有効です。</span><span class="sxs-lookup"><span data-stu-id="a9701-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="a9701-121">マネージ スレッドが、このオブジェクトのモニター ロックを所有していない場合`ppThread`と`pAcquisitionCount`は変更されず、およびメソッドは S_FALSE を返します。</span><span class="sxs-lookup"><span data-stu-id="a9701-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="a9701-122">場合`ppThread`または`pAcquisitionCount`有効なポインターでない、結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="a9701-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="a9701-123">スレッドが、このオブジェクトのモニター ロックを所有している場合は、これを特定できないように、エラーが発生した場合、メソッドは失敗を示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="a9701-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9701-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="a9701-124">Requirements</span></span>  
 <span data-ttu-id="a9701-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9701-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9701-126">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9701-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9701-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9701-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9701-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9701-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9701-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9701-129">See also</span></span>

- [<span data-ttu-id="a9701-130">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a9701-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a9701-131">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a9701-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
