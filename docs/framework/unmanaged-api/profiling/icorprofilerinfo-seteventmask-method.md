---
title: ICorProfilerInfo::SetEventMask メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 122a621552b49f476f219216ac0a52011c1542ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103949"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="6d351-102">ICorProfilerInfo::SetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="6d351-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="6d351-103">共通言語ランタイム (CLR) からの通知を受け取るプロファイラーに対するイベントの種類を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6d351-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d351-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d351-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d351-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d351-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="6d351-106">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="6d351-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="6d351-107">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="6d351-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="6d351-108">ビットが記載されて、 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="6d351-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d351-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d351-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d351-110">呼び出す必要があります、 [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)このメソッドではなくメソッド。</span><span class="sxs-lookup"><span data-stu-id="6d351-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="6d351-111">ただし、`SetEventMask`メソッドが引き続きサポートされますが、 [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d351-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d351-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6d351-112">Requirements</span></span>  
 <span data-ttu-id="6d351-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d351-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d351-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d351-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d351-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d351-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d351-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d351-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d351-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d351-117">See also</span></span>

- [<span data-ttu-id="6d351-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d351-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="6d351-119">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="6d351-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
