---
title: ICorProfilerInfo::GetClassIDInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 45abb39fa7266e19bbd375b476f2ab48bfc5914d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041328"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="0a9ba-102">ICorProfilerInfo::GetClassIDInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="0a9ba-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="0a9ba-103">指定したクラスの親モジュールとメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a9ba-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a9ba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a9ba-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0a9ba-106">[in]情報を取得する対象のクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="0a9ba-107">[out]クラスの親モジュールの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="0a9ba-108">[out]クラスのメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a9ba-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a9ba-109">Remarks</span></span>  
 <span data-ttu-id="0a9ba-110">プロファイラー コードを呼び出すことができます[icorprofilerinfo::getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)指定したモジュールのメタデータ インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="0a9ba-111">`pTypeDefToken` によって参照される場所に返されるメタデータ トークンを使用すると、クラスのメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="0a9ba-112">ジェネリック型の詳細情報を表示するには使用[icorprofilerinfo 2::getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a9ba-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="0a9ba-113">Requirements</span></span>  
 <span data-ttu-id="0a9ba-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a9ba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a9ba-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0a9ba-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0a9ba-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a9ba-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a9ba-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a9ba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a9ba-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a9ba-118">See also</span></span>

- [<span data-ttu-id="0a9ba-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a9ba-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
