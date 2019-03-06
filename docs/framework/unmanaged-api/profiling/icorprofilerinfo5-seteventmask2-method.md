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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22a783b7564c3545edea93bf4faca1fc40b54cec
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499798"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="ccc64-102">ICorProfilerInfo5::SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="ccc64-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="ccc64-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="ccc64-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ccc64-104">プロファイラーが共通言語ランタイム (CLR) からイベント通知を受け取ることを希望するイベントの型を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="ccc64-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="ccc64-105">多くの機能を提供しますが、 [icorprofilerinfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ccc64-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc64-106">構文</span><span class="sxs-lookup"><span data-stu-id="ccc64-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccc64-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ccc64-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="ccc64-108">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="ccc64-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="ccc64-109">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="ccc64-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ccc64-110">ビットが記載されて、 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="ccc64-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="ccc64-111">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="ccc64-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="ccc64-112">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="ccc64-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ccc64-113">ビットが記載されて、 [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="ccc64-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccc64-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ccc64-114">Remarks</span></span>  
 <span data-ttu-id="ccc64-115">
  `SetEventMask2\` メソッドは、プロファイラーが登録するコールバックを設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ccc64-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="ccc64-116">通常を呼び出す、 [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)のどのビットが設定されているかを判断するメソッドの論理 OR を実行するその`pdwEventsLow`と`pdwEventsHigh`値と新しいビットを設定し、呼び出すたい、`SetEventMask2`メソッド。</span><span class="sxs-lookup"><span data-stu-id="ccc64-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="ccc64-117">このメソッドは、推奨される代替、 [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="ccc64-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc64-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="ccc64-118">Requirements</span></span>  
 <span data-ttu-id="ccc64-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccc64-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccc64-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ccc64-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ccc64-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccc64-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccc64-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc64-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc64-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccc64-123">See also</span></span>
- [<span data-ttu-id="ccc64-124">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ccc64-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="ccc64-125">GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="ccc64-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
