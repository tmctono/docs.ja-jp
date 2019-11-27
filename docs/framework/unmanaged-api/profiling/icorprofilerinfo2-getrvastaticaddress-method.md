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
ms.openlocfilehash: db768c97a2d1a0fd5ee42ecfb121fb96d3092e79
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433012"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="29fc4-102">ICorProfilerInfo2::GetRVAStaticAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="29fc4-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="29fc4-103">指定した相対仮想アドレス (RVA) の静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="29fc4-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29fc4-104">構文</span><span class="sxs-lookup"><span data-stu-id="29fc4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29fc4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29fc4-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="29fc4-106">から要求された RVA 静的フィールドを含むクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="29fc4-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="29fc4-107">から要求された RVA 静的フィールドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="29fc4-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="29fc4-108">入出力RVA の静的フィールドのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="29fc4-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29fc4-109">コメント</span><span class="sxs-lookup"><span data-stu-id="29fc4-109">Remarks</span></span>  
 <span data-ttu-id="29fc4-110">`GetRVAStaticAddress` メソッドは、次のいずれかを返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="29fc4-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="29fc4-111">指定されたコンテキストで、指定された静的フィールドにアドレスが割り当てられていない場合は CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="29fc4-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="29fc4-112">ガベージコレクションヒープ内に存在する可能性があるオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="29fc4-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="29fc4-113">これらのアドレスは、ガベージコレクションの後に無効になることがあります。そのため、ガベージコレクションの後、プロファイラーはそれらが有効であると想定してはなりません。</span><span class="sxs-lookup"><span data-stu-id="29fc4-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="29fc4-114">クラスのクラスコンストラクターが完了する前に、`GetRVAStaticAddress` はすべての静的フィールドに対して CORPROF_E_DATAINCOMPLETE を返します。ただし、一部の静的フィールドは既に初期化されており、ガベージコレクションオブジェクトをルート化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29fc4-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29fc4-115">要件</span><span class="sxs-lookup"><span data-stu-id="29fc4-115">Requirements</span></span>  
 <span data-ttu-id="29fc4-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fc4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29fc4-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29fc4-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29fc4-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29fc4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29fc4-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29fc4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29fc4-120">参照</span><span class="sxs-lookup"><span data-stu-id="29fc4-120">See also</span></span>

- [<span data-ttu-id="29fc4-121">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29fc4-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="29fc4-122">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29fc4-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
