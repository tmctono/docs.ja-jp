---
title: ICorProfilerInfo2::GetStaticFieldInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0106b2dd1151e302c0082b306d999ab5a1c4322
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177750"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="507b9-102">ICorProfilerInfo2::GetStaticFieldInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="507b9-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="507b9-103">指定したフィールドに適用される静的の種類を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="507b9-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="507b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="507b9-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="507b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="507b9-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="507b9-106">[in]静的フィールドが定義されているクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="507b9-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="507b9-107">[in]静的フィールドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="507b9-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="507b9-108">[out]値へのポインター、 [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)列挙型を示す指定したフィールドが静的かどうかとかどうか、静的な種類に適用されるフィールド。</span><span class="sxs-lookup"><span data-stu-id="507b9-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="507b9-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="507b9-109">Remarks</span></span>  
 <span data-ttu-id="507b9-110">この情報は、静的フィールドのアドレスを取得するために呼び出すには、どの関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="507b9-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="507b9-111">プロファイラー コードでは、実際にアドレスを持っていることを確認する静的フィールドのメタデータを確認する必要がありますもします。</span><span class="sxs-lookup"><span data-stu-id="507b9-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="507b9-112">静的リテラル (つまり、定数) は、メタデータにのみ存在し、アドレスはありません。</span><span class="sxs-lookup"><span data-stu-id="507b9-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="507b9-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="507b9-113">Requirements</span></span>  
 <span data-ttu-id="507b9-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="507b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="507b9-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="507b9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="507b9-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="507b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="507b9-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="507b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507b9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="507b9-118">See also</span></span>

- [<span data-ttu-id="507b9-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="507b9-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="507b9-120">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="507b9-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
