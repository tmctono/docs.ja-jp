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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f422e99a5f6a4153368304ff0b33bbc55381575a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177113"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="c5bde-102">ICorProfilerCallback::AppDomainShutdownStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="c5bde-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="c5bde-103">プロセスから、アプリケーション ドメインがアンロードされることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c5bde-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bde-104">構文</span><span class="sxs-lookup"><span data-stu-id="c5bde-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5bde-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5bde-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="c5bde-106">[in]アプリケーションのアセンブリが格納されているドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="c5bde-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5bde-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5bde-107">Remarks</span></span>  
 <span data-ttu-id="c5bde-108">値`appDomainId`は後の情報の要求は無効です、`AppDomainShutdownStarted`メソッドを返します。-これは、このアプリケーション ドメインに関する情報を取得するプロファイラーの最後のチャンスです。</span><span class="sxs-lookup"><span data-stu-id="c5bde-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5bde-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c5bde-109">Requirements</span></span>  
 <span data-ttu-id="c5bde-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5bde-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5bde-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5bde-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5bde-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5bde-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5bde-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5bde-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bde-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5bde-114">See also</span></span>

- [<span data-ttu-id="c5bde-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5bde-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
