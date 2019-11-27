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
ms.openlocfilehash: de6d46897f3d3266bf708528efd712ca7db8ea4a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438828"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="14741-102">ICorProfilerInfo::GetObjectSize メソッド</span><span class="sxs-lookup"><span data-stu-id="14741-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="14741-103">指定したオブジェクトのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="14741-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14741-104">構文</span><span class="sxs-lookup"><span data-stu-id="14741-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14741-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="14741-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="14741-106">からオブジェクトの ID です。</span><span class="sxs-lookup"><span data-stu-id="14741-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="14741-107">入出力オブジェクトのサイズへのポインター (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="14741-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14741-108">コメント</span><span class="sxs-lookup"><span data-stu-id="14741-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14741-109">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="14741-109">This method is obsolete.</span></span> <span data-ttu-id="14741-110">64ビットプラットフォームで 4 GB を超えるオブジェクトの COR_E_OVERFLOW を返します。</span><span class="sxs-lookup"><span data-stu-id="14741-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="14741-111">代わりに[ICorProfilerInfo4:: GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="14741-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="14741-112">多くの場合、同じ種類の異なるオブジェクトのサイズは同じです。</span><span class="sxs-lookup"><span data-stu-id="14741-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="14741-113">ただし、配列や文字列など、一部の型では、オブジェクトごとにサイズが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="14741-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="14741-114">`GetObjectSize` メソッドによって返されるサイズには、オブジェクトがガベージコレクションヒープに配置された後に表示されるアラインメントの埋め込みは含まれません。</span><span class="sxs-lookup"><span data-stu-id="14741-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="14741-115">`GetObjectSize` メソッドを使用してオブジェクトからガベージコレクションヒープ上のオブジェクトに進む場合は、必要に応じて、手動でアラインメントのパディングを追加します。</span><span class="sxs-lookup"><span data-stu-id="14741-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="14741-116">32ビットの Windows では、COR_PRF_GC_GEN_0、COR_PRF_GC_GEN_1、および COR_PRF_GC_GEN_2 は4バイトの配置を使用し、COR_PRF_GC_LARGE_OBJECT_HEAP は8バイトの配置を使用します。</span><span class="sxs-lookup"><span data-stu-id="14741-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="14741-117">64ビットの Windows では、アラインメントは常に8バイトです。</span><span class="sxs-lookup"><span data-stu-id="14741-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14741-118">要件</span><span class="sxs-lookup"><span data-stu-id="14741-118">Requirements</span></span>  
 <span data-ttu-id="14741-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14741-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14741-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14741-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14741-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14741-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14741-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14741-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14741-123">参照</span><span class="sxs-lookup"><span data-stu-id="14741-123">See also</span></span>

- [<span data-ttu-id="14741-124">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14741-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
