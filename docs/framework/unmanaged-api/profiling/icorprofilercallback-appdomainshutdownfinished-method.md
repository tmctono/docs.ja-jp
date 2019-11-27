---
title: ICorProfilerCallback::AppDomainShutdownFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: 8ff7d5a593388bd3a584e031aea411dfdb6c9845
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445201"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="83380-102">ICorProfilerCallback::AppDomainShutdownFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="83380-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="83380-103">アプリケーションドメインがプロセスからアンロードされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="83380-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83380-104">構文</span><span class="sxs-lookup"><span data-stu-id="83380-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83380-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83380-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="83380-106">からアプリケーションのアセンブリが格納されているドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="83380-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="83380-107">からアプリケーションドメインが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="83380-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83380-108">コメント</span><span class="sxs-lookup"><span data-stu-id="83380-108">Remarks</span></span>  
 <span data-ttu-id="83380-109">`appDomainId` の値は、 [ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)メソッドが返された後の情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="83380-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="83380-110">アプリケーションドメインのアンロードの一部は、`AppDomainCreationFinished` コールバックの後も続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="83380-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="83380-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="83380-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="83380-112">ただし、`hrStatus` の成功 HRESULT は、アプリケーションドメインのアンロードの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="83380-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83380-113">要件</span><span class="sxs-lookup"><span data-stu-id="83380-113">Requirements</span></span>  
 <span data-ttu-id="83380-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83380-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83380-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83380-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83380-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83380-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83380-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83380-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83380-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="83380-118">See also</span></span>

- [<span data-ttu-id="83380-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83380-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
