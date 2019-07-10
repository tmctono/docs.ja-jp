---
title: ICorProfilerInfo2::GetRVAStaticAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc7b6d1a27faf7bde46305f9c98d98351e6261b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782273"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="019e4-102">ICorProfilerInfo2::GetRVAStaticAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="019e4-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="019e4-103">指定された相対仮想アドレス (RVA) の静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="019e4-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="019e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="019e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="019e4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="019e4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="019e4-106">[in]要求の RVA 静的フィールドを含むクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="019e4-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="019e4-107">[in]要求された静的 RVA フィールドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="019e4-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="019e4-108">[out]RVA 静的フィールドのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="019e4-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="019e4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="019e4-109">Remarks</span></span>  
 <span data-ttu-id="019e4-110">`GetRVAStaticAddress`メソッドは、次のいずれかを返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="019e4-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="019e4-111">指定された静的フィールドに指定したコンテキスト内のアドレスが割り当てられていない場合の CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="019e4-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="019e4-112">ガベージ コレクション ヒープで可能性のあるオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="019e4-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="019e4-113">これらのアドレスは、ガベージ コレクション後にプロファイラーを想定しないでくださいが有効であるために、ガベージ コレクションの後無効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="019e4-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="019e4-114">クラスのクラスのコンス トラクターが完了したら、前に`GetRVAStaticAddress`は既に初期化することがいくつかの静的フィールドと、ガベージ コレクション オブジェクトをルートすることがありますが、すべての静的フィールドの CORPROF_E_DATAINCOMPLETE を返します。</span><span class="sxs-lookup"><span data-stu-id="019e4-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="019e4-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="019e4-115">Requirements</span></span>  
 <span data-ttu-id="019e4-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="019e4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="019e4-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="019e4-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="019e4-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="019e4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="019e4-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="019e4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019e4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="019e4-120">See also</span></span>

- [<span data-ttu-id="019e4-121">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="019e4-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="019e4-122">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="019e4-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
