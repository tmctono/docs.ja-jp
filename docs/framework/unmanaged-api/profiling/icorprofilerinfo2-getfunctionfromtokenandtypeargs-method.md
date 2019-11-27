---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433216"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="6cd91-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs メソッド</span><span class="sxs-lookup"><span data-stu-id="6cd91-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="6cd91-103">指定されたメタデータトークン、格納クラス、および任意の型引数の `ClassID` 値を使用して、関数の `FunctionID` を取得します。</span><span class="sxs-lookup"><span data-stu-id="6cd91-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd91-104">構文</span><span class="sxs-lookup"><span data-stu-id="6cd91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cd91-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6cd91-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6cd91-106">から関数が存在するモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="6cd91-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="6cd91-107">から関数を参照する `mdMethodDef` メタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="6cd91-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="6cd91-108">からクラスを含んでいる関数の ID。</span><span class="sxs-lookup"><span data-stu-id="6cd91-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="6cd91-109">から指定された関数の型パラメーターの数。</span><span class="sxs-lookup"><span data-stu-id="6cd91-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="6cd91-110">非ジェネリック関数の場合、この値は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cd91-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="6cd91-111">から`ClassID` 値の配列。それぞれが関数の引数です。</span><span class="sxs-lookup"><span data-stu-id="6cd91-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="6cd91-112">`cTypeArgs` が0に設定されている場合、`typeArgs` の値は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="6cd91-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="6cd91-113">入出力指定した関数の `FunctionID` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6cd91-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cd91-114">コメント</span><span class="sxs-lookup"><span data-stu-id="6cd91-114">Remarks</span></span>  
 <span data-ttu-id="6cd91-115">`mdMethodDef` メタデータトークンではなく `mdMethodRef` メタデータを使用して `GetFunctionFromTokenAndTypeArgs` メソッドを呼び出すと、予期しない結果になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6cd91-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="6cd91-116">呼び出し元は、`mdMethodRef` を渡すときに `mdMethodDef` に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cd91-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="6cd91-117">関数がまだ読み込まれていない場合は、`GetFunctionFromTokenAndTypeArgs` を呼び出すと読み込みが発生します。これは、多くのコンテキストでは危険な操作です。</span><span class="sxs-lookup"><span data-stu-id="6cd91-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="6cd91-118">たとえば、モジュールまたは型の読み込み中にこのメソッドを呼び出すと、ランタイムが循環読み込みを試みたときに無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6cd91-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="6cd91-119">一般に、`GetFunctionFromTokenAndTypeArgs` の使用は推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="6cd91-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="6cd91-120">プロファイラーが特定の関数のイベントに関心を持っている場合は、その関数の `ModuleID` と `mdMethodDef` を格納し、 [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)を使用して、特定の `FunctionID` が目的の関数のものであるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cd91-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cd91-121">要件</span><span class="sxs-lookup"><span data-stu-id="6cd91-121">Requirements</span></span>  
 <span data-ttu-id="6cd91-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cd91-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cd91-123">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6cd91-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6cd91-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cd91-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cd91-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cd91-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cd91-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cd91-126">See also</span></span>

- [<span data-ttu-id="6cd91-127">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cd91-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="6cd91-128">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cd91-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
