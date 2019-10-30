---
title: ICorProfilerInfo5::GetEventMask2 メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: 2e814eaba04fd6781d10bbcb67ade9acdefa161d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114744"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="42fa0-102">ICorProfilerInfo5::GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="42fa0-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="42fa0-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="42fa0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="42fa0-104">現在のイベント カテゴリを取得します。プロファイラーは、これに関する通知を共通言語ランタイム (CLR) から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="42fa0-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="42fa0-105">[ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)メソッドで提供されていない機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="42fa0-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42fa0-106">構文</span><span class="sxs-lookup"><span data-stu-id="42fa0-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42fa0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42fa0-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="42fa0-108">[out] イベントのカテゴリを指定する 4 バイト値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="42fa0-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="42fa0-109">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="42fa0-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="42fa0-110">ビットは、 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="42fa0-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="42fa0-111">[out] イベントのカテゴリを指定する 4 バイト値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="42fa0-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="42fa0-112">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="42fa0-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="42fa0-113">ビットは、 [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="42fa0-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42fa0-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="42fa0-114">Remarks</span></span>  
 <span data-ttu-id="42fa0-115">`GetEventMask2` メソッドは、プロファイラーがサブスクライブしたコールバックを判断するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="42fa0-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="42fa0-116">通常は、`pdwEventsLow` と `pdwEventsHigh` 値と、設定する新しいビットの論理 OR を実行し、次に[SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="42fa0-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="42fa0-117">このメソッドは、 [Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)メソッドの代替手段として推奨されます。</span><span class="sxs-lookup"><span data-stu-id="42fa0-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42fa0-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="42fa0-118">Requirements</span></span>  
 <span data-ttu-id="42fa0-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42fa0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42fa0-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42fa0-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42fa0-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42fa0-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42fa0-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42fa0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42fa0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="42fa0-123">See also</span></span>

- [<span data-ttu-id="42fa0-124">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42fa0-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="42fa0-125">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="42fa0-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
