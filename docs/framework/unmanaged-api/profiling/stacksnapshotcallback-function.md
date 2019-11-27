---
title: StackSnapshotCallback 関数
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: c0cec9eb7bb8bbc94b255152a9b4d79108bdd1b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427082"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="a2e71-102">StackSnapshotCallback 関数</span><span class="sxs-lookup"><span data-stu-id="a2e71-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="a2e71-103">[ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)メソッドによって開始されるスタックウォーク中に、各マネージフレームおよびスタック上のアンマネージフレームの各実行に関する情報をプロファイラーに提供します。</span><span class="sxs-lookup"><span data-stu-id="a2e71-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2e71-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2e71-104">Syntax</span></span>  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2e71-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2e71-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="a2e71-106">からこの値が0の場合、このコールバックはアンマネージフレームの実行用です。それ以外の場合は、マネージ関数の識別子であり、このコールバックはマネージフレーム用です。</span><span class="sxs-lookup"><span data-stu-id="a2e71-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="a2e71-107">からフレーム内のネイティブコード命令ポインターの値。</span><span class="sxs-lookup"><span data-stu-id="a2e71-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="a2e71-108">からスタックフレームに関する情報を参照する `COR_PRF_FRAME_INFO` 値。</span><span class="sxs-lookup"><span data-stu-id="a2e71-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="a2e71-109">この値は、このコールバック中にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2e71-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a2e71-110">から`context` パラメーターによって参照される `CONTEXT` 構造体のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a2e71-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="a2e71-111">からこのフレームの CPU の状態を表す Win32 `CONTEXT` 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2e71-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="a2e71-112">`context` パラメーターは `ICorProfilerInfo2::DoStackSnapshot`で COR_PRF_SNAPSHOT_CONTEXT フラグが渡された場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a2e71-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="a2e71-113">から`ICorProfilerInfo2::DoStackSnapshot`から直接渡されるクライアントデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a2e71-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2e71-114">コメント</span><span class="sxs-lookup"><span data-stu-id="a2e71-114">Remarks</span></span>  
 <span data-ttu-id="a2e71-115">`StackSnapshotCallback` 関数は、プロファイラーライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="a2e71-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="a2e71-116">`StackSnapshotCallback`で実行する作業の複雑さを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e71-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="a2e71-117">たとえば、非同期方式で `ICorProfilerInfo2::DoStackSnapshot` を使用する場合、ターゲットスレッドがロックを保持している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2e71-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="a2e71-118">`StackSnapshotCallback` 内のコードで同じロックが要求された場合、デッドロックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2e71-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="a2e71-119">`ICorProfilerInfo2::DoStackSnapshot` メソッドは、マネージフレームごとに1回、またはアンマネージフレームの実行ごとに1回、`StackSnapshotCallback` 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a2e71-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="a2e71-120">アンマネージフレームの実行に対して `StackSnapshotCallback` が呼び出された場合、プロファイラーは、(`context` パラメーターによって参照される) レジスタコンテキストを使用して、独自のアンマネージスタックウォークを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2e71-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="a2e71-121">この場合、Win32 `CONTEXT` 構造体は、アンマネージフレームの実行中に最後にプッシュされたフレームの CPU 状態を表します。</span><span class="sxs-lookup"><span data-stu-id="a2e71-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="a2e71-122">Win32 `CONTEXT` 構造体にはすべてのレジスタの値が含まれていますが、スタックポインターレジスタ、フレームポインターレジスタ、命令ポインターレジスタ、および不揮発性の (つまり、保持されている) 整数レジスタの値のみに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2e71-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2e71-123">要件</span><span class="sxs-lookup"><span data-stu-id="a2e71-123">Requirements</span></span>  
 <span data-ttu-id="a2e71-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2e71-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2e71-125">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="a2e71-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a2e71-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2e71-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2e71-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2e71-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2e71-128">参照</span><span class="sxs-lookup"><span data-stu-id="a2e71-128">See also</span></span>

- [<span data-ttu-id="a2e71-129">DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="a2e71-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="a2e71-130">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="a2e71-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
