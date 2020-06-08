---
title: ICorProfilerInfo::GetFunctionInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
ms.openlocfilehash: e7193526bb0da1d28da4bf6bde108fc4d3fba273
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503017"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="1e61d-102">ICorProfilerInfo::GetFunctionInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="1e61d-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="1e61d-103">指定された関数の親クラスとメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="1e61d-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e61d-104">構文</span><span class="sxs-lookup"><span data-stu-id="1e61d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e61d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e61d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="1e61d-106">から親クラスおよびメタデータトークンを取得する対象の関数の ID。</span><span class="sxs-lookup"><span data-stu-id="1e61d-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="1e61d-107">[out] 関数の親クラスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1e61d-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="1e61d-108">[out] 関数の親クラスが定義されているモジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1e61d-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="1e61d-109">[out] 関数のメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1e61d-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e61d-110">解説</span><span class="sxs-lookup"><span data-stu-id="1e61d-110">Remarks</span></span>  
 <span data-ttu-id="1e61d-111">プロファイラーコードは、 [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md)を呼び出して、指定されたモジュールのメタデータインターフェイスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1e61d-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="1e61d-112">`pToken` が参照している場所に返されるメタデータ トークンを使用すると、関数のメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1e61d-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="1e61d-113">`ClassID`ジェネリッククラスの関数は、関数の使用に関するコンテキスト情報がないと取得できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e61d-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="1e61d-114">この場合、 `pClassId` は0になります。</span><span class="sxs-lookup"><span data-stu-id="1e61d-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="1e61d-115">プロファイラーコードでは、 [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)と COR_PRF_FRAME_INFO 値を使用して、より多くのコンテキストを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e61d-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e61d-116">要件</span><span class="sxs-lookup"><span data-stu-id="1e61d-116">Requirements</span></span>  
 <span data-ttu-id="1e61d-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e61d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e61d-118">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e61d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e61d-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e61d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e61d-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e61d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e61d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e61d-121">See also</span></span>

- [<span data-ttu-id="1e61d-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e61d-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
