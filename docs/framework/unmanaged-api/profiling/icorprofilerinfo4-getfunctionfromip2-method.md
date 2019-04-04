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
ms.openlocfilehash: 51f8768fc3cd73f0fd5bdb84842af03b900fafdf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495352"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="c4844-102">ICorProfilerInfo4::GetFunctionFromIP2 メソッド</span><span class="sxs-lookup"><span data-stu-id="c4844-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="c4844-103">マネージ コードの命令ポインターを関数の JIT 再コンパイル バージョンにマップします。</span><span class="sxs-lookup"><span data-stu-id="c4844-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4844-104">構文</span><span class="sxs-lookup"><span data-stu-id="c4844-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4844-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4844-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="c4844-106">[in]マネージ コードで命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="c4844-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="c4844-107">[out]関数の id です。</span><span class="sxs-lookup"><span data-stu-id="c4844-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="c4844-108">[out]関数の JIT 再コンパイル バージョンの id。</span><span class="sxs-lookup"><span data-stu-id="c4844-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4844-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4844-109">Remarks</span></span>  
 <span data-ttu-id="c4844-110">`GetFunctionFromIP2` ような`GetFunctionFromIP`を指定した IP アドレスを含む関数の関数の ID ではなく、JIT 再コンパイルの ID を取得する点を除いて、します。</span><span class="sxs-lookup"><span data-stu-id="c4844-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4844-111">`GetFunctionFromIP2` 一方、ガベージ コレクションをトリガーできる`GetFunctionFromIP`されません。</span><span class="sxs-lookup"><span data-stu-id="c4844-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="c4844-112">詳細については、[CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4844-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4844-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c4844-113">Requirements</span></span>  
 <span data-ttu-id="c4844-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4844-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4844-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4844-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4844-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4844-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4844-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4844-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4844-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4844-118">See also</span></span>
- [<span data-ttu-id="c4844-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4844-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
