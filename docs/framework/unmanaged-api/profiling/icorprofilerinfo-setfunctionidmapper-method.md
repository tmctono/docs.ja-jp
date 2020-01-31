---
title: ICorProfilerInfo::SetFunctionIDMapper メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
ms.openlocfilehash: 52ab9a089b5def4f3db2f99abc5a718d66cca739
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863453"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="06bcf-102">ICorProfilerInfo::SetFunctionIDMapper メソッド</span><span class="sxs-lookup"><span data-stu-id="06bcf-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="06bcf-103">`FunctionID` 値を代替値に対応付けるために呼び出すプロファイラー実装関数を指定します。代替値は、プロファイラーの関数の開始フックと終了フックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="06bcf-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06bcf-104">構文</span><span class="sxs-lookup"><span data-stu-id="06bcf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06bcf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="06bcf-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="06bcf-106">から`FunctionID` 値を代替値にマップするために呼び出される[Functionidmapper](functionidmapper-function.md)実装へのポインター。</span><span class="sxs-lookup"><span data-stu-id="06bcf-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06bcf-107">コメント</span><span class="sxs-lookup"><span data-stu-id="06bcf-107">Remarks</span></span>  
 <span data-ttu-id="06bcf-108">`FunctionID` 値の代替手段は、 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)メソッドによって指定されたプロファイラーの関数の開始/終了フック ([FunctionEnter2](functionenter2-function.md)、 [FunctionLeave2](functionleave2-function.md)、および[FunctionTailcall2](functiontailcall2-function.md)) に渡されます。</span><span class="sxs-lookup"><span data-stu-id="06bcf-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="06bcf-109">`FunctionIDMapper` は一度だけ設定できます。 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)コールバックで設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="06bcf-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06bcf-110">要件</span><span class="sxs-lookup"><span data-stu-id="06bcf-110">Requirements</span></span>  
 <span data-ttu-id="06bcf-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06bcf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06bcf-112">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06bcf-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06bcf-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06bcf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06bcf-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06bcf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06bcf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="06bcf-115">See also</span></span>

- [<span data-ttu-id="06bcf-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06bcf-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
