---
title: ICorProfilerModuleEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
ms.openlocfilehash: fb7a2a6d8bac7e9a67a5275694fc07e0f1d469e1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861334"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="89d9b-102">ICorProfilerModuleEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="89d9b-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="89d9b-103">指定した数の要素がスキップされるように、この列挙子のカーソルを現在の位置から進めます。</span><span class="sxs-lookup"><span data-stu-id="89d9b-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="89d9b-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89d9b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="89d9b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="89d9b-106">からスキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="89d9b-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89d9b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="89d9b-107">Return Value</span></span>  
 <span data-ttu-id="89d9b-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="89d9b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="89d9b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89d9b-109">HRESULT</span></span>|<span data-ttu-id="89d9b-110">説明</span><span class="sxs-lookup"><span data-stu-id="89d9b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89d9b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="89d9b-111">S_OK</span></span>|<span data-ttu-id="89d9b-112">`celt` の要素はスキップされました。</span><span class="sxs-lookup"><span data-stu-id="89d9b-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="89d9b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="89d9b-113">S_FALSE</span></span>|<span data-ttu-id="89d9b-114">`celt` 要素がスキップされました。これは、要素がこれ以上存在しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="89d9b-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89d9b-115">コメント</span><span class="sxs-lookup"><span data-stu-id="89d9b-115">Remarks</span></span>  
 <span data-ttu-id="89d9b-116">この列挙子のカーソルの新しい位置は、(現在位置) + `celt`です。</span><span class="sxs-lookup"><span data-stu-id="89d9b-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d9b-117">要件</span><span class="sxs-lookup"><span data-stu-id="89d9b-117">Requirements</span></span>  
 <span data-ttu-id="89d9b-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89d9b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d9b-119">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89d9b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89d9b-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89d9b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89d9b-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d9b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d9b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="89d9b-122">See also</span></span>

- [<span data-ttu-id="89d9b-123">ICorProfilerModuleEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="89d9b-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="89d9b-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="89d9b-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
