---
title: ICorProfilerCallback3::InitializeForAttach メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: d0219751987b1f2d78ee37a1553b323014c1ccfe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865689"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="40b64-102">ICorProfilerCallback3::InitializeForAttach メソッド</span><span class="sxs-lookup"><span data-stu-id="40b64-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="40b64-103">アタッチ操作後にその状態を初期化する機会をプロファイラーに与えるために、共通言語ランタイム (CLR) により呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="40b64-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b64-104">構文</span><span class="sxs-lookup"><span data-stu-id="40b64-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40b64-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40b64-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="40b64-106">[in] `ICorProfilerInfo*` インターフェイスへのインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="40b64-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="40b64-107">から`pvClientData` パラメーターで[IClrProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md)メソッドに渡されるデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="40b64-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="40b64-108">このパラメーターが null の場合、`cbClientData` は 0 (ゼロ) になります。</span><span class="sxs-lookup"><span data-stu-id="40b64-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="40b64-109">CLR は、`InitializeForAttach` から戻るとこのメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="40b64-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="40b64-110">[in] `pvClientData` がポイントするデータのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="40b64-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40b64-111">コメント</span><span class="sxs-lookup"><span data-stu-id="40b64-111">Remarks</span></span>  
 <span data-ttu-id="40b64-112">CLR は `InitializeForAttach` を呼び出し、コールバックを要求できる機会をプロファイラーに与えます。</span><span class="sxs-lookup"><span data-stu-id="40b64-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40b64-113">要件</span><span class="sxs-lookup"><span data-stu-id="40b64-113">Requirements</span></span>  
 <span data-ttu-id="40b64-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40b64-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40b64-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40b64-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40b64-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40b64-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40b64-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40b64-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b64-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="40b64-118">See also</span></span>

- [<span data-ttu-id="40b64-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40b64-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="40b64-120">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40b64-120">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="40b64-121">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="40b64-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="40b64-122">プロファイル</span><span class="sxs-lookup"><span data-stu-id="40b64-122">Profiling</span></span>](index.md)
