---
title: ICorProfilerInfo2::GetContextStaticAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2c5c8165d44cc3a305820f8e97c07da37f2a0693
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775810"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="b63c4-102">ICorProfilerInfo2::GetContextStaticAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="b63c4-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="b63c4-103">指定したコンテキストのスコープ内の指定したコンテキストの静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b63c4-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b63c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="b63c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b63c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b63c4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b63c4-106">[in]要求されたコンテキストの静的フィールドが含まれるクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="b63c4-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="b63c4-107">[in]要求されたコンテキストの静的フィールドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="b63c4-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="b63c4-108">[in]要求されたコンテキストの静的フィールドのスコープのコンテキストの ID。</span><span class="sxs-lookup"><span data-stu-id="b63c4-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="b63c4-109">[out]指定したコンテキスト内にある静的フィールドのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b63c4-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b63c4-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b63c4-110">Remarks</span></span>  
 <span data-ttu-id="b63c4-111">`GetContextStaticAddress`メソッドは、次のいずれかを返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b63c4-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="b63c4-112">指定された静的フィールドに指定したコンテキスト内のアドレスが割り当てられていない場合の CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b63c4-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="b63c4-113">ガベージ コレクション ヒープで可能性のあるオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="b63c4-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="b63c4-114">これらのアドレスは、ガベージ コレクション後にプロファイラーを想定しないでくださいが有効であるために、ガベージ コレクションの後無効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b63c4-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="b63c4-115">クラスのクラスのコンス トラクターが完了したら、前に`GetContextStaticAddress`はいくつかの静的フィールドは既に初期化可能性がありますが、すべての静的フィールドの CORPROF_E_DATAINCOMPLETE を返し、ガベージ コレクション オブジェクトのルートします。</span><span class="sxs-lookup"><span data-stu-id="b63c4-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b63c4-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="b63c4-116">Requirements</span></span>  
 <span data-ttu-id="b63c4-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b63c4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b63c4-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b63c4-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b63c4-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b63c4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b63c4-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b63c4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63c4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b63c4-121">See also</span></span>

- [<span data-ttu-id="b63c4-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b63c4-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b63c4-123">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b63c4-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
