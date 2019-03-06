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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7124aadc9c848ee2656473b7e06c3bc9b7881a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469334"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a><span data-ttu-id="58bfc-102">ICorProfilerInfo4::GetILToNativeMapping2 メソッド</span><span class="sxs-lookup"><span data-stu-id="58bfc-102">ICorProfilerInfo4::GetILToNativeMapping2 Method</span></span>
<span data-ttu-id="58bfc-103">Microsoft Intermediate Language (MSIL) オフセットから、指定した関数の JIT 再コンパイル バージョンに含まれるコードのネイティブ オフセットへのマップを取得します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58bfc-104">構文</span><span class="sxs-lookup"><span data-stu-id="58bfc-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58bfc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58bfc-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="58bfc-106">[in] コードを含む関数の ID。</span><span class="sxs-lookup"><span data-stu-id="58bfc-106">[in] The ID of the function that contains the code.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="58bfc-107">[in] JIT 再コンパイルされた関数のID。</span><span class="sxs-lookup"><span data-stu-id="58bfc-107">[in] The identity of the JIT-recompiled function.</span></span> <span data-ttu-id="58bfc-108">
  [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] ではこの ID はゼロでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="58bfc-108">The identity must be zero in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 `cMap`  
 <span data-ttu-id="58bfc-109">[in] `map` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="58bfc-109">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="58bfc-110">[out]使用可能な COR_DEBUG_IL_TO_NATIVE_MAP 構造体の合計数。</span><span class="sxs-lookup"><span data-stu-id="58bfc-110">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="58bfc-111">[out] `COR_DEBUG_IL_TO_NATIVE_MAP` 構造体の配列。各構造体はオフセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-111">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="58bfc-112">
  `GetILToNativeMapping2\` メソッドから制御が戻ると、`COR_DEBUG_IL_TO_NATIVE_MAP\` 構造体の一部または全部が `map\` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="58bfc-112">After the `GetILToNativeMapping2` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58bfc-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="58bfc-113">Remarks</span></span>  
 <span data-ttu-id="58bfc-114">`GetILToNativeMapping2` ような[icorprofilerinfo::getiltonativemapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)メソッド、プロファイラーが後で再コンパイルされた関数の ID を指定することができますが、解放します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-114">`GetILToNativeMapping2` is similar to the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method, except that it will allow the profiler to specify the ID of the recompiled function in future releases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58bfc-115">[Icorprofilerfunctioncontrol::setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)でメソッドが実装されていません、 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]JIT 再コンパイルされている関数とは異なる IL からネイティブへのマッピングを含めることはできませんので、もともと関数をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="58bfc-115">The [ICorProfilerFunctionControl::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) method is not implemented in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], so functions that have been JIT-recompiled cannot have an IL-to-native mapping that differs from the originally compiled function.</span></span> <span data-ttu-id="58bfc-116">このため `GetILToNativeMapping2` は、[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] でゼロ以外の JIT 再コンパイル済み ID を使用して呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="58bfc-116">As such, `GetILToNativeMapping2` cannot be called with a nonzero JIT-recompiled ID in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 <span data-ttu-id="58bfc-117">
  `GetILToNativeMapping2\` メソッドは、`COR_DEBUG_IL_TO_NATIVE_MAP\` 構造体の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-117">The `GetILToNativeMapping2` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="58bfc-118">ネイティブ命令の特定の範囲がコード (たとえば、プロローグ) の特殊なリージョンに対応することを伝える、配列内のエントリを持つことができます、`ilOffset`フィールドの値に設定、 [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)列挙体です。</span><span class="sxs-lookup"><span data-stu-id="58bfc-118">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="58bfc-119">
  `GetILToNativeMapping2\` から制御が戻ったら、`map\` バッファーのサイズが十分で、すべての `COR_DEBUG_IL_TO_NATIVE_MAP\` 構造体を格納できたかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58bfc-119">After `GetILToNativeMapping2` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="58bfc-120">これを行うには、`cMap` の値を `pcMap` パラメーターの値と比較します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-120">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="58bfc-121">`pcMap` 値 に `COR_DEBUG_IL_TO_NATIVE_MAP` 構造体のサイズを乗算した結果が `cMap` より大きい場合は、`map` バッファーの割り当てを増やし、`cMap` を新しい大きいサイズに更新した後、`GetILToNativeMapping2` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-121">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping2` again.</span></span>  
  
 <span data-ttu-id="58bfc-122">別の方法として、最初に `GetILToNativeMapping2` を長さゼロの `map` バッファーで呼び出して、適切なバッファーのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-122">Alternatively, you can first call `GetILToNativeMapping2` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="58bfc-123">その後、バッファーのサイズを `pcMap` で返された値に設定し、`GetILToNativeMapping2` を再度呼び出します。</span><span class="sxs-lookup"><span data-stu-id="58bfc-123">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58bfc-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="58bfc-124">Requirements</span></span>  
 <span data-ttu-id="58bfc-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58bfc-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58bfc-126">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58bfc-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58bfc-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58bfc-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58bfc-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58bfc-128">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bfc-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="58bfc-129">See also</span></span>
- [<span data-ttu-id="58bfc-130">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="58bfc-130">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="58bfc-131">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58bfc-131">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="58bfc-132">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="58bfc-132">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="58bfc-133">プロファイル</span><span class="sxs-lookup"><span data-stu-id="58bfc-133">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
