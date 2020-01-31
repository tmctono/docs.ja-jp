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
ms.openlocfilehash: 0851ac33a2bac4fcf727cf09e5225f6b83481b50
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866677"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="19ede-102">ICorProfilerCallback::AppDomainShutdownFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="19ede-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="19ede-103">アプリケーションドメインがプロセスからアンロードされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="19ede-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ede-104">構文</span><span class="sxs-lookup"><span data-stu-id="19ede-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19ede-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19ede-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="19ede-106">の \[] アプリケーションのアセンブリが格納されているドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="19ede-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="19ede-107">\[] アプリケーションドメインが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="19ede-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="19ede-108">コメント</span><span class="sxs-lookup"><span data-stu-id="19ede-108">Remarks</span></span>  
 <span data-ttu-id="19ede-109">`appDomainId` の値は、 [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md)メソッドが返された後の情報要求に対して無効です。</span><span class="sxs-lookup"><span data-stu-id="19ede-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="19ede-110">アプリケーションドメインのアンロードの一部は、`AppDomainCreationFinished` コールバックの後も続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="19ede-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="19ede-111">`hrStatus` のエラー HRESULT はエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="19ede-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="19ede-112">ただし、`hrStatus` の成功 HRESULT は、アプリケーションドメインのアンロードの最初の部分が成功したことのみを示します。</span><span class="sxs-lookup"><span data-stu-id="19ede-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19ede-113">要件</span><span class="sxs-lookup"><span data-stu-id="19ede-113">Requirements</span></span>  
 <span data-ttu-id="19ede-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19ede-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19ede-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19ede-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19ede-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19ede-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19ede-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ede-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ede-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="19ede-118">See also</span></span>

- [<span data-ttu-id="19ede-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19ede-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
