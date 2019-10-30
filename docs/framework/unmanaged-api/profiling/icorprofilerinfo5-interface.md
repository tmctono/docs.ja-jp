---
title: ICorProfilerInfo5 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: e6df5dcb26d61d30407d1efeeed7d207744276fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124185"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="7c46e-102">ICorProfilerInfo5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c46e-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="7c46e-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="7c46e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7c46e-104">イベント監視を制御するために、コードプロファイラーが共通言語ランタイム (CLR) と通信するために使用するメソッドを提供する[ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="7c46e-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c46e-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c46e-105">Methods</span></span>  
  
|<span data-ttu-id="7c46e-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c46e-106">Method</span></span>|<span data-ttu-id="7c46e-107">説明</span><span class="sxs-lookup"><span data-stu-id="7c46e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c46e-108">GetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="7c46e-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="7c46e-109">プロファイラーが CLR からの通知を受信するための現在のイベント カテゴリーを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c46e-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="7c46e-110">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="7c46e-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="7c46e-111">プロファイラーが CLR からのイベント通知を受信するためのイベントの種類を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c46e-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c46e-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c46e-112">Remarks</span></span>  
 <span data-ttu-id="7c46e-113">このインターフェイスで使用できるメソッドは、 [ICorProfilerInfo:: geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)メソッドと[ICorProfilerInfo:: seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッドを置き換えることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="7c46e-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c46e-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="7c46e-114">Requirements</span></span>  
 <span data-ttu-id="7c46e-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c46e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c46e-116">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c46e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c46e-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c46e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c46e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c46e-118">See also</span></span>

- [<span data-ttu-id="7c46e-119">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c46e-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
