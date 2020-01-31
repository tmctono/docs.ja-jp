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
ms.openlocfilehash: 49e154ade91ea1a207645f924bd8aea1dbdb635c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868123"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="e340f-102">StackSnapshotCallback 関数</span><span class="sxs-lookup"><span data-stu-id="e340f-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="e340f-103">[ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md)メソッドによって開始されるスタックウォーク中に、各マネージフレームおよびスタック上のアンマネージフレームの各実行に関する情報をプロファイラーに提供します。</span><span class="sxs-lookup"><span data-stu-id="e340f-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e340f-104">構文</span><span class="sxs-lookup"><span data-stu-id="e340f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e340f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e340f-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="e340f-106">からこの値が0の場合、このコールバックはアンマネージフレームの実行用です。それ以外の場合は、マネージ関数の識別子であり、このコールバックはマネージフレーム用です。</span><span class="sxs-lookup"><span data-stu-id="e340f-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="e340f-107">からフレーム内のネイティブコード命令ポインターの値。</span><span class="sxs-lookup"><span data-stu-id="e340f-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="e340f-108">からスタックフレームに関する情報を参照する `COR_PRF_FRAME_INFO` 値。</span><span class="sxs-lookup"><span data-stu-id="e340f-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="e340f-109">この値は、このコールバック中にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e340f-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e340f-110">から`context` パラメーターによって参照される `CONTEXT` 構造体のサイズ。</span><span class="sxs-lookup"><span data-stu-id="e340f-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="e340f-111">からこのフレームの CPU の状態を表す Win32 `CONTEXT` 構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e340f-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="e340f-112">`context` パラメーターは `ICorProfilerInfo2::DoStackSnapshot`で COR_PRF_SNAPSHOT_CONTEXT フラグが渡された場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e340f-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="e340f-113">から`ICorProfilerInfo2::DoStackSnapshot`から直接渡されるクライアントデータへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e340f-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e340f-114">コメント</span><span class="sxs-lookup"><span data-stu-id="e340f-114">Remarks</span></span>  
 <span data-ttu-id="e340f-115">`StackSnapshotCallback` 関数は、プロファイラーライターによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="e340f-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="e340f-116">`StackSnapshotCallback`で実行する作業の複雑さを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e340f-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="e340f-117">たとえば、非同期方式で `ICorProfilerInfo2::DoStackSnapshot` を使用する場合、ターゲットスレッドがロックを保持している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e340f-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="e340f-118">`StackSnapshotCallback` 内のコードで同じロックが要求された場合、デッドロックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e340f-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="e340f-119">`ICorProfilerInfo2::DoStackSnapshot` メソッドは、マネージフレームごとに1回、またはアンマネージフレームの実行ごとに1回、`StackSnapshotCallback` 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e340f-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="e340f-120">アンマネージフレームの実行に対して `StackSnapshotCallback` が呼び出された場合、プロファイラーは、(`context` パラメーターによって参照される) レジスタコンテキストを使用して、独自のアンマネージスタックウォークを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e340f-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="e340f-121">この場合、Win32 `CONTEXT` 構造体は、アンマネージフレームの実行中に最後にプッシュされたフレームの CPU 状態を表します。</span><span class="sxs-lookup"><span data-stu-id="e340f-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="e340f-122">Win32 `CONTEXT` 構造体にはすべてのレジスタの値が含まれていますが、スタックポインターレジスタ、フレームポインターレジスタ、命令ポインターレジスタ、および不揮発性の (つまり、保持されている) 整数レジスタの値のみに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e340f-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e340f-123">要件</span><span class="sxs-lookup"><span data-stu-id="e340f-123">Requirements</span></span>  
 <span data-ttu-id="e340f-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e340f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e340f-125">**ヘッダー:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="e340f-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e340f-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e340f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e340f-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e340f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e340f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e340f-128">See also</span></span>

- [<span data-ttu-id="e340f-129">DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="e340f-129">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="e340f-130">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="e340f-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
