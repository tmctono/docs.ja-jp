---
title: ICorProfilerInfo::GetEventMask メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1051f42788b3c2a63780f43f5784b063ef23027
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483992"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="04f64-102">ICorProfilerInfo::GetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="04f64-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="04f64-103">現在のイベント カテゴリを取得します。プロファイラーは、これに関するイベント通知を共通言語ランタイム (CLR) から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="04f64-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f64-104">構文</span><span class="sxs-lookup"><span data-stu-id="04f64-104">Syntax</span></span>  
  
```  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f64-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04f64-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="04f64-106">[out] イベントのカテゴリを指定する 4 バイト値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="04f64-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="04f64-107">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="04f64-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="04f64-108">ビットが記載されて、 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="04f64-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04f64-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="04f64-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04f64-110">呼び出す必要があります、 [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)このメソッドではなくメソッド。</span><span class="sxs-lookup"><span data-stu-id="04f64-110">You should call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="04f64-111">ただし、`SetEventMask`メソッドが引き続きサポートされますが、 [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="04f64-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f64-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="04f64-112">Requirements</span></span>  
 <span data-ttu-id="04f64-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04f64-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f64-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04f64-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04f64-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04f64-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04f64-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04f64-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f64-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="04f64-117">See also</span></span>
- [<span data-ttu-id="04f64-118">GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="04f64-118">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="04f64-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04f64-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
