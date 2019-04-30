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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d4d5ec9119cdcf89e507f133288f569e6fb37ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000689"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="98448-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs メソッド</span><span class="sxs-lookup"><span data-stu-id="98448-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="98448-103">取得、`ClassID`指定したメタデータ トークンを使用して型の`ClassID`いずれかの値が引数を入力します。</span><span class="sxs-lookup"><span data-stu-id="98448-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98448-104">構文</span><span class="sxs-lookup"><span data-stu-id="98448-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98448-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98448-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="98448-106">[in]型が存在するモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="98448-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="98448-107">[in]`mdTypeDef`型を参照するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="98448-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="98448-108">[in]指定した型の型パラメーターの数。</span><span class="sxs-lookup"><span data-stu-id="98448-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="98448-109">この値は、非ジェネリック型に対しては 0 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="98448-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="98448-110">[in]配列の`ClassID`型の引数は、それぞれの値。</span><span class="sxs-lookup"><span data-stu-id="98448-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="98448-111">値`typeArgs`場合に NULL が`cTypeArgs`0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="98448-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="98448-112">[out]ポインター、`ClassID`の指定した型。</span><span class="sxs-lookup"><span data-stu-id="98448-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98448-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="98448-113">Remarks</span></span>  
 <span data-ttu-id="98448-114">呼び出す、`GetClassFromTokenAndTypeArgs`メソッドを`mdTypeRef`の代わりに、`mdTypeDef`メタデータ トークンが予期しない結果を持つことができます。 呼び出し元を解決する必要があります、`mdTypeRef`を、`mdTypeDef`渡すとき。</span><span class="sxs-lookup"><span data-stu-id="98448-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="98448-115">型が既に読み込まれていない場合は、呼び出す`GetClassFromTokenAndTypeArgs`読み込み、これはさまざまなコンテキストで危険な操作がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="98448-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="98448-116">たとえば、モジュールまたはその他の型の読み込み中にこのメソッドを呼び出すと、ランタイムが循環的に読み込みしよう無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98448-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="98448-117">一般の使用`GetClassFromTokenAndTypeArgs`をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98448-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="98448-118">プロファイラー イベントは、特定の型の場合、保存する必要があります、`ModuleID`と`mdTypeDef`その種類、および使用の[icorprofilerinfo 2::getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)を確認するかどうかを指定した`ClassID`の目的の型。</span><span class="sxs-lookup"><span data-stu-id="98448-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98448-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="98448-119">Requirements</span></span>  
 <span data-ttu-id="98448-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98448-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98448-121">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98448-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98448-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98448-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98448-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98448-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98448-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="98448-124">See also</span></span>

- [<span data-ttu-id="98448-125">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98448-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="98448-126">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98448-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
