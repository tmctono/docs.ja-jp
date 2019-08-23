---
title: 'ICorProfilerInfo7:: ReadInMemorySymbols'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955371"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="5e17e-102">ICorProfilerInfo7:: ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="5e17e-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="5e17e-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="5e17e-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="5e17e-104">メモリ内シンボルストリームからバイトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5e17e-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e17e-105">構文</span><span class="sxs-lookup"><span data-stu-id="5e17e-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e17e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e17e-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5e17e-107">からメモリ内ストリームを格納しているモジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="5e17e-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="5e17e-108">からメモリ内ストリーム内でバイトの読み取りを開始する位置のオフセット。</span><span class="sxs-lookup"><span data-stu-id="5e17e-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="5e17e-109">入出力データがコピーされるバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5e17e-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="5e17e-110">バッファーには、 `countSymbolBytes`使用可能な領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="5e17e-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="5e17e-111">からコピーするバイト数。</span><span class="sxs-lookup"><span data-stu-id="5e17e-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="5e17e-112">入出力メソッドから制御が戻るときに、実際に読み取られたバイト数を格納します。</span><span class="sxs-lookup"><span data-stu-id="5e17e-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e17e-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="5e17e-113">Return Value</span></span>  
 <span data-ttu-id="5e17e-114">`S_OK`0以外のバイト数が読み取られた場合は。</span><span class="sxs-lookup"><span data-stu-id="5e17e-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="5e17e-115">`CORPROF_E_MODULE_IS_DYNAMIC`モジュールがを使用して<xref:System.Reflection.Emit>作成された場合は。</span><span class="sxs-lookup"><span data-stu-id="5e17e-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e17e-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e17e-116">Remarks</span></span>  
 <span data-ttu-id="5e17e-117">メソッド`ReadInMemorySymbols`は、インメモリ`countSymbolBytes`ストリーム内のオフセット`symbolsReadOffset`を開始位置として、データの読み取りを試みます。</span><span class="sxs-lookup"><span data-stu-id="5e17e-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="5e17e-118">データはに`pSymbolBytes`コピーされます。これには`countSymbolBytes` 、使用可能な領域があることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="5e17e-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="5e17e-119">`pCountSymbolsBytesRead`実際に読み取られたバイト数を格納します。ストリーム`countSymbolBytes`の末尾に到達した場合よりも小さくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="5e17e-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e17e-120">現在の実装では、リフレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5e17e-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="5e17e-121">モジュールがリフレクションを使用して作成された場合、メソッド`CORPROF_E_MODULE_IS_DYNAMIC`はを返します。</span><span class="sxs-lookup"><span data-stu-id="5e17e-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e17e-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e17e-122">Requirements</span></span>  
 <span data-ttu-id="5e17e-123">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e17e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e17e-124">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="5e17e-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e17e-125">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="5e17e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e17e-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e17e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e17e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e17e-127">See also</span></span>

- [<span data-ttu-id="5e17e-128">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e17e-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
