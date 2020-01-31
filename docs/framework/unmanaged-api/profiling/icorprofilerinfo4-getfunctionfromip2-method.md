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
ms.openlocfilehash: 8ad04a7a6705b961686317c9473b885fb90676ce
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861919"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="788d5-102">ICorProfilerInfo4::GetFunctionFromIP2 メソッド</span><span class="sxs-lookup"><span data-stu-id="788d5-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="788d5-103">マネージコード命令ポインターを JIT 再コンパイルされた関数のバージョンにマップします。</span><span class="sxs-lookup"><span data-stu-id="788d5-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="788d5-104">構文</span><span class="sxs-lookup"><span data-stu-id="788d5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="788d5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="788d5-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="788d5-106">からマネージコード内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="788d5-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="788d5-107">入出力関数 ID。</span><span class="sxs-lookup"><span data-stu-id="788d5-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="788d5-108">入出力関数の JIT 再コンパイルバージョンの id。</span><span class="sxs-lookup"><span data-stu-id="788d5-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="788d5-109">コメント</span><span class="sxs-lookup"><span data-stu-id="788d5-109">Remarks</span></span>  
 <span data-ttu-id="788d5-110">`GetFunctionFromIP2` は `GetFunctionFromIP`に似ていますが、指定された IP アドレスを含む関数の関数 ID ではなく、JIT 再コンパイルされた ID を取得する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="788d5-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="788d5-111">`GetFunctionFromIP2` はガベージコレクションをトリガーできますが、`GetFunctionFromIP` は実行されません。</span><span class="sxs-lookup"><span data-stu-id="788d5-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="788d5-112">詳細については、「 [HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="788d5-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="788d5-113">要件</span><span class="sxs-lookup"><span data-stu-id="788d5-113">Requirements</span></span>  
 <span data-ttu-id="788d5-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="788d5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="788d5-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="788d5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="788d5-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="788d5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="788d5-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="788d5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="788d5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="788d5-118">See also</span></span>

- [<span data-ttu-id="788d5-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="788d5-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
