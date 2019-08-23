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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c133338ec0edac19f49d435df41e3081c486f51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948460"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="4539b-102">ICorProfilerInfo4::GetFunctionFromIP2 メソッド</span><span class="sxs-lookup"><span data-stu-id="4539b-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="4539b-103">マネージコード命令ポインターを JIT 再コンパイルされた関数のバージョンにマップします。</span><span class="sxs-lookup"><span data-stu-id="4539b-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4539b-104">構文</span><span class="sxs-lookup"><span data-stu-id="4539b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4539b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4539b-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="4539b-106">からマネージコード内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="4539b-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="4539b-107">入出力関数 ID。</span><span class="sxs-lookup"><span data-stu-id="4539b-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="4539b-108">入出力関数の JIT 再コンパイルバージョンの id。</span><span class="sxs-lookup"><span data-stu-id="4539b-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4539b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4539b-109">Remarks</span></span>  
 <span data-ttu-id="4539b-110">`GetFunctionFromIP2`はと似`GetFunctionFromIP`ていますが、指定された IP アドレスを含む関数の関数 id ではなく、JIT 再コンパイルされた id を取得する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="4539b-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4539b-111">`GetFunctionFromIP2``GetFunctionFromIP`はガベージコレクションをトリガーできますが、では発生しません。</span><span class="sxs-lookup"><span data-stu-id="4539b-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="4539b-112">詳細については、「 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4539b-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4539b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="4539b-113">Requirements</span></span>  
 <span data-ttu-id="4539b-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4539b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4539b-115">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="4539b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4539b-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="4539b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4539b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4539b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4539b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4539b-118">See also</span></span>

- [<span data-ttu-id="4539b-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4539b-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
