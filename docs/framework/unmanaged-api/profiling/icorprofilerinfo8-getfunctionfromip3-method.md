---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f3c0a3525c87fbf39199c15a6619ff4a0d2acc42
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973852"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="21acf-102">ICorProfilerInfo8:: GetFunctionFromIP3 メソッド</span><span class="sxs-lookup"><span data-stu-id="21acf-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>
  
  <span data-ttu-id="21acf-103">マネージコード命令ポインターを FunctionID にマップします。</span><span class="sxs-lookup"><span data-stu-id="21acf-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="21acf-104">このメソッドは、動的メソッドと非動的メソッドの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="21acf-104">This method works for both dynamic and non-dynamic methods.</span></span>    
  
## <a name="syntax"></a><span data-ttu-id="21acf-105">構文</span><span class="sxs-lookup"><span data-stu-id="21acf-105">Syntax</span></span>  
  
```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```  
  
#### <a name="parameters"></a><span data-ttu-id="21acf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21acf-106">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="21acf-107">からマネージコード内の命令ポインター。</span><span class="sxs-lookup"><span data-stu-id="21acf-107">[in] The instruction pointer in managed code.</span></span>  

 `pFunctionId`  
 <span data-ttu-id="21acf-108">入出力関数 ID。</span><span class="sxs-lookup"><span data-stu-id="21acf-108">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="21acf-109">入出力関数の JIT 再コンパイルバージョンの id。</span><span class="sxs-lookup"><span data-stu-id="21acf-109">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21acf-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="21acf-110">Remarks</span></span>  
 <span data-ttu-id="21acf-111">このメソッドは、動的メソッドと非動的メソッドの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="21acf-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="21acf-112">これは[GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)のスーパーセットであり、メタデータを持つ関数に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="21acf-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>
  

## <a name="requirements"></a><span data-ttu-id="21acf-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="21acf-113">Requirements</span></span>  
 <span data-ttu-id="21acf-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21acf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21acf-115">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="21acf-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21acf-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="21acf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21acf-117">**.NET Framework のバージョン:** [![Net_current_v472plus](../../../../includes/net-current-v472plus.md)を含める</span><span class="sxs-lookup"><span data-stu-id="21acf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21acf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="21acf-118">See also</span></span>
- [<span data-ttu-id="21acf-119">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21acf-119">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

