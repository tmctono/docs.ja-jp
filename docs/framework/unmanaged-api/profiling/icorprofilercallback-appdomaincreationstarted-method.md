---
title: ICorProfilerCallback::AppDomainCreationStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e42a8ab23705703770c8214b8c641b48c86094a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598280"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="3e812-102">ICorProfilerCallback::AppDomainCreationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="3e812-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="3e812-103">アプリケーション ドメインが作成されていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3e812-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e812-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e812-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e812-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e812-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="3e812-106">[in]作成されるドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="3e812-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e812-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e812-107">Remarks</span></span>  
 <span data-ttu-id="3e812-108">ID が、情報の要求までの有効な[icorprofilercallback::appdomaincreationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3e812-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e812-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e812-109">Requirements</span></span>  
 <span data-ttu-id="3e812-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e812-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e812-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e812-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e812-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e812-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e812-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e812-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e812-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e812-114">See also</span></span>

- [<span data-ttu-id="3e812-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e812-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
