---
title: ICorProfilerCallback::ObjectsAllocatedByClass メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4229332ef3a079a5a294e27b624dde0e1fb46691
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782961"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="90005-102">ICorProfilerCallback::ObjectsAllocatedByClass メソッド</span><span class="sxs-lookup"><span data-stu-id="90005-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="90005-103">最新のガベージ コレクションの後に作成された指定した各クラスのインスタンスの数をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="90005-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90005-104">構文</span><span class="sxs-lookup"><span data-stu-id="90005-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="90005-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90005-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="90005-106">[in]サイズ、`classIds`と`cObjects`配列。</span><span class="sxs-lookup"><span data-stu-id="90005-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="90005-107">[in]クラス Id、各 ID が 1 つまたは複数のインスタンスを持つクラスを指定の配列。</span><span class="sxs-lookup"><span data-stu-id="90005-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="90005-108">[in]各整数が対応するクラスのインスタンスの数を指定します、整数の配列、`classIds`配列。</span><span class="sxs-lookup"><span data-stu-id="90005-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90005-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="90005-109">Remarks</span></span>  
 <span data-ttu-id="90005-110">`classIds`と`cObjects`配列は並列配列です。</span><span class="sxs-lookup"><span data-stu-id="90005-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="90005-111">たとえば、`classIds[i]`と`cObjects[i]`同じクラスを参照します。</span><span class="sxs-lookup"><span data-stu-id="90005-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="90005-112">前のガベージ コレクションの後、クラスのインスタンスが作成されていない場合、クラスは省略されます。</span><span class="sxs-lookup"><span data-stu-id="90005-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="90005-113">`ObjectsAllocatedByClass`コールバックは、大きなオブジェクト ヒープに割り当てられたオブジェクトは報告されません。</span><span class="sxs-lookup"><span data-stu-id="90005-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="90005-114">によって、報告される`ObjectsAllocatedByClass`はのみ推定されます。</span><span class="sxs-lookup"><span data-stu-id="90005-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="90005-115">正確な数は、使用[icorprofilercallback::objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="90005-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="90005-116">`classIds`配列は 1 つまたは複数の null エントリを含めることができる場合、対応する`cObjects`配列がアンロードしている型。</span><span class="sxs-lookup"><span data-stu-id="90005-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90005-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="90005-117">Requirements</span></span>  
 <span data-ttu-id="90005-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90005-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90005-119">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90005-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90005-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90005-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90005-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90005-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90005-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="90005-122">See also</span></span>

- [<span data-ttu-id="90005-123">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="90005-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
