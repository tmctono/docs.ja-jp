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
ms.openlocfilehash: 2ad2092c902b137df0dfe108743ef4081ca5f04d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948113"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="1aca9-102">ICorProfilerInfo::GetObjectSize メソッド</span><span class="sxs-lookup"><span data-stu-id="1aca9-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="1aca9-103">指定したオブジェクトのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="1aca9-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aca9-104">構文</span><span class="sxs-lookup"><span data-stu-id="1aca9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aca9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1aca9-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="1aca9-106">からオブジェクトの ID です。</span><span class="sxs-lookup"><span data-stu-id="1aca9-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="1aca9-107">入出力オブジェクトのサイズへのポインター (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="1aca9-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aca9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1aca9-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1aca9-109">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="1aca9-109">This method is obsolete.</span></span> <span data-ttu-id="1aca9-110">64ビットプラットフォームで 4 GB を超えるオブジェクトの COR_E_OVERFLOW を返します。</span><span class="sxs-lookup"><span data-stu-id="1aca9-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="1aca9-111">代わりに[ICorProfilerInfo4:: GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="1aca9-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="1aca9-112">多くの場合、同じ種類の異なるオブジェクトのサイズは同じです。</span><span class="sxs-lookup"><span data-stu-id="1aca9-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="1aca9-113">ただし、配列や文字列など、一部の型では、オブジェクトごとにサイズが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1aca9-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="1aca9-114">`GetObjectSize`メソッドによって返されるサイズには、オブジェクトがガベージコレクションヒープに配置された後に表示されるアラインメントの埋め込みは含まれません。</span><span class="sxs-lookup"><span data-stu-id="1aca9-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="1aca9-115">`GetObjectSize`メソッドを使用してオブジェクトからガベージコレクションヒープ上のオブジェクトに進む場合は、必要に応じて、手動でアラインメントのパディングを追加します。</span><span class="sxs-lookup"><span data-stu-id="1aca9-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="1aca9-116">32ビット Windows、COR_PRF_GC_GEN_0、COR_PRF_GC_GEN_1、および COR_PRF_GC_GEN_2 では、4バイトのアラインメントが使用され、COR_PRF_GC_LARGE_OBJECT_HEAP では8バイトのアラインメントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1aca9-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="1aca9-117">64ビットの Windows では、アラインメントは常に8バイトです。</span><span class="sxs-lookup"><span data-stu-id="1aca9-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aca9-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="1aca9-118">Requirements</span></span>  
 <span data-ttu-id="1aca9-119">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aca9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aca9-120">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="1aca9-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1aca9-121">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="1aca9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aca9-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aca9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aca9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="1aca9-123">See also</span></span>

- [<span data-ttu-id="1aca9-124">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1aca9-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
