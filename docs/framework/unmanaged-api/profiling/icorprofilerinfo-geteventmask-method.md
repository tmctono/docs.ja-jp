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
ms.openlocfilehash: 63f19fe899abd75380249e171f248480949bc471
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863908"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="874a7-102">ICorProfilerInfo::GetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="874a7-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="874a7-103">現在のイベント カテゴリを取得します。プロファイラーは、これに関するイベント通知を共通言語ランタイム (CLR) から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="874a7-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874a7-104">構文</span><span class="sxs-lookup"><span data-stu-id="874a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="874a7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="874a7-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="874a7-106">[out] イベントのカテゴリを指定する 4 バイト値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="874a7-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="874a7-107">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="874a7-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="874a7-108">ビットは、 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="874a7-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="874a7-109">コメント</span><span class="sxs-lookup"><span data-stu-id="874a7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="874a7-110">このメソッドではなく、 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="874a7-110">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="874a7-111">`SetEventMask` メソッドは引き続きサポートされますが、 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)には追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="874a7-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="874a7-112">要件</span><span class="sxs-lookup"><span data-stu-id="874a7-112">Requirements</span></span>  
 <span data-ttu-id="874a7-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="874a7-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="874a7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="874a7-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="874a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="874a7-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="874a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874a7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="874a7-117">See also</span></span>

- [<span data-ttu-id="874a7-118">GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="874a7-118">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="874a7-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="874a7-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
