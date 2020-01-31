---
title: ICorDebugFunction3::GetActiveReJitRequestILCode メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 70a55b833acb7fa946c694a63e1e8b51562938bc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777725"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="1f451-102">ICorDebugFunction3::GetActiveReJitRequestILCode メソッド</span><span class="sxs-lookup"><span data-stu-id="1f451-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="1f451-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="1f451-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1f451-104">アクティブな ReJIT 要求から IL を含む、[コード](icordebugilcode-interface.md)へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f451-104">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f451-105">構文</span><span class="sxs-lookup"><span data-stu-id="1f451-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f451-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f451-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="1f451-107">アクティブな ReJIT 要求からの、IL へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f451-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f451-108">コメント</span><span class="sxs-lookup"><span data-stu-id="1f451-108">Remarks</span></span>  
 <span data-ttu-id="1f451-109">この `ICorDebugFunction3` オブジェクトによって表示されるメソッドがアクティブな ReJIT 要求を持っている場合、`ppReJitedILCode` は IL へのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="1f451-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="1f451-110">一般的なケースであるアクティブな要求がない場合、`ppReJitedILCode` は**null**になります。</span><span class="sxs-lookup"><span data-stu-id="1f451-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="1f451-111">ReJIT 要求は、 [ICorProfilerCallback4:: GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)メソッドの呼び出しから実行が戻った直後にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="1f451-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="1f451-112">これは、まだ JIT コンパイルされていない可能性があり、スレッドはコードの元のバージョンで実行中の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f451-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="1f451-113">ReJIT 要求は、 [ICorProfilerInfo4:: RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)メソッドへのプロファイラーの呼び出し中に非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="1f451-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="1f451-114">LI が戻された後であっても、スレッドは JIT 再コンパイル (ReJIT) されたコードで実行中の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f451-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f451-115">要件</span><span class="sxs-lookup"><span data-stu-id="1f451-115">Requirements</span></span>  
 <span data-ttu-id="1f451-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f451-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f451-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f451-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f451-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f451-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f451-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f451-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f451-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f451-120">See also</span></span>

- [<span data-ttu-id="1f451-121">ICorDebugFunction3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f451-121">ICorDebugFunction3 Interface</span></span>](icordebugfunction3-interface.md)
- [<span data-ttu-id="1f451-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f451-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1f451-123">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="1f451-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
