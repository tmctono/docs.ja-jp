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
ms.openlocfilehash: 028207486f43e35086ed2e515eb3ae6bca304491
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866079"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="bdc66-102">ICorProfilerCallback::ObjectsAllocatedByClass メソッド</span><span class="sxs-lookup"><span data-stu-id="bdc66-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="bdc66-103">最後のガベージコレクション以降に作成された、指定した各クラスのインスタンスの数をプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="bdc66-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc66-104">構文</span><span class="sxs-lookup"><span data-stu-id="bdc66-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdc66-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdc66-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="bdc66-106">から`classIds` および `cObjects` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="bdc66-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="bdc66-107">からクラス Id の配列。各 ID は、1つ以上のインスタンスを持つクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bdc66-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="bdc66-108">から整数の配列。各整数は、`classIds` 配列内の対応するクラスのインスタンスの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bdc66-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdc66-109">コメント</span><span class="sxs-lookup"><span data-stu-id="bdc66-109">Remarks</span></span>  
 <span data-ttu-id="bdc66-110">`classIds` 配列と `cObjects` 配列は、並列配列です。</span><span class="sxs-lookup"><span data-stu-id="bdc66-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="bdc66-111">たとえば、`classIds[i]` と `cObjects[i]` は同じクラスを参照します。</span><span class="sxs-lookup"><span data-stu-id="bdc66-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="bdc66-112">前のガベージコレクションの後にクラスのインスタンスが作成されていない場合、クラスは省略されます。</span><span class="sxs-lookup"><span data-stu-id="bdc66-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="bdc66-113">`ObjectsAllocatedByClass` コールバックは、大きなオブジェクトヒープに割り当てられたオブジェクトを報告しません。</span><span class="sxs-lookup"><span data-stu-id="bdc66-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="bdc66-114">`ObjectsAllocatedByClass` によって報告される数値は、推定値のみです。</span><span class="sxs-lookup"><span data-stu-id="bdc66-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="bdc66-115">正確にカウントするには、 [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bdc66-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="bdc66-116">対応する `cObjects` 配列にアンロードされている型がある場合、`classIds` 配列には1つ以上の null エントリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bdc66-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdc66-117">要件</span><span class="sxs-lookup"><span data-stu-id="bdc66-117">Requirements</span></span>  
 <span data-ttu-id="bdc66-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc66-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdc66-119">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdc66-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdc66-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdc66-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdc66-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdc66-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc66-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdc66-122">See also</span></span>

- [<span data-ttu-id="bdc66-123">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bdc66-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
