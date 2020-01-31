---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 5822136eb1a7f582bcfae901a99775950e586198
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863180"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="8f48c-102">ICorProfilerInfo10:: RequestReJITWithInliners メソッド</span><span class="sxs-lookup"><span data-stu-id="8f48c-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="8f48c-103">要求されたメソッドのほか、要求されたメソッドの inliners を再適用します。</span><span class="sxs-lookup"><span data-stu-id="8f48c-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f48c-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f48c-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="8f48c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f48c-105">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="8f48c-106">\[] [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md)のビットマスク。</span><span class="sxs-lookup"><span data-stu-id="8f48c-106">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="8f48c-107">\[] 再コンパイルする関数の数。</span><span class="sxs-lookup"><span data-stu-id="8f48c-107">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="8f48c-108">\[in] 再コンパイルする関数を識別する (`module`、`methodDef`) のペアの `moduleId` の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f48c-108">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="8f48c-109">\[in] 再コンパイルする関数を識別する (`module`、`methodDef`) のペアの `methodId` の部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f48c-109">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f48c-110">コメント</span><span class="sxs-lookup"><span data-stu-id="8f48c-110">Remarks</span></span>

<span data-ttu-id="8f48c-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md)では、インラインメソッドの追跡は行われません。</span><span class="sxs-lookup"><span data-stu-id="8f48c-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="8f48c-112">プロファイラーは、インライン化されたメソッドのすべてのインスタンスが ReJITted であることを確認するために、インライン展開をブロックするか、インライン展開を追跡し、すべての inliners に対して `RequestReJIT` を呼び出す必要がありました。</span><span class="sxs-lookup"><span data-stu-id="8f48c-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="8f48c-113">これにより、再インライン化を監視するためのプロファイラーが存在しないため、ReJIT on attach に問題が生じます。</span><span class="sxs-lookup"><span data-stu-id="8f48c-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="8f48c-114">このメソッドを呼び出すことにより、inliners の完全なセットも ReJITted になることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="8f48c-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f48c-115">要件</span><span class="sxs-lookup"><span data-stu-id="8f48c-115">Requirements</span></span>

<span data-ttu-id="8f48c-116">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f48c-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="8f48c-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f48c-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="8f48c-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f48c-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8f48c-119">**.Net のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f48c-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8f48c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f48c-120">See also</span></span>

- [<span data-ttu-id="8f48c-121">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f48c-121">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
