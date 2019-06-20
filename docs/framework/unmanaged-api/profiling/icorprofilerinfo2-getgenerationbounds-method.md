---
title: ICorProfilerInfo2::GetGenerationBounds メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 310bde2889f8a383fde88cb1bbffce9bad157399
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267994"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="c0821-102">ICorProfilerInfo2::GetGenerationBounds メソッド</span><span class="sxs-lookup"><span data-stu-id="c0821-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="c0821-103">各種ガベージ コレクション ジェネレーションを構成するメモリ領域 (ヒープのセグメント) を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0821-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0821-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0821-104">Syntax</span></span>  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0821-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0821-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="c0821-106">[in] `ranges` 配列の呼び出し元によって割り当てられた要素の数。</span><span class="sxs-lookup"><span data-stu-id="c0821-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="c0821-107">[out] その一部または全部が `ranges` 配列で返される範囲の総数を指定する整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0821-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="c0821-108">[out]配列の[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)構造体、ガベージ コレクション ジェネレーション内、メモリの範囲 (ブロック) それぞれについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c0821-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0821-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0821-109">Remarks</span></span>  
 <span data-ttu-id="c0821-110">ガベージ コレクションを処理中でない場合、`GetGenerationBounds` メソッドは任意のプロファイラー コールバックから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c0821-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="c0821-111">通常、ジェネレーションの移動はガベージ コレクション中に行われます。</span><span class="sxs-lookup"><span data-stu-id="c0821-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="c0821-112">コレクションの間にジェネレーションが増大する可能性はありますが、一般的に移動はありません。</span><span class="sxs-lookup"><span data-stu-id="c0821-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="c0821-113">したがって、`GetGenerationBounds` を呼び出す上で最も注目すべき地点は `ICorProfilerCallback2::GarbageCollectionStarted` と `ICorProfilerCallback2::GarbageCollectionFinished` の間です。</span><span class="sxs-lookup"><span data-stu-id="c0821-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="c0821-114">プログラムの起動中に、いくつかのオブジェクトが共通言語ランタイム (CLR) 自体によって割り当てられます。これは、一般的にはジェネレーションの 3 と 0 で行われます。</span><span class="sxs-lookup"><span data-stu-id="c0821-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="c0821-115">したがって、マネージド コードが実行を開始するまでに、これらのジェネレーションには既にオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0821-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="c0821-116">通常、ジェネレーションの 1 と 2 は、ガベージ コレクターによって生成されたダミー オブジェクトを除き、空です。</span><span class="sxs-lookup"><span data-stu-id="c0821-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="c0821-117">(ダミー オブジェクトのサイズは、CLR の 32 ビット実装で 12 バイト、64 ビット実装ではそれよりも大きくなります。)ジェネレーション 2 の範囲がネイティブ イメージ ジェネレーター (NGen.exe) によって作成されたモジュール内のこともあります。</span><span class="sxs-lookup"><span data-stu-id="c0821-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="c0821-118">ジェネレーション 2 のオブジェクトは、この場合、*固定オブジェクト*、ガベージ コレクターではなく、NGen.exe 実行時にこれが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c0821-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="c0821-119">この関数は、呼び出し元が割り当てたバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0821-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0821-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0821-120">Requirements</span></span>  
 <span data-ttu-id="c0821-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0821-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0821-122">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0821-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0821-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0821-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0821-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0821-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0821-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0821-125">See also</span></span>

- [<span data-ttu-id="c0821-126">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0821-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c0821-127">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0821-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="c0821-128">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0821-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c0821-129">プロファイル</span><span class="sxs-lookup"><span data-stu-id="c0821-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
