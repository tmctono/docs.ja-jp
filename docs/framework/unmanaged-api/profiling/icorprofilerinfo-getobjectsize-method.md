---
title: ICorProfilerInfo::GetObjectSize メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd337ca6d7b03ad22f178c9c7084cfa2585da73c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782749"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="42012-102">ICorProfilerInfo::GetObjectSize メソッド</span><span class="sxs-lookup"><span data-stu-id="42012-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="42012-103">指定したオブジェクトのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="42012-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42012-104">構文</span><span class="sxs-lookup"><span data-stu-id="42012-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42012-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42012-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="42012-106">[in]オブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="42012-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="42012-107">[out]オブジェクトのサイズ (バイト) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="42012-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42012-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="42012-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="42012-109">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="42012-109">This method is obsolete.</span></span> <span data-ttu-id="42012-110">返されます COR_E_OVERFLOW オブジェクト 4 GB より大きい 64 ビット プラットフォームで。</span><span class="sxs-lookup"><span data-stu-id="42012-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="42012-111">使用して、 [icorprofilerinfo 4::getobjectsize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="42012-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="42012-112">多くの場合、同じ種類の異なるオブジェクトと同じサイズである場合します。</span><span class="sxs-lookup"><span data-stu-id="42012-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="42012-113">ただし、配列や文字列など、一部の種類には、オブジェクトごとに別のサイズがあります。</span><span class="sxs-lookup"><span data-stu-id="42012-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="42012-114">によって返されるサイズ、`GetObjectSize`メソッドにオブジェクトがガベージ コレクション ヒープに後に表示される配置の埋め込みは含まれません。</span><span class="sxs-lookup"><span data-stu-id="42012-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="42012-115">使用する場合、`GetObjectSize`オブジェクトからオブジェクトをガベージ コレクション ヒープで切り替わるようにメソッドが配置を手動で、必要に応じてパディングを追加します。</span><span class="sxs-lookup"><span data-stu-id="42012-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="42012-116">32 ビットの Windows では、COR_PRF_GC_GEN_0、COR_PRF_GC_GEN_1、および COR_PRF_GC_GEN_2 4 バイトのアラインメントを使用して、COR_PRF_GC_LARGE_OBJECT_HEAP が 8 バイト アラインメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="42012-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="42012-117">64 ビットの Windows では、配置と、8 バイトでは常にします。</span><span class="sxs-lookup"><span data-stu-id="42012-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42012-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="42012-118">Requirements</span></span>  
 <span data-ttu-id="42012-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42012-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42012-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42012-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42012-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42012-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42012-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42012-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42012-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="42012-123">See also</span></span>

- [<span data-ttu-id="42012-124">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42012-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
