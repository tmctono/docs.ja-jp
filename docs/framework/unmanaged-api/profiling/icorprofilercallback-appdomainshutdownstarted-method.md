---
title: ICorProfilerCallback::AppDomainShutdownStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: 6bbb41f8fd3ac37f1c21fe8b4f6159e3d303777c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445183"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="f2317-102">ICorProfilerCallback::AppDomainShutdownStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="f2317-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="f2317-103">アプリケーションドメインがプロセスからアンロードされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f2317-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2317-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2317-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2317-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2317-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="f2317-106">からアプリケーションのアセンブリが格納されているドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="f2317-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2317-107">コメント</span><span class="sxs-lookup"><span data-stu-id="f2317-107">Remarks</span></span>  
 <span data-ttu-id="f2317-108">`appDomainId` の値は、`AppDomainShutdownStarted` メソッドから返された後の情報要求に対して無効です。これは、このアプリケーションドメインに関する情報を取得するためのプロファイラーの最後の機会です。</span><span class="sxs-lookup"><span data-stu-id="f2317-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2317-109">要件</span><span class="sxs-lookup"><span data-stu-id="f2317-109">Requirements</span></span>  
 <span data-ttu-id="f2317-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2317-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2317-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2317-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2317-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2317-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2317-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2317-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2317-114">参照</span><span class="sxs-lookup"><span data-stu-id="f2317-114">See also</span></span>

- [<span data-ttu-id="f2317-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f2317-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
