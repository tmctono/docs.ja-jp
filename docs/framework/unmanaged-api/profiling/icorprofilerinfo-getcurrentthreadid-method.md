---
title: ICorProfilerInfo::GetCurrentThreadID メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863961"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="a0d57-102">ICorProfilerInfo::GetCurrentThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="a0d57-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="a0d57-103">マネージスレッドの場合、現在のスレッドの ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="a0d57-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0d57-104">構文</span><span class="sxs-lookup"><span data-stu-id="a0d57-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0d57-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0d57-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="a0d57-106">入出力返されたマネージスレッドの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a0d57-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0d57-107">コメント</span><span class="sxs-lookup"><span data-stu-id="a0d57-107">Remarks</span></span>  
 <span data-ttu-id="a0d57-108">現在のスレッドが内部ランタイムスレッドまたはその他のアンマネージスレッドである場合、`GetCurrentThreadID` は HRESULT として CORPROF_E_NOT_MANAGED_THREAD を返し、`pThreadId` パラメーターの戻り値は null になります。</span><span class="sxs-lookup"><span data-stu-id="a0d57-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0d57-109">要件</span><span class="sxs-lookup"><span data-stu-id="a0d57-109">Requirements</span></span>  
 <span data-ttu-id="a0d57-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0d57-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0d57-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0d57-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0d57-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0d57-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0d57-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0d57-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d57-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0d57-114">See also</span></span>

- [<span data-ttu-id="a0d57-115">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0d57-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
