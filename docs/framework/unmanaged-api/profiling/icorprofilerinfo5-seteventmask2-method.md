---
title: ICorProfilerInfo5::SetEventMask2 メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 1e1779c0f4f36b2d7b81832bc90cf5aee0b8a7df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130389"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="e5f23-102">ICorProfilerInfo5::SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e5f23-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="e5f23-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="e5f23-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e5f23-104">プロファイラーが共通言語ランタイム (CLR) からイベント通知を受け取ることを希望するイベントの型を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="e5f23-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="e5f23-105">[ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッドよりも多くの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e5f23-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f23-106">構文</span><span class="sxs-lookup"><span data-stu-id="e5f23-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5f23-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e5f23-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="e5f23-108">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="e5f23-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="e5f23-109">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="e5f23-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="e5f23-110">ビットは、 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="e5f23-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="e5f23-111">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="e5f23-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="e5f23-112">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="e5f23-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="e5f23-113">ビットは、 [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="e5f23-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5f23-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5f23-114">Remarks</span></span>  
 <span data-ttu-id="e5f23-115">`SetEventMask2` メソッドは、プロファイラーが登録するコールバックを設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e5f23-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="e5f23-116">通常は、 [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)メソッドを呼び出して、どのビットが設定されているかを判断し、その `pdwEventsLow` と `pdwEventsHigh` 値および設定する新しいビットの論理 OR を実行してから、`SetEventMask2` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e5f23-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="e5f23-117">このメソッドは、 [Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッドの代替手段として推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e5f23-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f23-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="e5f23-118">Requirements</span></span>  
 <span data-ttu-id="e5f23-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f23-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f23-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5f23-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5f23-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5f23-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5f23-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f23-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f23-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5f23-123">See also</span></span>

- [<span data-ttu-id="e5f23-124">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5f23-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="e5f23-125">GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e5f23-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
