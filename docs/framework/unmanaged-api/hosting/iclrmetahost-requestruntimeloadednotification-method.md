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
ms.openlocfilehash: 6813f72f9d27aeff90f797a6ca9370b22e03e6f0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703695"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="985c5-102">ICLRMetaHost::RequestRuntimeLoadedNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="985c5-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="985c5-103">共通言語ランタイム (CLR) のバージョンが最初に読み込まれたが、まだ開始されていないときに呼び出されることが保証されているコールバック関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="985c5-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="985c5-104">このメソッドは、 [Lockclrversion](lockclrversion-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="985c5-104">This method supersedes the [LockClrVersion](lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="985c5-105">構文</span><span class="sxs-lookup"><span data-stu-id="985c5-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="985c5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="985c5-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="985c5-107">から新しいランタイムが読み込まれたときに呼び出されるコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="985c5-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="985c5-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="985c5-108">Return Value</span></span>  
 <span data-ttu-id="985c5-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="985c5-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="985c5-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="985c5-110">HRESULT</span></span>|<span data-ttu-id="985c5-111">説明</span><span class="sxs-lookup"><span data-stu-id="985c5-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="985c5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="985c5-112">S_OK</span></span>|<span data-ttu-id="985c5-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="985c5-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="985c5-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="985c5-114">E_POINTER</span></span>|<span data-ttu-id="985c5-115">`pCallbackFunction` が null です。</span><span class="sxs-lookup"><span data-stu-id="985c5-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="985c5-116">解説</span><span class="sxs-lookup"><span data-stu-id="985c5-116">Remarks</span></span>  
 <span data-ttu-id="985c5-117">コールバックは、次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="985c5-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="985c5-118">コールバックは、ランタイムが初めて読み込まれるときにのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="985c5-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="985c5-119">同じランタイムの再入可能な読み込みに対してコールバックが呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="985c5-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="985c5-120">再入可能でないランタイムの読み込みでは、コールバック関数の呼び出しがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="985c5-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="985c5-121">コールバック関数のプロトタイプは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="985c5-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="985c5-122">コールバック関数のプロトタイプは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="985c5-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="985c5-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="985c5-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="985c5-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="985c5-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="985c5-125">ホストの読み込みまたは再入によって別のランタイムの読み込みが発生する場合は、 `pfnCallbackThreadSet` `pfnCallbackThreadUnset` コールバック関数で指定されたパラメーターとパラメーターを次のように使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="985c5-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="985c5-126">`pfnCallbackThreadSet`このような読み込みが試行される前に、ランタイムの読み込みを発生させる可能性のあるスレッドによって呼び出される必要があります。</span><span class="sxs-lookup"><span data-stu-id="985c5-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="985c5-127">`pfnCallbackThreadUnset`は、スレッドがこのようなランタイム読み込みを行わなくなる場合 (および最初のコールバックから戻る前) に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="985c5-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="985c5-128">`pfnCallbackThreadSet`と `pfnCallbackThreadUnset` はどちらも再入不可能です。</span><span class="sxs-lookup"><span data-stu-id="985c5-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="985c5-129">ホストアプリケーションは、 `pfnCallbackThreadSet` `pfnCallbackThreadUnset` パラメーターのスコープ外でおよびを呼び出すことはできません `pCallbackFunction` 。</span><span class="sxs-lookup"><span data-stu-id="985c5-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="985c5-130">要件</span><span class="sxs-lookup"><span data-stu-id="985c5-130">Requirements</span></span>  
 <span data-ttu-id="985c5-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="985c5-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="985c5-132">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="985c5-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="985c5-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="985c5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="985c5-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="985c5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="985c5-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="985c5-135">See also</span></span>

- [<span data-ttu-id="985c5-136">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="985c5-136">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="985c5-137">ホスティング</span><span class="sxs-lookup"><span data-stu-id="985c5-137">Hosting</span></span>](index.md)
