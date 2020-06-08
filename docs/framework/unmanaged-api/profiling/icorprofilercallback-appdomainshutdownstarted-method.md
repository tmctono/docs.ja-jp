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
ms.openlocfilehash: 1b973cdeaffbec0dad1f2d082c44e8001647fdcc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500456"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="d2f2d-102">ICorProfilerCallback::AppDomainShutdownStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="d2f2d-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="d2f2d-103">アプリケーションドメインがプロセスからアンロードされていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2f2d-104">構文</span><span class="sxs-lookup"><span data-stu-id="d2f2d-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2f2d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2f2d-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="d2f2d-106">\[in] は、アプリケーションのアセンブリが格納されているドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2f2d-107">解説</span><span class="sxs-lookup"><span data-stu-id="d2f2d-107">Remarks</span></span>  
 <span data-ttu-id="d2f2d-108">の値は、 `appDomainId` メソッドが返された後の情報要求に対して有効ではありません `AppDomainShutdownStarted` 。これは、このアプリケーションドメインに関する情報を取得する最後の機会です。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2f2d-109">要件</span><span class="sxs-lookup"><span data-stu-id="d2f2d-109">Requirements</span></span>  
 <span data-ttu-id="d2f2d-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2f2d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2f2d-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2f2d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2f2d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2f2d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2f2d-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2f2d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f2d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2f2d-114">See also</span></span>

- [<span data-ttu-id="d2f2d-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d2f2d-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
