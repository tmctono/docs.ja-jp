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
ms.openlocfilehash: f3943eef969f777b40dc51c4900b190561f14887
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868396"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="1b27e-102">ICorProfilerInfo5::GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="1b27e-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="1b27e-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="1b27e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1b27e-104">現在のイベント カテゴリを取得します。プロファイラーは、これに関する通知を共通言語ランタイム (CLR) から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1b27e-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="1b27e-105">[ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md)メソッドで提供されていない機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b27e-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b27e-106">構文</span><span class="sxs-lookup"><span data-stu-id="1b27e-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b27e-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b27e-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="1b27e-108">[out] イベントのカテゴリを指定する 4 バイト値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1b27e-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="1b27e-109">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="1b27e-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="1b27e-110">ビットは、 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="1b27e-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="1b27e-111">[out] イベントのカテゴリを指定する 4 バイト値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1b27e-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="1b27e-112">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="1b27e-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="1b27e-113">ビットは、 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="1b27e-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b27e-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b27e-114">Remarks</span></span>  
 <span data-ttu-id="1b27e-115">`GetEventMask2` メソッドは、プロファイラーがサブスクライブしたコールバックを判断するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="1b27e-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="1b27e-116">通常は、`pdwEventsLow` と `pdwEventsHigh` 値と、設定する新しいビットの論理 OR を実行し、次に[SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1b27e-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="1b27e-117">このメソッドは、 [Geteventmask](icorprofilerinfo-geteventmask-method.md)メソッドの代替手段として推奨されます。</span><span class="sxs-lookup"><span data-stu-id="1b27e-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b27e-118">要件</span><span class="sxs-lookup"><span data-stu-id="1b27e-118">Requirements</span></span>  
 <span data-ttu-id="1b27e-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b27e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b27e-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b27e-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b27e-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b27e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b27e-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b27e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b27e-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b27e-123">See also</span></span>

- [<span data-ttu-id="1b27e-124">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b27e-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="1b27e-125">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="1b27e-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
