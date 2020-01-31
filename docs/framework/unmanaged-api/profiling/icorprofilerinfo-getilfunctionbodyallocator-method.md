---
title: ICorProfilerInfo::GetILFunctionBodyAllocator メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: 5fe472c4a0053ec9e37d7d61ffde5cf21d65dd2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863505"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="f881d-102">ICorProfilerInfo::GetILFunctionBodyAllocator メソッド</span><span class="sxs-lookup"><span data-stu-id="f881d-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="f881d-103">Microsoft 中間言語 (MSIL) コードでメソッドの本体を交換するために使用されるメモリを割り当てるメソッドを提供するインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f881d-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f881d-104">構文</span><span class="sxs-lookup"><span data-stu-id="f881d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f881d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f881d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f881d-106">からメソッドが存在するモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="f881d-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="f881d-107">入出力メモリを割り当てるメソッドを提供する[Imethodmalloc](imethodmalloc-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f881d-107">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f881d-108">コメント</span><span class="sxs-lookup"><span data-stu-id="f881d-108">Remarks</span></span>  
 <span data-ttu-id="f881d-109">MSIL コードのメソッド本体は、読み込まれたモジュールに対して相対的な相対仮想アドレス (RVA) として配置されている必要があります。これは、モジュールが 4 GB 以内に続くことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f881d-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="f881d-110">ツールがメソッドの本体を簡単に交換できるようにするために、`GetILFunctionBodyAllocator` メソッドを使用すると、その範囲内でメモリが確実に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f881d-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f881d-111">要件</span><span class="sxs-lookup"><span data-stu-id="f881d-111">Requirements</span></span>  
 <span data-ttu-id="f881d-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f881d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f881d-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f881d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f881d-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f881d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f881d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f881d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f881d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f881d-116">See also</span></span>

- [<span data-ttu-id="f881d-117">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f881d-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
