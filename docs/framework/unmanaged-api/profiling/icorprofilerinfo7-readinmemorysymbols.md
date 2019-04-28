---
title: ICorProfilerInfo7::ReadInMemorySymbols
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
ms.openlocfilehash: 662863ec69e464dafe893552f1d81755313acc75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786230"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="6cec9-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="6cec9-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="6cec9-103">[[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 以降のバージョンでサポート]</span><span class="sxs-lookup"><span data-stu-id="6cec9-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="6cec9-104">メモリ内のシンボルのストリームからバイトを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="6cec9-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cec9-105">構文</span><span class="sxs-lookup"><span data-stu-id="6cec9-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cec9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6cec9-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="6cec9-107">[in]メモリ内のストリームを含むモジュールの識別子です。</span><span class="sxs-lookup"><span data-stu-id="6cec9-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="6cec9-108">[in]バイトの読み取りを開始する位置のメモリ内ストリーム内のオフセット。</span><span class="sxs-lookup"><span data-stu-id="6cec9-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="6cec9-109">[out]データのコピー先バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6cec9-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="6cec9-110">バッファーがあります`countSymbolBytes`使用可能な領域。</span><span class="sxs-lookup"><span data-stu-id="6cec9-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="6cec9-111">[in]コピーするバイト数。</span><span class="sxs-lookup"><span data-stu-id="6cec9-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="6cec9-112">[out]メソッドが戻るとき、実際に読み取られたバイト数を格納します。</span><span class="sxs-lookup"><span data-stu-id="6cec9-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cec9-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="6cec9-113">Return Value</span></span>  
 <span data-ttu-id="6cec9-114">`S_OK`、読み取られたバイト数を 0 以外の場合。</span><span class="sxs-lookup"><span data-stu-id="6cec9-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="6cec9-115">`CORPROF_E_MODULE_IS_DYNAMIC`を使用して、モジュールが作成された場合<xref:System.Reflection.Emit>します。</span><span class="sxs-lookup"><span data-stu-id="6cec9-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cec9-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="6cec9-116">Remarks</span></span>  
 <span data-ttu-id="6cec9-117">`ReadInMemorySymbols`メソッドの読み取りを試みます`countSymbolBytes`オフセットから始まるデータの`symbolsReadOffset`メモリ内ストリーム内で。</span><span class="sxs-lookup"><span data-stu-id="6cec9-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="6cec9-118">データをコピー`pSymbolBytes`が想定されています`countSymbolBytes`使用可能な領域。</span><span class="sxs-lookup"><span data-stu-id="6cec9-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="6cec9-119">`pCountSymbolsBytesRead` 実際の少ない可能性がありますが、読み取られたバイト数を含むより`countSymbolBytes`ストリームの末尾に達した場合。</span><span class="sxs-lookup"><span data-stu-id="6cec9-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cec9-120">現在の実装は、Reflection.Emit をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6cec9-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="6cec9-121">かどうか、モジュールは、Reflection.Emit を使用して作成された、メソッドを返します`CORPROF_E_MODULE_IS_DYNAMIC`します。</span><span class="sxs-lookup"><span data-stu-id="6cec9-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cec9-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="6cec9-122">Requirements</span></span>  
 <span data-ttu-id="6cec9-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cec9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cec9-124">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6cec9-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6cec9-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cec9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cec9-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cec9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cec9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cec9-127">See also</span></span>

- [<span data-ttu-id="6cec9-128">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6cec9-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
