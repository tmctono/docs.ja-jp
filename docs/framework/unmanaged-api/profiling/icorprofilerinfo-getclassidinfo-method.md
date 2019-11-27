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
ms.openlocfilehash: c3b1bdac8ccd37cf2f6aac5073def313f04acf28
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439251"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="59f23-102">ICorProfilerInfo::GetClassIDInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="59f23-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="59f23-103">指定したクラスの親モジュールとメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="59f23-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f23-104">構文</span><span class="sxs-lookup"><span data-stu-id="59f23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59f23-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59f23-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="59f23-106">から情報を取得する対象のクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="59f23-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="59f23-107">入出力クラスの親モジュールの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="59f23-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="59f23-108">入出力クラスのメタデータトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="59f23-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59f23-109">コメント</span><span class="sxs-lookup"><span data-stu-id="59f23-109">Remarks</span></span>  
 <span data-ttu-id="59f23-110">プロファイラーコードは、 [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)を呼び出して、指定されたモジュールのメタデータインターフェイスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="59f23-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="59f23-111">`pTypeDefToken` によって参照される場所に返されるメタデータ トークンを使用すると、クラスのメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="59f23-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="59f23-112">ジェネリック型の詳細情報を取得するには、 [ICorProfilerInfo2:: GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="59f23-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59f23-113">要件</span><span class="sxs-lookup"><span data-stu-id="59f23-113">Requirements</span></span>  
 <span data-ttu-id="59f23-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f23-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59f23-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59f23-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59f23-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59f23-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59f23-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59f23-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f23-118">参照</span><span class="sxs-lookup"><span data-stu-id="59f23-118">See also</span></span>

- [<span data-ttu-id="59f23-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59f23-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
