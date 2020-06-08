---
title: ICorProfilerInfo2::GetBoxClassLayout メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: 630b67a64716f26577bbc376970e4f76216f4da5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497355"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="2bd9a-102">ICorProfilerInfo2::GetBoxClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="2bd9a-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="2bd9a-103">指定された値型がボックス化されている場合の位置に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2bd9a-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd9a-104">構文</span><span class="sxs-lookup"><span data-stu-id="2bd9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bd9a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2bd9a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2bd9a-106">からボックス化された値の型を記述するクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="2bd9a-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="2bd9a-107">入出力値型のボックス化されたオブジェクト ID ポインターを基準とするオフセットを表す整数。</span><span class="sxs-lookup"><span data-stu-id="2bd9a-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bd9a-108">解説</span><span class="sxs-lookup"><span data-stu-id="2bd9a-108">Remarks</span></span>  
 <span data-ttu-id="2bd9a-109">`pBufferOffset`値は、ボックス内の値の型の場所です。</span><span class="sxs-lookup"><span data-stu-id="2bd9a-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="2bd9a-110">ボックス化されたオブジェクトにを適用した後 `pBufferOffset` 、値型のクラスレイアウトを使用して、オブジェクトの値を解釈できます。</span><span class="sxs-lookup"><span data-stu-id="2bd9a-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bd9a-111">要件</span><span class="sxs-lookup"><span data-stu-id="2bd9a-111">Requirements</span></span>  
 <span data-ttu-id="2bd9a-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bd9a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bd9a-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2bd9a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2bd9a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bd9a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bd9a-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bd9a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd9a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bd9a-116">See also</span></span>

- [<span data-ttu-id="2bd9a-117">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bd9a-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2bd9a-118">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2bd9a-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
