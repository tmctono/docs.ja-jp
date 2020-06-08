---
title: ICorProfilerCallback::JITFunctionPitched メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 2715a5b6b03a5ad33a6f18fb736fce3911bfbef0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500027"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="1b9e4-102">ICorProfilerCallback::JITFunctionPitched メソッド</span><span class="sxs-lookup"><span data-stu-id="1b9e4-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="1b9e4-103">Just-in-time (JIT) でコンパイルされた関数がメモリから削除されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1b9e4-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b9e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b9e4-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b9e4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b9e4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="1b9e4-106">から削除された関数の ID。</span><span class="sxs-lookup"><span data-stu-id="1b9e4-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b9e4-107">解説</span><span class="sxs-lookup"><span data-stu-id="1b9e4-107">Remarks</span></span>  
 <span data-ttu-id="1b9e4-108">削除された関数が呼び出されると、関数が再コンパイルされると、プロファイラーは新しい JIT コンパイルイベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1b9e4-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="1b9e4-109">現在、共通言語ランタイム (CLR) の JIT コンパイラでは、メモリから関数が削除されないため、このコールバックは現在使用されていないため、プロファイラーによって受信されません。</span><span class="sxs-lookup"><span data-stu-id="1b9e4-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="1b9e4-110">の値 `functionId` は、関数が再コンパイルされるまで有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="1b9e4-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="1b9e4-111">関数を再コンパイルすると、同じ `functionId` 値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b9e4-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b9e4-112">要件</span><span class="sxs-lookup"><span data-stu-id="1b9e4-112">Requirements</span></span>  
 <span data-ttu-id="1b9e4-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b9e4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b9e4-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b9e4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b9e4-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b9e4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b9e4-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b9e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9e4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b9e4-117">See also</span></span>

- [<span data-ttu-id="1b9e4-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b9e4-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
