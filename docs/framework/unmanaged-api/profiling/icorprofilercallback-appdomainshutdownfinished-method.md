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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d927bd21903bda6fd8a34992145eb495a3342382
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081958"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="8a9aa-102">ICorProfilerCallback::AppDomainShutdownFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="8a9aa-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="8a9aa-103">アプリケーション ドメインが、プロセスからアンロードされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a9aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a9aa-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a9aa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a9aa-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="8a9aa-106">[in]アプリケーションのアセンブリが格納されているドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="8a9aa-107">[in]かどうか、アプリケーション ドメインがアンロードされた正常を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a9aa-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a9aa-108">Remarks</span></span>  
 <span data-ttu-id="8a9aa-109">値`appDomainId`は後の情報の要求は無効です、 [icorprofilercallback::appdomainshutdownstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)メソッドを返します。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="8a9aa-110">アプリケーション ドメインのアンロードの一部が後に続ける可能性があります、`AppDomainCreationFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="8a9aa-111">エラーの HRESULT で`hrStatus`失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="8a9aa-112">ただし、成功 HRESULT で`hrStatus`のみにアプリケーション ドメインをアンロードの最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a9aa-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a9aa-113">Requirements</span></span>  
 <span data-ttu-id="8a9aa-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a9aa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a9aa-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a9aa-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a9aa-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a9aa-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8a9aa-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8a9aa-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a9aa-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a9aa-118">See also</span></span>

- [<span data-ttu-id="8a9aa-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a9aa-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
