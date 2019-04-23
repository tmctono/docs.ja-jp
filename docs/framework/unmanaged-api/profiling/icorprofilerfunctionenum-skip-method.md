---
title: ICorProfilerFunctionEnum::Skip メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e334c75afee60591db2b4e1f45cf0ec753ee2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141651"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="5b1be-102">ICorProfilerFunctionEnum::Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="5b1be-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="5b1be-103">指定した数の要素がスキップされるように、この列挙子のカーソルを現在の位置から進めます。</span><span class="sxs-lookup"><span data-stu-id="5b1be-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b1be-104">構文</span><span class="sxs-lookup"><span data-stu-id="5b1be-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b1be-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5b1be-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5b1be-106">[in]スキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="5b1be-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b1be-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="5b1be-107">Return Value</span></span>  
 <span data-ttu-id="5b1be-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="5b1be-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5b1be-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b1be-109">HRESULT</span></span>|<span data-ttu-id="5b1be-110">説明</span><span class="sxs-lookup"><span data-stu-id="5b1be-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b1be-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b1be-111">S_OK</span></span>|<span data-ttu-id="5b1be-112">`celt` 要素がスキップされました。</span><span class="sxs-lookup"><span data-stu-id="5b1be-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="5b1be-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5b1be-113">S_FALSE</span></span>|<span data-ttu-id="5b1be-114">少ない`celt`要素がスキップされたない要素があることを示します。</span><span class="sxs-lookup"><span data-stu-id="5b1be-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b1be-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="5b1be-115">Remarks</span></span>  
 <span data-ttu-id="5b1be-116">この列挙子のカーソルの新しい位置は (現在の位置) +`celt`します。</span><span class="sxs-lookup"><span data-stu-id="5b1be-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b1be-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="5b1be-117">Requirements</span></span>  
 <span data-ttu-id="5b1be-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b1be-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b1be-119">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b1be-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b1be-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b1be-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b1be-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b1be-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b1be-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b1be-122">See also</span></span>

- [<span data-ttu-id="5b1be-123">ICorProfilerFunctionEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b1be-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="5b1be-124">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5b1be-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
