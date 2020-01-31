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
ms.openlocfilehash: a675cc301d2dd32f87e3864a3123e2044761ef91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868357"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="08f97-102">ICorProfilerInfo7:: Getinmemoryシンボルの長さメソッド</span><span class="sxs-lookup"><span data-stu-id="08f97-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="08f97-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="08f97-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="08f97-104">メモリ内シンボルストリームの長さを返します。</span><span class="sxs-lookup"><span data-stu-id="08f97-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f97-105">構文</span><span class="sxs-lookup"><span data-stu-id="08f97-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08f97-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="08f97-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="08f97-107">からメモリ内ストリームを格納しているモジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="08f97-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="08f97-108">Pcountシンボルバイト数</span><span class="sxs-lookup"><span data-stu-id="08f97-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="08f97-109">入出力メソッドから制御が戻るときに、ストリーム長がバイト単位で格納されている `DWORD` 値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="08f97-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08f97-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="08f97-110">Return Value</span></span>  
 <span data-ttu-id="08f97-111">このメソッドは、ゼロ (0) であっても、メモリストリームの長さを特定できる場合に `S_OK` を返します。</span><span class="sxs-lookup"><span data-stu-id="08f97-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="08f97-112">メソッドが <xref:System.Reflection.Emit?displayProperty=nameWithType>を使用して作成された場合、メソッドは `CORPROF_E_MODULE_IS_DYNAMIC` を返します。</span><span class="sxs-lookup"><span data-stu-id="08f97-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08f97-113">コメント</span><span class="sxs-lookup"><span data-stu-id="08f97-113">Remarks</span></span>  
 <span data-ttu-id="08f97-114">モジュールにメモリ内シンボルがある場合、ストリームの長さは `pCountSymbolBytes`に配置されます。</span><span class="sxs-lookup"><span data-stu-id="08f97-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="08f97-115">モジュールにメモリ内シンボルがない場合は、`*pCountSymbolBytes = 0`ます。</span><span class="sxs-lookup"><span data-stu-id="08f97-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08f97-116">現在の実装では、リフレクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="08f97-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="08f97-117">モジュールがリフレクションを使用して作成された場合、メソッドは `CORPROF_E_MODULE_IS_DYNAMIC`を返します。</span><span class="sxs-lookup"><span data-stu-id="08f97-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f97-118">要件</span><span class="sxs-lookup"><span data-stu-id="08f97-118">Requirements</span></span>  
 <span data-ttu-id="08f97-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08f97-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f97-120">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08f97-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08f97-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08f97-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08f97-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f97-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f97-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="08f97-123">See also</span></span>

- [<span data-ttu-id="08f97-124">ICorProfilerInfo7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08f97-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
