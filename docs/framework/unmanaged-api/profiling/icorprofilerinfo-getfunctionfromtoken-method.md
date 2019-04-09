---
title: ICorProfilerInfo::GetFunctionFromToken メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f4fb2292154a2660a2db3f0b3962fcf2114e385
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099977"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="999ac-102">ICorProfilerInfo::GetFunctionFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="999ac-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="999ac-103">関数の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="999ac-103">Gets the ID of a function.</span></span> <span data-ttu-id="999ac-104">このメソッドは、.NET Framework version 2.0 で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="999ac-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="999ac-105">使用して、 [icorprofilerinfo 2::getfunctionfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="999ac-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999ac-106">構文</span><span class="sxs-lookup"><span data-stu-id="999ac-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="999ac-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="999ac-107">Remarks</span></span>  
 <span data-ttu-id="999ac-108">`GetFunctionFromToken`メソッドは、ジェネリック関数またはジェネリック型の関数は機能しません。 以外は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="999ac-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="999ac-109">使用`ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs`すべての関数。</span><span class="sxs-lookup"><span data-stu-id="999ac-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="999ac-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="999ac-110">Requirements</span></span>  
 <span data-ttu-id="999ac-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="999ac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="999ac-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="999ac-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="999ac-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="999ac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="999ac-114">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="999ac-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="999ac-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="999ac-115">See also</span></span>

- [<span data-ttu-id="999ac-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="999ac-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
