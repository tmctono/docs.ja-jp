---
title: ICorProfilerInfo4::GetFunctionFromIP2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
ms.openlocfilehash: 5153a25ef87d9c06bb46b74945c8eb68eb041682
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443145"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="e0e68-102">ICorProfilerInfo4::GetFunctionFromIP2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e0e68-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="e0e68-103">マネージコード命令ポインターを JIT 再コンパイルされた関数のバージョンにマップします。</span><span class="sxs-lookup"><span data-stu-id="e0e68-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e68-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0e68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0e68-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0e68-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="e0e68-106">からマネージコード内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="e0e68-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="e0e68-107">入出力関数 ID。</span><span class="sxs-lookup"><span data-stu-id="e0e68-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="e0e68-108">入出力関数の JIT 再コンパイルバージョンの id。</span><span class="sxs-lookup"><span data-stu-id="e0e68-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0e68-109">コメント</span><span class="sxs-lookup"><span data-stu-id="e0e68-109">Remarks</span></span>  
 <span data-ttu-id="e0e68-110">`GetFunctionFromIP2` は `GetFunctionFromIP`に似ていますが、指定された IP アドレスを含む関数の関数 ID ではなく、JIT 再コンパイルされた ID を取得する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="e0e68-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0e68-111">`GetFunctionFromIP2` はガベージコレクションをトリガーできますが、`GetFunctionFromIP` は実行されません。</span><span class="sxs-lookup"><span data-stu-id="e0e68-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="e0e68-112">詳細については、「 [HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e68-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e68-113">要件</span><span class="sxs-lookup"><span data-stu-id="e0e68-113">Requirements</span></span>  
 <span data-ttu-id="e0e68-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e68-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0e68-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0e68-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0e68-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0e68-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0e68-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0e68-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e68-118">参照</span><span class="sxs-lookup"><span data-stu-id="e0e68-118">See also</span></span>

- [<span data-ttu-id="e0e68-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0e68-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
