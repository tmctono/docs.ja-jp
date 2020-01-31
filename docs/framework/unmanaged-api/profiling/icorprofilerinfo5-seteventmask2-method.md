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
ms.openlocfilehash: 10e84b729c8af607165009a8591a69dbc1afcb1e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868383"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="71516-102">ICorProfilerInfo5::SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="71516-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="71516-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="71516-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="71516-104">プロファイラーが共通言語ランタイム (CLR) からイベント通知を受け取ることを希望するイベントの型を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="71516-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="71516-105">[ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)メソッドよりも多くの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="71516-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71516-106">構文</span><span class="sxs-lookup"><span data-stu-id="71516-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71516-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71516-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="71516-108">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="71516-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="71516-109">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="71516-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="71516-110">ビットは、 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="71516-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="71516-111">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="71516-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="71516-112">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="71516-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="71516-113">ビットは、 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="71516-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71516-114">コメント</span><span class="sxs-lookup"><span data-stu-id="71516-114">Remarks</span></span>  
 <span data-ttu-id="71516-115">`SetEventMask2` メソッドは、プロファイラーが登録するコールバックを設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="71516-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="71516-116">通常は、 [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)メソッドを呼び出して、どのビットが設定されているかを判断し、その `pdwEventsLow` と `pdwEventsHigh` 値および設定する新しいビットの論理 OR を実行してから、`SetEventMask2` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="71516-116">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="71516-117">このメソッドは、 [Seteventmask](icorprofilerinfo-seteventmask-method.md)メソッドの代替手段として推奨されます。</span><span class="sxs-lookup"><span data-stu-id="71516-117">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71516-118">要件</span><span class="sxs-lookup"><span data-stu-id="71516-118">Requirements</span></span>  
 <span data-ttu-id="71516-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71516-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71516-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71516-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71516-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71516-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71516-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71516-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71516-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="71516-123">See also</span></span>

- [<span data-ttu-id="71516-124">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71516-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="71516-125">GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="71516-125">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
