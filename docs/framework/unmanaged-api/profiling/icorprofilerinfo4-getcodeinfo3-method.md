---
title: ICorProfilerInfo4::GetCodeInfo3 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
ms.openlocfilehash: d29145a9c224a064cf9210c56c8617d99f7690ba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443062"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="5b6a5-102">ICorProfilerInfo4::GetCodeInfo3 メソッド</span><span class="sxs-lookup"><span data-stu-id="5b6a5-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="5b6a5-103">指定した関数の JIT 再コンパイル バージョンに関連付けられているネイティブ コードの範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b6a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b6a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b6a5-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="5b6a5-106">[in] ネイティブ コードが関連付けられている関数の ID。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="5b6a5-107">[in] JIT 再コンパイルされた関数のID。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="5b6a5-108">[in] `codeInfos` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="5b6a5-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="5b6a5-110">[out] 呼び出し元が提供したバッファー。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="5b6a5-111">メソッドから制御が戻った後で、それぞれがネイティブ コードのブロックを記述する `COR_PRF_CODE_INFO` の構造体の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b6a5-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b6a5-112">Remarks</span></span>  
 <span data-ttu-id="5b6a5-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b6a5-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="5b6a5-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="5b6a5-116">エクステントは共通中間言語 (CIL) オフセットの昇順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="5b6a5-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="5b6a5-118">これを行うには、`cCodeInfos` の値を `cchName` パラメーターの値と比較します。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="5b6a5-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="5b6a5-120">別の方法として、最初に `GetCodeInfo3` を長さゼロの `codeInfos` バッファーで呼び出して、適切なバッファーのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="5b6a5-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span><span class="sxs-lookup"><span data-stu-id="5b6a5-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b6a5-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="5b6a5-122">Requirements</span></span>  
 <span data-ttu-id="5b6a5-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b6a5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b6a5-124">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b6a5-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b6a5-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b6a5-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b6a5-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b6a5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6a5-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b6a5-127">See also</span></span>

- [<span data-ttu-id="5b6a5-128">GetCodeInfo2 メソッド</span><span class="sxs-lookup"><span data-stu-id="5b6a5-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="5b6a5-129">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b6a5-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="5b6a5-130">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b6a5-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5b6a5-131">プロファイル</span><span class="sxs-lookup"><span data-stu-id="5b6a5-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
