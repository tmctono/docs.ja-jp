---
title: ICorProfilerFunctionControl::SetILInstrumentedCodeMap メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b36439dd6fb882bb41c38e953cb7b1c5f2b93d30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041380"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a><span data-ttu-id="84d9b-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="84d9b-102">ICorProfilerFunctionControl::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="84d9b-103">指定した共通中間言語 (CIL) マップ エントリを使用して、指定される関数のコード マップを設定します。</span><span class="sxs-lookup"><span data-stu-id="84d9b-103">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="84d9b-104">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84d9b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="84d9b-105">Parameters</span></span>  
 `cILMapEntries`  
 <span data-ttu-id="84d9b-106">[in] マップ内のエントリの数。</span><span class="sxs-lookup"><span data-stu-id="84d9b-106">[in] The number of entries in the map.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="84d9b-107">[in]COR_IL_MAP エントリの呼び出し元が割り当てた配列。</span><span class="sxs-lookup"><span data-stu-id="84d9b-107">[in] The caller-allocated array of COR_IL_MAP  entries.</span></span> <span data-ttu-id="84d9b-108">これらのエントリの解釈が同じである、 [icorprofilerinfo::setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="84d9b-108">The interpretation of these entries is the same as for the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84d9b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="84d9b-109">Remarks</span></span>  
 <span data-ttu-id="84d9b-110">このメソッドを呼び出して、マッピングの設定を使用するマッピングを呼び出すことによって取得デバッガー [icordebugilcode 2::getinstrumentedilmap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="84d9b-110">Setting the mapping by calling this method allows the debugger to retrieve the mapping by calling [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md).</span></span> <span data-ttu-id="84d9b-111">またデバッガーは、スタック トレースおよび可変的な有効期間に対する IL オフセットを計算するときに、マッピングを内部で使用できます。</span><span class="sxs-lookup"><span data-stu-id="84d9b-111">It also allows the debugger to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d9b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="84d9b-112">Requirements</span></span>  
 <span data-ttu-id="84d9b-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d9b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d9b-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84d9b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84d9b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84d9b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84d9b-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d9b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d9b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="84d9b-117">See also</span></span>

- [<span data-ttu-id="84d9b-118">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84d9b-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
