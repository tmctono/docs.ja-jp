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
ms.openlocfilehash: 722a1e0adea41a13ca25829c53372c29187b80bd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500469"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="c4916-102">ICorProfilerCallback::AppDomainShutdownFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="c4916-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="c4916-103">アプリケーションドメインがプロセスからアンロードされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c4916-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4916-104">構文</span><span class="sxs-lookup"><span data-stu-id="c4916-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4916-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4916-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="c4916-106">\[in] は、アプリケーションのアセンブリが格納されているドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="c4916-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="c4916-107">\[in] アプリケーションドメインが正常にアンロードされたかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="c4916-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4916-108">解説</span><span class="sxs-lookup"><span data-stu-id="c4916-108">Remarks</span></span>  
 <span data-ttu-id="c4916-109">`appDomainId` [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md)メソッドがを返すと、の値は情報要求に対して有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="c4916-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="c4916-110">アプリケーションドメインのアンロードの一部は、コールバック後に続行される場合があり `AppDomainCreationFinished` ます。</span><span class="sxs-lookup"><span data-stu-id="c4916-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="c4916-111">のエラー HRESULT は `hrStatus` エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="c4916-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c4916-112">ただし、の成功 HRESULT は、 `hrStatus` アプリケーションドメインのアンロードの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c4916-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4916-113">要件</span><span class="sxs-lookup"><span data-stu-id="c4916-113">Requirements</span></span>  
 <span data-ttu-id="c4916-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4916-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4916-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4916-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4916-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4916-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4916-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4916-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4916-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4916-118">See also</span></span>

- [<span data-ttu-id="c4916-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4916-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
