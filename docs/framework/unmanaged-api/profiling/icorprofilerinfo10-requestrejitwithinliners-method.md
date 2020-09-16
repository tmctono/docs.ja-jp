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
ms.openlocfilehash: e3d5a09730cb8e477bd506749017a403acff1696
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540562"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="1f9f8-102">ICorProfilerInfo10:: RequestReJITWithInliners メソッド</span><span class="sxs-lookup"><span data-stu-id="1f9f8-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="1f9f8-103">要求されたメソッドのほか、要求されたメソッドの inliners を再適用します。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f9f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f9f8-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="1f9f8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f9f8-105">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="1f9f8-106">\[in) [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md)のビットマスク。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-106">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="1f9f8-107">\[in] 再コンパイルする関数の数。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-107">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="1f9f8-108">\[in] は、再 `moduleId` `module` コンパイルする関数を識別する (、) ペアの部分を指定し `methodDef` ます。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-108">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="1f9f8-109">\[in] は、再 `methodId` `module` コンパイルする関数を識別する (、) ペアの部分を指定し `methodDef` ます。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-109">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f9f8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f9f8-110">Remarks</span></span>

<span data-ttu-id="1f9f8-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) では、インラインメソッドの追跡は行われません。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="1f9f8-112">プロファイラーは、インライン化された `RequestReJIT` メソッドのすべてのインスタンスが ReJITted であることを確認するために、インライン展開をブロックするか、インライン展開を追跡し、すべての inliners に対してを呼び出す必要がありました</span><span class="sxs-lookup"><span data-stu-id="1f9f8-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="1f9f8-113">これにより、再インライン化を監視するためのプロファイラーが存在しないため、ReJIT on attach に問題が生じます。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="1f9f8-114">このメソッドを呼び出すことにより、inliners の完全なセットも ReJITted になることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f9f8-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f9f8-115">Requirements</span></span>

<span data-ttu-id="1f9f8-116">**プラットフォーム:** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/install/windows.md?pivots=os-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="1f9f8-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f9f8-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1f9f8-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f9f8-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1f9f8-119">**.Net のバージョン:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f9f8-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1f9f8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f9f8-120">See also</span></span>

- [<span data-ttu-id="1f9f8-121">ICorProfilerInfo10 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f9f8-121">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
