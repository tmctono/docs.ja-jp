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
ms.openlocfilehash: f7dee16373fc67580130c57482a130ba02f50204
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497466"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="49f37-102">ICorProfilerInfo::SetEventMask メソッド</span><span class="sxs-lookup"><span data-stu-id="49f37-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="49f37-103">共通言語ランタイム (CLR) からの通知を受け取るプロファイラーに対するイベントの種類を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="49f37-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f37-104">構文</span><span class="sxs-lookup"><span data-stu-id="49f37-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49f37-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="49f37-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="49f37-106">[in] イベントのカテゴリを指定する 4 バイトの値。</span><span class="sxs-lookup"><span data-stu-id="49f37-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="49f37-107">各ビットは、異なる性能、動作、またはイベントの型を制御します。</span><span class="sxs-lookup"><span data-stu-id="49f37-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="49f37-108">ビットは、 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)列挙体に記述されています。</span><span class="sxs-lookup"><span data-stu-id="49f37-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49f37-109">解説</span><span class="sxs-lookup"><span data-stu-id="49f37-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49f37-110">このメソッドではなく、 [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="49f37-110">You should call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="49f37-111">メソッドは `SetEventMask` 引き続きサポートされますが、 [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)には追加機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="49f37-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f37-112">要件</span><span class="sxs-lookup"><span data-stu-id="49f37-112">Requirements</span></span>  
 <span data-ttu-id="49f37-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49f37-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49f37-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49f37-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49f37-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49f37-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49f37-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49f37-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f37-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="49f37-117">See also</span></span>

- [<span data-ttu-id="49f37-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49f37-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="49f37-119">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="49f37-119">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
