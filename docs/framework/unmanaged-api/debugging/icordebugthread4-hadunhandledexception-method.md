---
title: ICorDebugThread4::HadUnhandledException メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: d9f0eff35dbe0058398d2d1c851ef85effa9cd28
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122419"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="40d1c-102">ICorDebugThread4::HadUnhandledException メソッド</span><span class="sxs-lookup"><span data-stu-id="40d1c-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="40d1c-103">スレッドで未処理の例外が発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="40d1c-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40d1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="40d1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="40d1c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40d1c-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="40d1c-106">入出力[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体の順序付けられた列挙体のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40d1c-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40d1c-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="40d1c-107">Return Value</span></span>  
 <span data-ttu-id="40d1c-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="40d1c-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="40d1c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40d1c-109">HRESULT</span></span>|<span data-ttu-id="40d1c-110">説明</span><span class="sxs-lookup"><span data-stu-id="40d1c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40d1c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="40d1c-111">S_OK</span></span>|<span data-ttu-id="40d1c-112">スレッドの作成以降、ハンドルされない例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="40d1c-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="40d1c-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="40d1c-113">S_FALSE</span></span>|<span data-ttu-id="40d1c-114">スレッドでハンドルされない例外が発生していません。</span><span class="sxs-lookup"><span data-stu-id="40d1c-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40d1c-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="40d1c-115">Remarks</span></span>  
 <span data-ttu-id="40d1c-116">このメソッドは、スレッドにハンドルされない例外が発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="40d1c-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="40d1c-117">未処理の例外のコールバックがトリガーされるか、ネイティブの JIT アタッチが開始されるまで、このメソッドは S_OK を返すことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="40d1c-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="40d1c-118">処理不能な例外が返されるという保証はありませ[ん。](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)ただし、ハンドルされない例外コールバックを取得した後、またはネイティブ JIT アタッチによってプロセスがまだ続行されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="40d1c-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="40d1c-119">また、ネイティブ JIT アタッチがトリガーされたときに、ハンドルされない例外を持つ複数のスレッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="40d1c-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="40d1c-120">このような場合は、どの例外が JIT アタッチをトリガーしたかを判断する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="40d1c-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40d1c-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="40d1c-121">Requirements</span></span>  
 <span data-ttu-id="40d1c-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40d1c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40d1c-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40d1c-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40d1c-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40d1c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40d1c-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40d1c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d1c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="40d1c-126">See also</span></span>

- [<span data-ttu-id="40d1c-127">ICorDebugThread4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40d1c-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="40d1c-128">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40d1c-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="40d1c-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="40d1c-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
