---
title: ICorProfilerModuleEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
ms.openlocfilehash: 361f08f8c787ad4c1288c56fb1bdb4d5136933e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442692"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="f94c6-102">ICorProfilerModuleEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f94c6-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="f94c6-103">モジュールのシーケンシャル コレクションから、列挙子の現在の位置以降にある指定した数の隣接するモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="f94c6-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="f94c6-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f94c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f94c6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f94c6-106">[in] 取得するモジュールの数。</span><span class="sxs-lookup"><span data-stu-id="f94c6-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="f94c6-107">[out] それぞれが取得されたモジュールを表す、`ModuleID` 値の配列。</span><span class="sxs-lookup"><span data-stu-id="f94c6-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f94c6-108">[out] `ids` 配列で実際に返されるモジュールの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f94c6-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f94c6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f94c6-109">Return Value</span></span>  
 <span data-ttu-id="f94c6-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="f94c6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f94c6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f94c6-111">HRESULT</span></span>|<span data-ttu-id="f94c6-112">説明</span><span class="sxs-lookup"><span data-stu-id="f94c6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f94c6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f94c6-113">S_OK</span></span>|<span data-ttu-id="f94c6-114">`celt` 要素が返されました。</span><span class="sxs-lookup"><span data-stu-id="f94c6-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="f94c6-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f94c6-115">S_FALSE</span></span>|<span data-ttu-id="f94c6-116">`celt` よりも少ない数の要素が返されました。これは、列挙が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f94c6-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f94c6-117">要件</span><span class="sxs-lookup"><span data-stu-id="f94c6-117">Requirements</span></span>  
 <span data-ttu-id="f94c6-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f94c6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f94c6-119">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f94c6-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f94c6-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f94c6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f94c6-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f94c6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94c6-122">参照</span><span class="sxs-lookup"><span data-stu-id="f94c6-122">See also</span></span>

- [<span data-ttu-id="f94c6-123">ICorProfilerModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f94c6-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="f94c6-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f94c6-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
