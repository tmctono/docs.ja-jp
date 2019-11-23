---
title: ICorProfilerInfo2::GetThreadAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
ms.openlocfilehash: 8637be3c0a59676dc52aea985d7418bfd8f247bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443107"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="eace1-102">ICorProfilerInfo2::GetThreadAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="eace1-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="eace1-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span><span class="sxs-lookup"><span data-stu-id="eace1-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eace1-104">構文</span><span class="sxs-lookup"><span data-stu-id="eace1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eace1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eace1-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="eace1-106">[in] The ID specifying the thread.</span><span class="sxs-lookup"><span data-stu-id="eace1-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="eace1-107">[out] A pointer to the ID of the application domain.</span><span class="sxs-lookup"><span data-stu-id="eace1-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eace1-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="eace1-108">Requirements</span></span>  
 <span data-ttu-id="eace1-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eace1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eace1-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eace1-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eace1-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eace1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eace1-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eace1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eace1-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="eace1-113">See also</span></span>

- [<span data-ttu-id="eace1-114">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eace1-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="eace1-115">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eace1-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
