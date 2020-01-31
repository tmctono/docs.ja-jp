---
title: ICorProfilerInfo4 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: c287b630aee58c6795ef405cc1801149e220fd51
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868422"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="d3c37-102">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3c37-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="d3c37-103">コードプロファイラーが共通言語ランタイム (CLR) と通信してイベント監視と要求情報を制御するために使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="d3c37-104">を確認しています。</span><span class="sxs-lookup"><span data-stu-id="d3c37-104">.</span></span> <span data-ttu-id="d3c37-105">`ICorProfilerInfo4` インターフェイスは、他の `ICorProfilerInfo` インターフェイスの拡張です。</span><span class="sxs-lookup"><span data-stu-id="d3c37-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="d3c37-106">これには、just-in-time (JIT) の再コンパイルをサポートする新しいメソッドが用意されており、.NET Framework 4.5 に追加されています。</span><span class="sxs-lookup"><span data-stu-id="d3c37-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3c37-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-107">Methods</span></span>  
  
|<span data-ttu-id="d3c37-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-108">Method</span></span>|<span data-ttu-id="d3c37-109">説明</span><span class="sxs-lookup"><span data-stu-id="d3c37-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3c37-110">EnumJITedFunctions2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-110">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="d3c37-111">以前に JIT コンパイルおよび JIT 再コンパイルされたすべての関数の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="d3c37-112">EnumThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-112">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="d3c37-113">プロファイリングされたプロセス内のすべてのマネージスレッドのコレクションを順番に反復処理するメソッドを提供する列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="d3c37-114">GetCodeInfo3 メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-114">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="d3c37-115">指定した関数の JIT 再コンパイル バージョンに関連付けられているネイティブ コードの範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="d3c37-116">GetFunctionFromIP2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-116">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="d3c37-117">マネージコード命令ポインターを、指定された関数の JIT 再コンパイルバージョンにマップします。</span><span class="sxs-lookup"><span data-stu-id="d3c37-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="d3c37-118">GetILToNativeMapping2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-118">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="d3c37-119">Microsoft 中間言語 (MSIL) オフセットから、指定した関数の JIT 再コンパイルバージョンに含まれるコードのネイティブオフセットへのマップを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="d3c37-120">GetObjectSize2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-120">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="d3c37-121">指定したオブジェクトのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="d3c37-122">GetReJITIDs メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-122">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="d3c37-123">割り当てられている指定された関数のすべての JIT 再コンパイルバージョンを識別する Id の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="d3c37-124">InitializeCurrentThread メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-124">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="d3c37-125">デッドロックを回避できるように、同じスレッドで、後続のプロファイラー API 呼び出しの前に現在のスレッドを初期化します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="d3c37-126">RequestReJIT メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-126">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="d3c37-127">指定された関数のすべてのインスタンスの JIT 再コンパイルを要求します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="d3c37-128">RequestRevert メソッド</span><span class="sxs-lookup"><span data-stu-id="d3c37-128">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="d3c37-129">指定された関数のすべてのインスタンスを元のバージョンに戻します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3c37-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3c37-130">Remarks</span></span>  
 <span data-ttu-id="d3c37-131">CLR は、`ICorProfilerInfo4` インターフェイスのメソッドを、フリー スレッド モデルを使用して実装します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="d3c37-132">各メソッドが、成功または失敗を示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c37-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="d3c37-133">返される可能性があるリターン コードの一覧については、CorError.h ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c37-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3c37-134">要件</span><span class="sxs-lookup"><span data-stu-id="d3c37-134">Requirements</span></span>  
 <span data-ttu-id="d3c37-135">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c37-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3c37-136">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3c37-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3c37-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3c37-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3c37-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3c37-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c37-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3c37-139">See also</span></span>

- [<span data-ttu-id="d3c37-140">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3c37-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d3c37-141">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3c37-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
