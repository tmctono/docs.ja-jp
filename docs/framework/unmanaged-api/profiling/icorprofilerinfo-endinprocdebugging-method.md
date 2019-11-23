---
title: ICorProfilerInfo::EndInprocDebugging メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
ms.openlocfilehash: 09b1b81bde486db67acede99e0d67ff85cb01bae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447757"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="5059f-102">ICorProfilerInfo::EndInprocDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="5059f-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="5059f-103">Shuts down an in-process debugging session.</span><span class="sxs-lookup"><span data-stu-id="5059f-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="5059f-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="5059f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5059f-105">構文</span><span class="sxs-lookup"><span data-stu-id="5059f-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5059f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5059f-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="5059f-107">[in] A value that identifies the debugging session.</span><span class="sxs-lookup"><span data-stu-id="5059f-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="5059f-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="5059f-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5059f-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="5059f-109">Remarks</span></span>  
 <span data-ttu-id="5059f-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span><span class="sxs-lookup"><span data-stu-id="5059f-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="5059f-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span><span class="sxs-lookup"><span data-stu-id="5059f-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="5059f-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span><span class="sxs-lookup"><span data-stu-id="5059f-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="5059f-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span><span class="sxs-lookup"><span data-stu-id="5059f-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5059f-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="5059f-114">Requirements</span></span>  
 <span data-ttu-id="5059f-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5059f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5059f-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5059f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5059f-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5059f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5059f-118">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="5059f-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5059f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5059f-119">See also</span></span>

- [<span data-ttu-id="5059f-120">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5059f-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
