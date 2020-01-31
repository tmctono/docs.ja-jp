---
title: ICorProfilerCallback::JITInlining メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 3e13b17fb03530730a78f6889309f1993419574b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866214"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="824ec-102">ICorProfilerCallback::JITInlining メソッド</span><span class="sxs-lookup"><span data-stu-id="824ec-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="824ec-103">Just-in-time (JIT) コンパイラが、別の関数と共に関数を挿入しようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="824ec-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="824ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="824ec-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="824ec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="824ec-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="824ec-106">から`calleeId` 関数が挿入される関数の ID。</span><span class="sxs-lookup"><span data-stu-id="824ec-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="824ec-107">から挿入する関数の ID。</span><span class="sxs-lookup"><span data-stu-id="824ec-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="824ec-108">[out] 挿入を行うことができるように `true` します。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="824ec-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="824ec-109">コメント</span><span class="sxs-lookup"><span data-stu-id="824ec-109">Remarks</span></span>  
 <span data-ttu-id="824ec-110">プロファイラーは `pfShouldInline` を `false` に設定して、`calleeId` 関数が `callerId` 関数に挿入されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="824ec-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="824ec-111">また、プロファイラーは、 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)列挙体の COR_PRF_DISABLE_INLINING 値を使用して、インライン挿入をグローバルに無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="824ec-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="824ec-112">インラインで挿入された関数は、入力または終了するためのイベントを発生させません。</span><span class="sxs-lookup"><span data-stu-id="824ec-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="824ec-113">したがって、正確なコールグラフを生成するためには、プロファイラーで `pfShouldInline` を `false` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="824ec-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="824ec-114">`pfShouldInline` を `false` に設定すると、パフォーマンスに影響します。インライン挿入では通常、速度が向上し、挿入されたメソッドの個別の JIT コンパイルイベントの数が減少するためです。</span><span class="sxs-lookup"><span data-stu-id="824ec-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="824ec-115">要件</span><span class="sxs-lookup"><span data-stu-id="824ec-115">Requirements</span></span>  
 <span data-ttu-id="824ec-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="824ec-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="824ec-117">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="824ec-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="824ec-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="824ec-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="824ec-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="824ec-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824ec-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="824ec-120">See also</span></span>

- [<span data-ttu-id="824ec-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="824ec-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
