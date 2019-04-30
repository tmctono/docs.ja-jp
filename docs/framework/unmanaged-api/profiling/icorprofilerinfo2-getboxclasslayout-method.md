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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4dac7e38d1e767a3edeef932a0c0916daffe24b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049571"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="71852-102">ICorProfilerInfo2::GetBoxClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="71852-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="71852-103">指定した値型の配置がボックス化されるときに場所に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="71852-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71852-104">構文</span><span class="sxs-lookup"><span data-stu-id="71852-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71852-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71852-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="71852-106">[in]値の型にボックス化を記述するクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="71852-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="71852-107">[out]ボックス化されたオブジェクト ID のポインター値の型の基準とした、オフセットを示す整数。</span><span class="sxs-lookup"><span data-stu-id="71852-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71852-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="71852-108">Remarks</span></span>  
 <span data-ttu-id="71852-109">`pBufferOffset`値は、値の型のボックス内の場所です。</span><span class="sxs-lookup"><span data-stu-id="71852-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="71852-110">後`pBufferOffset`が適用されるオブジェクトの値を解釈するボックス化されたオブジェクトに値型のクラス レイアウトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="71852-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71852-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="71852-111">Requirements</span></span>  
 <span data-ttu-id="71852-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71852-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71852-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71852-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71852-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71852-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71852-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71852-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71852-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="71852-116">See also</span></span>

- [<span data-ttu-id="71852-117">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71852-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="71852-118">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71852-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
