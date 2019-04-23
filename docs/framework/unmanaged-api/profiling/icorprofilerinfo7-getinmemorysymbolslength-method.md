---
title: ICorProfilerInfo7::GetInMemorySymbolsLength メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 422fdfef6bea40e0f4bcc7447df8dba1eab2896e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146095"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="1b0fb-102">ICorProfilerInfo7::GetInMemorySymbolsLength メソッド</span><span class="sxs-lookup"><span data-stu-id="1b0fb-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="1b0fb-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="1b0fb-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="1b0fb-104">メモリ内のシンボルのストリームの長さを返します。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b0fb-105">構文</span><span class="sxs-lookup"><span data-stu-id="1b0fb-105">Syntax</span></span>  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b0fb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b0fb-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="1b0fb-107">[in]メモリ内のストリームを含むモジュールの識別子です。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="1b0fb-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="1b0fb-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="1b0fb-109">[out]ポインターを`DWORD`メソッドが戻るときに、バイト単位のストリームの長さを格納する値。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b0fb-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="1b0fb-110">Return Value</span></span>  
 <span data-ttu-id="1b0fb-111">メソッドを返します`S_OK`かどうかメモリ ストリームの長さを決定できますはゼロ (0) 場合でもです。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="1b0fb-112">メソッドを返します`CORPROF_E_MODULE_IS_DYNAMIC`を使用して、メソッドが作成された場合<xref:System.Reflection.Emit?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b0fb-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b0fb-113">Remarks</span></span>  
 <span data-ttu-id="1b0fb-114">モジュールは、メモリ内のシンボルには、ストリームの長さに置かれます。`pCountSymbolBytes`します。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="1b0fb-115">モジュールは、メモリ内のシンボルを持っていない場合`*pCountSymbolBytes = 0`します。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b0fb-116">現在の実装は、Reflection.Emit をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="1b0fb-117">かどうか、モジュールは、Reflection.Emit を使用して作成された、メソッドを返します`CORPROF_E_MODULE_IS_DYNAMIC`します。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b0fb-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="1b0fb-118">Requirements</span></span>  
 <span data-ttu-id="1b0fb-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b0fb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b0fb-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b0fb-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b0fb-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b0fb-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b0fb-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b0fb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0fb-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b0fb-123">See also</span></span>

- [<span data-ttu-id="1b0fb-124">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b0fb-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
