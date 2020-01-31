---
title: ICorProfilerInfo4::GetObjectSize2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: 441f7743ba01884592393ce9382348fbecaeaa9d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861880"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="80b0a-102">ICorProfilerInfo4::GetObjectSize2 メソッド</span><span class="sxs-lookup"><span data-stu-id="80b0a-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="80b0a-103">指定したオブジェクトのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="80b0a-103">Returns the size of a specified object.</span></span> <span data-ttu-id="80b0a-104">`ULONG`で表現できる値よりも大きいオブジェクトのサイズをレポートすることによって、 [ICorProfilerInfo:: GetObjectSize](icorprofilerinfo-getobjectsize-method.md)メソッドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="80b0a-104">Replaces the [ICorProfilerInfo::GetObjectSize](icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b0a-105">構文</span><span class="sxs-lookup"><span data-stu-id="80b0a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80b0a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="80b0a-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="80b0a-107">からオブジェクトの ID です。</span><span class="sxs-lookup"><span data-stu-id="80b0a-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="80b0a-108">入出力オブジェクトのサイズへのポインター (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="80b0a-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80b0a-109">コメント</span><span class="sxs-lookup"><span data-stu-id="80b0a-109">Remarks</span></span>  
 <span data-ttu-id="80b0a-110">多くの場合、同じ種類の異なるオブジェクトのサイズは同じです。</span><span class="sxs-lookup"><span data-stu-id="80b0a-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="80b0a-111">ただし、配列や文字列など、一部の型では、オブジェクトごとにサイズが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="80b0a-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80b0a-112">要件</span><span class="sxs-lookup"><span data-stu-id="80b0a-112">Requirements</span></span>  
 <span data-ttu-id="80b0a-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80b0a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80b0a-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="80b0a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="80b0a-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80b0a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80b0a-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80b0a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b0a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="80b0a-117">See also</span></span>

- [<span data-ttu-id="80b0a-118">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80b0a-118">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
