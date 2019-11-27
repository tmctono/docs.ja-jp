---
title: ICorProfilerInfo4::GetILToNativeMapping2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
ms.openlocfilehash: dfce86e95ba41a65e72524546072244a47f8360c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442930"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="20f84-102">ICorProfilerInfo4::GetILToNativeMapping2 メソッド</span><span class="sxs-lookup"><span data-stu-id="20f84-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="20f84-103">Microsoft Intermediate Language (MSIL) オフセットから、指定した関数の JIT 再コンパイル バージョンに含まれるコードのネイティブ オフセットへのマップを取得します。</span><span class="sxs-lookup"><span data-stu-id="20f84-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f84-104">構文</span><span class="sxs-lookup"><span data-stu-id="20f84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20f84-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20f84-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="20f84-106">[in] コードを含む関数の ID。</span><span class="sxs-lookup"><span data-stu-id="20f84-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="20f84-107">[in] JIT 再コンパイルされた関数のID。</span><span class="sxs-lookup"><span data-stu-id="20f84-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="20f84-108">.NET Framework 4.5 では、id は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="20f84-108">The identity must be zero in the .NET Framework 4.5.</span></span>  
  
 `cMap`  
 <span data-ttu-id="20f84-109">[in] `map` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="20f84-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="20f84-110">[out]使用できる COR_DEBUG_IL_TO_NATIVE_MAP 構造体の総数。</span><span class="sxs-lookup"><span data-stu-id="20f84-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="20f84-111">[out] `COR_DEBUG_IL_TO_NATIVE_MAP` 構造体の配列。各構造体はオフセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="20f84-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="20f84-112">`GetILToNativeMapping2` メソッドから制御が戻ると、`map` 構造体の一部または全部が `COR_DEBUG_IL_TO_NATIVE_MAP` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="20f84-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20f84-113">コメント</span><span class="sxs-lookup"><span data-stu-id="20f84-113">Remarks</span></span>  
 <span data-ttu-id="20f84-114">`GetILToNativeMapping2` は[ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)メソッドに似ていますが、今後のリリースでプロファイラーが再コンパイルされた関数の ID を指定できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="20f84-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20f84-115">[ICorProfilerFunctionControl:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)メソッドは .NET Framework 4.5 で実装されていないため、JIT 再コンパイルされた関数は、最初にコンパイルされた関数とは異なる IL からネイティブへのマッピングを持つことができません。</span><span class="sxs-lookup"><span data-stu-id="20f84-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the .NET Framework 4.5, so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="20f84-116">そのため、.NET Framework 4.5 で、ゼロ以外の JIT 再コンパイルされた ID を使用して `GetILToNativeMapping2` を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="20f84-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the .NET Framework 4.5.</span></span>  
  
 <span data-ttu-id="20f84-117">`GetILToNativeMapping2` メソッドは、`COR_DEBUG_IL_TO_NATIVE_MAP` 構造体の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="20f84-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="20f84-118">ネイティブ命令の特定の範囲がコードの特別な領域 (プロローグなど) に対応することを伝えるために、配列内のエントリには、`ilOffset` フィールドを[CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)列挙値に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="20f84-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="20f84-119">`GetILToNativeMapping2` から制御が戻ったら、`map` バッファーのサイズが十分で、すべての `COR_DEBUG_IL_TO_NATIVE_MAP` 構造体を格納できたかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20f84-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="20f84-120">これを行うには、`cMap` の値を `pcMap` パラメーターの値と比較します。</span><span class="sxs-lookup"><span data-stu-id="20f84-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="20f84-121">`pcMap` 値 に `COR_DEBUG_IL_TO_NATIVE_MAP` 構造体のサイズを乗算した結果が `cMap` より大きい場合は、`map` バッファーの割り当てを増やし、`cMap` を新しい大きいサイズに更新した後、`GetILToNativeMapping2` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="20f84-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="20f84-122">別の方法として、最初に `GetILToNativeMapping2` を長さゼロの `map` バッファーで呼び出して、適切なバッファーのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="20f84-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="20f84-123">その後、バッファーのサイズを `pcMap` で返された値に設定し、`GetILToNativeMapping2` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="20f84-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20f84-124">要件</span><span class="sxs-lookup"><span data-stu-id="20f84-124">Requirements</span></span>  
 <span data-ttu-id="20f84-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20f84-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20f84-126">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20f84-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20f84-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20f84-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20f84-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20f84-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f84-129">参照</span><span class="sxs-lookup"><span data-stu-id="20f84-129">See also</span></span>

- [<span data-ttu-id="20f84-130">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="20f84-130">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="20f84-131">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20f84-131">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="20f84-132">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="20f84-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="20f84-133">プロファイル</span><span class="sxs-lookup"><span data-stu-id="20f84-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
