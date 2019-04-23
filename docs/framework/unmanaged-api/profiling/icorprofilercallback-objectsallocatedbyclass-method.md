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
ms.openlocfilehash: b9f5d2c08abbcab6bc1a6d0569b8e70d7c919def
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195866"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="7fa47-102">ICorProfilerCallback::ObjectsAllocatedByClass メソッド</span><span class="sxs-lookup"><span data-stu-id="7fa47-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="7fa47-103">最新のガベージ コレクションの後に作成された指定した各クラスのインスタンスの数をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="7fa47-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fa47-104">構文</span><span class="sxs-lookup"><span data-stu-id="7fa47-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fa47-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fa47-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="7fa47-106">[in]サイズ、`classIds`と`cObjects`配列。</span><span class="sxs-lookup"><span data-stu-id="7fa47-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="7fa47-107">[in]クラス Id、各 ID が 1 つまたは複数のインスタンスを持つクラスを指定の配列。</span><span class="sxs-lookup"><span data-stu-id="7fa47-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="7fa47-108">[in]各整数が対応するクラスのインスタンスの数を指定します、整数の配列、`classIds`配列。</span><span class="sxs-lookup"><span data-stu-id="7fa47-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fa47-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="7fa47-109">Remarks</span></span>  
 <span data-ttu-id="7fa47-110">`classIds`と`cObjects`配列は並列配列です。</span><span class="sxs-lookup"><span data-stu-id="7fa47-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="7fa47-111">たとえば、`classIds[i]`と`cObjects[i]`同じクラスを参照します。</span><span class="sxs-lookup"><span data-stu-id="7fa47-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="7fa47-112">前のガベージ コレクションの後、クラスのインスタンスが作成されていない場合、クラスは省略されます。</span><span class="sxs-lookup"><span data-stu-id="7fa47-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="7fa47-113">`ObjectsAllocatedByClass`コールバックは、大きなオブジェクト ヒープに割り当てられたオブジェクトは報告されません。</span><span class="sxs-lookup"><span data-stu-id="7fa47-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="7fa47-114">によって、報告される`ObjectsAllocatedByClass`はのみ推定されます。</span><span class="sxs-lookup"><span data-stu-id="7fa47-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="7fa47-115">正確な数は、使用[icorprofilercallback::objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="7fa47-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="7fa47-116">`classIds`配列は 1 つまたは複数の null エントリを含めることができる場合、対応する`cObjects`配列がアンロードしている型。</span><span class="sxs-lookup"><span data-stu-id="7fa47-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fa47-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="7fa47-117">Requirements</span></span>  
 <span data-ttu-id="7fa47-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fa47-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fa47-119">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7fa47-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7fa47-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fa47-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fa47-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fa47-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa47-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fa47-122">See also</span></span>

- [<span data-ttu-id="7fa47-123">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7fa47-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
