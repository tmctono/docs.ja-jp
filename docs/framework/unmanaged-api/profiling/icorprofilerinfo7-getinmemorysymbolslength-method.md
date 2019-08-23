---
title: 'ICorProfilerInfo7:: Getinmemoryシンボルの長さメソッド'
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
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955428"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="1a856-102">ICorProfilerInfo7:: Getinmemoryシンボルの長さメソッド</span><span class="sxs-lookup"><span data-stu-id="1a856-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="1a856-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="1a856-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="1a856-104">メモリ内シンボルストリームの長さを返します。</span><span class="sxs-lookup"><span data-stu-id="1a856-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a856-105">構文</span><span class="sxs-lookup"><span data-stu-id="1a856-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a856-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a856-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="1a856-107">からメモリ内ストリームを格納しているモジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="1a856-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="1a856-108">Pcountシンボルバイト数</span><span class="sxs-lookup"><span data-stu-id="1a856-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="1a856-109">入出力メソッドから制御が`DWORD`戻るときに、ストリーム長がバイト単位で格納されている値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a856-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a856-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="1a856-110">Return Value</span></span>  
 <span data-ttu-id="1a856-111">メモリストリームの`S_OK`長さがゼロ (0) であっても、このメソッドはを返します。</span><span class="sxs-lookup"><span data-stu-id="1a856-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="1a856-112">メソッドがを`CORPROF_E_MODULE_IS_DYNAMIC`使用して<xref:System.Reflection.Emit?displayProperty=nameWithType>作成された場合、メソッドはを返します。</span><span class="sxs-lookup"><span data-stu-id="1a856-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a856-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a856-113">Remarks</span></span>  
 <span data-ttu-id="1a856-114">モジュールにメモリ内シンボルがある場合は、ストリームの長さがに`pCountSymbolBytes`配置されます。</span><span class="sxs-lookup"><span data-stu-id="1a856-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="1a856-115">モジュールにメモリ内シンボル`*pCountSymbolBytes = 0`がない場合は。</span><span class="sxs-lookup"><span data-stu-id="1a856-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a856-116">現在の実装では、リフレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a856-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="1a856-117">モジュールがリフレクションを使用して作成された場合、メソッド`CORPROF_E_MODULE_IS_DYNAMIC`はを返します。</span><span class="sxs-lookup"><span data-stu-id="1a856-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a856-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="1a856-118">Requirements</span></span>  
 <span data-ttu-id="1a856-119">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a856-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a856-120">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="1a856-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a856-121">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="1a856-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a856-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a856-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a856-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a856-123">See also</span></span>

- [<span data-ttu-id="1a856-124">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a856-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
