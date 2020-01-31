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
ms.openlocfilehash: 6d50a5d74eccff6fe39aca111f768bac4d8f2e2e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868331"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="15902-102">ICorProfilerInfo8:: GetFunctionFromIP3 メソッド</span><span class="sxs-lookup"><span data-stu-id="15902-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="15902-103">マネージコード命令ポインターを FunctionID にマップします。</span><span class="sxs-lookup"><span data-stu-id="15902-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="15902-104">このメソッドは、動的メソッドと非動的メソッドの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="15902-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="15902-105">構文</span><span class="sxs-lookup"><span data-stu-id="15902-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a><span data-ttu-id="15902-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15902-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="15902-107">in] マネージコード内の命令ポインターを \[します。</span><span class="sxs-lookup"><span data-stu-id="15902-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="15902-108">\[] 関数 ID。</span><span class="sxs-lookup"><span data-stu-id="15902-108">\[out] The function ID.</span></span>

- `pReJitId`

  <span data-ttu-id="15902-109">\[out] 関数の JIT 再コンパイルバージョンの id。</span><span class="sxs-lookup"><span data-stu-id="15902-109">\[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="15902-110">コメント</span><span class="sxs-lookup"><span data-stu-id="15902-110">Remarks</span></span>

<span data-ttu-id="15902-111">このメソッドは、動的メソッドと非動的メソッドの両方に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="15902-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="15902-112">これは[GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)のスーパーセットであり、メタデータを持つ関数に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="15902-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="15902-113">要件</span><span class="sxs-lookup"><span data-stu-id="15902-113">Requirements</span></span>

<span data-ttu-id="15902-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15902-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="15902-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15902-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="15902-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15902-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="15902-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15902-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="15902-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="15902-118">See also</span></span>

- [<span data-ttu-id="15902-119">ICorProfilerInfo8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15902-119">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
