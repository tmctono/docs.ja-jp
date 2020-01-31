---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
ms.openlocfilehash: e0663ff122397ba639a0a219e513be2f3f0cbbef
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862777"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="dd0ff-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs メソッド</span><span class="sxs-lookup"><span data-stu-id="dd0ff-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="dd0ff-103">指定されたメタデータトークンと任意の型引数の `ClassID` 値を使用して、型の `ClassID` を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd0ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd0ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd0ff-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="dd0ff-106">から型が存在するモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="dd0ff-107">から型を参照する `mdTypeDef` メタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="dd0ff-108">から指定された型の型パラメーターの数。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="dd0ff-109">非ジェネリック型の場合、この値は0である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="dd0ff-110">から`ClassID` 値の配列。それぞれが型の引数です。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="dd0ff-111">`cTypeArgs` が0に設定されている場合、`typeArgs` の値は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="dd0ff-112">入出力指定した型の `ClassID` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd0ff-113">コメント</span><span class="sxs-lookup"><span data-stu-id="dd0ff-113">Remarks</span></span>  
 <span data-ttu-id="dd0ff-114">`mdTypeDef` メタデータトークンではなく `mdTypeRef` を使用して `GetClassFromTokenAndTypeArgs` メソッドを呼び出すと、予期しない結果が発生する可能性があります。呼び出し元は、`mdTypeRef` を渡すときに `mdTypeDef` に解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="dd0ff-115">型がまだ読み込まれていない場合は、`GetClassFromTokenAndTypeArgs` を呼び出すと読み込みがトリガーされます。これは、多くのコンテキストでは危険な操作です。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="dd0ff-116">たとえば、モジュールまたはその他の型の読み込み中にこのメソッドを呼び出すと、ランタイムが循環読み込みを試みたときに無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="dd0ff-117">一般に、`GetClassFromTokenAndTypeArgs` の使用は推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="dd0ff-118">プロファイラーが特定の型のイベントに関心を持っている場合は、その型の `ModuleID` と `mdTypeDef` を格納し、 [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)を使用して、特定の `ClassID` が目的の型であるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd0ff-119">要件</span><span class="sxs-lookup"><span data-stu-id="dd0ff-119">Requirements</span></span>  
 <span data-ttu-id="dd0ff-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd0ff-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd0ff-121">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dd0ff-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dd0ff-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd0ff-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd0ff-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd0ff-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd0ff-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd0ff-124">See also</span></span>

- [<span data-ttu-id="dd0ff-125">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd0ff-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="dd0ff-126">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd0ff-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
