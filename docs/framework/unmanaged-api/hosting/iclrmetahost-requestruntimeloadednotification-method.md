---
title: ICLRMetaHost::RequestRuntimeLoadedNotification メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: 23f868bba2dc058d99f1c5c09e9b311b1ff3634a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140892"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="adfd4-102">ICLRMetaHost::RequestRuntimeLoadedNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="adfd4-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="adfd4-103">共通言語ランタイム (CLR) のバージョンが最初に読み込まれたが、まだ開始されていないときに呼び出されることが保証されているコールバック関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="adfd4-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="adfd4-104">このメソッドは、 [Lockclrversion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="adfd4-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfd4-105">構文</span><span class="sxs-lookup"><span data-stu-id="adfd4-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adfd4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="adfd4-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="adfd4-107">から新しいランタイムが読み込まれたときに呼び出されるコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="adfd4-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adfd4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="adfd4-108">Return Value</span></span>  
 <span data-ttu-id="adfd4-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="adfd4-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="adfd4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adfd4-110">HRESULT</span></span>|<span data-ttu-id="adfd4-111">説明</span><span class="sxs-lookup"><span data-stu-id="adfd4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adfd4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="adfd4-112">S_OK</span></span>|<span data-ttu-id="adfd4-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="adfd4-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="adfd4-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="adfd4-114">E_POINTER</span></span>|<span data-ttu-id="adfd4-115">`pCallbackFunction` が null です。</span><span class="sxs-lookup"><span data-stu-id="adfd4-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adfd4-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="adfd4-116">Remarks</span></span>  
 <span data-ttu-id="adfd4-117">コールバックは、次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="adfd4-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="adfd4-118">コールバックは、ランタイムが初めて読み込まれるときにのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="adfd4-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="adfd4-119">同じランタイムの再入可能な読み込みに対してコールバックが呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="adfd4-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="adfd4-120">再入可能でないランタイムの読み込みでは、コールバック関数の呼び出しがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="adfd4-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="adfd4-121">コールバック関数のプロトタイプは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="adfd4-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="adfd4-122">コールバック関数のプロトタイプは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="adfd4-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="adfd4-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="adfd4-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="adfd4-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="adfd4-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="adfd4-125">ホストの読み込みまたは再入によって別のランタイムの読み込みが必要になった場合は、コールバック関数で指定された `pfnCallbackThreadSet` パラメーターと `pfnCallbackThreadUnset` パラメーターを次のように使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adfd4-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="adfd4-126">このような負荷が試行される前に、ランタイムの読み込みを発生させる可能性のあるスレッドによって `pfnCallbackThreadSet` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="adfd4-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="adfd4-127">スレッドがこのようなランタイム読み込みを行わなくなる (および最初のコールバックから戻る前に) 場合は、`pfnCallbackThreadUnset` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="adfd4-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="adfd4-128">`pfnCallbackThreadSet` と `pfnCallbackThreadUnset` は両方とも再入可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="adfd4-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="adfd4-129">ホストアプリケーションは、`pCallbackFunction` パラメーターのスコープ外で `pfnCallbackThreadSet` および `pfnCallbackThreadUnset` を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="adfd4-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adfd4-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="adfd4-130">Requirements</span></span>  
 <span data-ttu-id="adfd4-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adfd4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adfd4-132">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="adfd4-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="adfd4-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="adfd4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adfd4-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adfd4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adfd4-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="adfd4-135">See also</span></span>

- [<span data-ttu-id="adfd4-136">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="adfd4-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="adfd4-137">ホスティング</span><span class="sxs-lookup"><span data-stu-id="adfd4-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
